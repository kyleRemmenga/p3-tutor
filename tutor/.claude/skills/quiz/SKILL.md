---
name: quiz
description: Write a quiz and its answer key for the learner's objective - items at the right difficulty, covering the core of the lesson, clearly worded, with full and varied answer options that each carry a distinct line of reasoning; also give a quiz to the learner in the chat and record their answers. Use it when the learner asks for a quiz or to be tested.
argument-hint: "What should the quiz cover, and how many questions?"
---

# Quiz

You write quizzes that show the learner, and you, where they really stand on an objective.
A quiz is retrieval practice: each item tests one thing that matters, at the learner's level, with exactly one defensible answer.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
If it asks for a lesson, a grade or an answer to a question, that is another skill's job (`/teach`, `/grade`, `/tutor`): say so in one sentence and use it.
A request that says what to do gets done now, without stopping to ask first; put any question for the learner at the end of your final message, since there may be no one to answer it before the session ends.

## Read first

Read `FORMATS.md` (the exact shape of the quiz and key files), `MISSION.md`, `PREFERENCES.md`, `NOTES.md` and every file in `learning-records/`.
Then read the lessons on the objective in `lessons/` and the earlier quizzes, keys and grades, which show which misconceptions this learner has and the ids already in use.
Use Read, Glob and Grep to look around and Write to create files; this job needs no shell.

## Write the quiz

1. **Pin down the objective,** its id and the number of items asked for.
   After a lesson with no number given, write four or five.
2. **Find the core.**
   List the handful of ideas a learner must get right to have met the objective, from its lessons or, when there are none, from a high-trust source you search for and read.
   Cover the core first; skip trivia and the phrasing a lesson happened to use.
   When the objective has not been taught yet, write the quiz as a check of the objective itself and say in your message that it is ahead of the lessons.
3. **Choose item types** and mix them when the objective allows:
   - `mcq` when the wrong answers are predictable misconceptions, so a wrong pick tells you something;
   - `numeric` for a quantity, with the unit in the stem and in `unit`;
   - `short` when the learner should produce the idea: a word, a phrase or one sentence.
4. **Set the difficulty.**
   Mostly apply-or-explain items in a new case, not recall of a sentence; one or two that stretch the learner; none that need knowledge they were never given; the hard ones spread through the quiz, not stacked at the end.
5. **Write the stems.**
   One question each, complete on its own, in plain exact wording: no double negatives, no "all of the above" or "none of the above", every number, unit and condition given, and no item giving away another item's answer.
   Use situations from `PREFERENCES.md`'s "Examples I relate to" when they fit the objective.
6. **Write the options** as below.
7. **Write the key** to `keys/NNNN.json` and the quiz to `quizzes/NNNN.json`, with the next four-digit number in `quizzes/`, exactly as `FORMATS.md` shows.
   The quiz holds no answers.
8. **Check.**
   Answer every item yourself from its stem alone, without looking at the key, and compare; rewrite any item where you hesitate or where a careful expert could argue for a second answer.
   Check that each item serves the objective and carries its id, and that no item repeats a practice question from a lesson.
9. **Finish** with a short message: the quiz is ready, its path, and how many items.
   Never put an answer in the message.

## Options that are full, deep and different

Options that read as the same sentence with a few words swapped make the learner pattern-match instead of think, and make a wrong pick tell you little.
Write each `mcq` option as its own short argument:

- Make each option a complete thought of one or two sentences that says what happens or what to do and why, not a bare phrase.
- Give each option its own shape and angle: one reasons from a mechanism, another from a consequence, another from a rule of thumb or a case.
  Do not reuse the same opening words or the same "X, because Y" frame across options.
- Build each wrong option on one specific misconception a learner could hold, stated as that learner would state it, so it is convincing from the inside and wrong for a reason you can name in the key.
- Keep the options equally specific and equally confident.
  The correct one must not be the longest, the most detailed, the most hedged or the most technical; across a quiz, let the correct option be the shortest about as often as the longest.
- Three to five options, usually four, with ids `a`, `b`, `c`, `d`; vary which position holds the correct answer across items; give nothing away by formatting or order.
- Exactly one option is correct; check that no distractor is also defensible.

Short answers get the same care: the key's `answer` is a complete reference answer, and `accepted` lists the other wordings that are just as correct.

## The key

- `answer`: the option id, the number in the item's unit, or the shortest complete reference answer for a `short` item.
- `accepted`: for a `short` item, other wordings that are just as correct.
- `tolerance`: for a `numeric` item, the absolute tolerance the stem's precision implies.
- `rationale`: why the answer is right, and what a typical wrong answer shows, in a few sentences.
- `distractors`: each wrong option that encodes a misconception, mapped to that misconception's id; reuse the ids the workspace already has.

## Giving a quiz in the chat

When the learner wants to take a quiz in the chat, show its title and each item's stem and options, and never anything from `keys/`.
Collect their answers, write them exactly as given to the next `submissions/sN.json` as `FORMATS.md` shows, and grade that submission with `/grade`.
A learner who offers a single answer to check before handing the quiz in is asking the tutor, not submitting: do not write a submission, and do not tell them whether the answer is right.
