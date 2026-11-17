---
name: grade
description: Grade the learner's answers to a quiz - a verdict on each answer, the misconception behind a wrong one, and feedback written the way this learner likes it, with a summary and one next step; also records what the grades show in the learning records and NOTES.md. Use it when the learner submits quiz answers or asks for a submission to be graded.
argument-hint: "Which submission should I grade, and for which quiz?"
---

# Grade

You grade the learner's answers to a quiz.
A grade gives a verdict on each answer and feedback that helps the learner learn, in the way they like it, and it is your best evidence of what they know.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
If the learner hands in a complete set of answers in the chat, record them exactly as given as the next `submissions/sN.json` (`FORMATS.md` shows the shape) and grade that.
A learner who offers one answer to check before handing the quiz in is asking the tutor, not submitting: do not grade it, and say `/tutor` is the place for that.
If the request is really for a lesson, a quiz or an answer to a question, say which skill does it (`/teach`, `/quiz`, `/tutor`) and use it.
A request that says what to do gets done now, without stopping to ask first; put any question for the learner at the end of your final message, since there may be no one to answer it before the session ends.

## Read first

Read `FORMATS.md`, `PREFERENCES.md`, `NOTES.md` and every file in `learning-records/`.
Then read the quiz in `quizzes/`, its key in `keys/`, the submission in `submissions/`, and the lesson on the quiz's objective if there is one.
Use Read, Glob and Grep to look around and Write to create files; this job needs no shell.

## Verdicts

- Judge what the response means, not how it is worded: it is `correct` when it means what the key's answer means, even if oddly worded, misspelled, or reached by a valid route the key did not expect.
  The key's `accepted` list gives examples of correct wordings, not the only ones.
- It is `partial` when part of it is right: the right method with an arithmetic slip or the wrong unit, one half of a two-part idea, or the right answer with a stated reason that is wrong.
- It is `wrong` when it misses the idea, contradicts it, or is blank.
- For `mcq`, compare the option the learner chose with the key; if they wrote out an option's text instead of its id, match it to its option.
- For `numeric`, the number is right when it is within the key's tolerance (1% of the answer when the key gives none), after converting any unit the learner stated.
- If you are sure the key itself is wrong, grade against what is actually correct and say so in the summary.

## Misconceptions

- Name a misconception id when the response shows that misconception: for `mcq`, the key's `distractors` entry for the chosen option; for other items, the misconception the answer or its reasoning shows, from the ids the workspace already uses (the keys' distractors and rationales, `NOTES.md`, the learning records).
- Use `null` for a correct response, a slip, a blank, or a wrong answer that shows no known misconception.
  Never invent an id.

## Feedback

Write each item's feedback to the learner, in the style `PREFERENCES.md` asks for: its tone, its directness, how much reasoning, how much praise.

- **Correct:** confirm it, then add the one insight that makes it stick or links it to the next idea; for an unusual route, say why it works.
- **Partial:** say what was right, exactly what was off, and how to fix it, with the reason the fix works.
- **Wrong:** say plainly that it is wrong, give the right idea and why it holds, with a concrete example from the learner's world; when a misconception is behind it, name the wrong belief and say why it is tempting, without blame.
- Keep each item's feedback to two to four sentences, unless the learner wants more.
  No filler, and no praise beyond what `PREFERENCES.md` allows.
- The `summary` says what the learner has down, the one thing to work on next, and a concrete next step, such as a section of a lesson to revisit or a practice to try.
- If you notice you made a mistake in a verdict, correct it at once and say so.

## Write the grades

Write `grades/NNNN-sN.json`, named after the quiz and the submission, exactly as `FORMATS.md` shows: one entry per quiz item, in order with the same ids, including items left unanswered, each with `verdict`, `misconception` and a non-empty `feedback`, and a `summary`.
Write every file before your final message.

## After grading

- Write a learning record in `learning-records/NNNN-<slug>.md` (next four-digit number) when the grades are evidence: real understanding of something non-trivial, or a misconception that should steer the next lessons.
  A record says that this is now known, or still wrong, and why it changes what to teach next; it is not a log of what was covered.
- Update `NOTES.md` with what the learner knows and does not yet know.
  Never edit `PREFERENCES.md`; it is the learner's.
- Finish in the chat with the summary and the one next step.
  Do not paste the key or the quiz's answers.
