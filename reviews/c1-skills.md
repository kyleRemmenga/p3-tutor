# Reviews: c1-skills

Your quick rounds while you build `c1-skills`, and then its major review, once you have snapshotted it and made its full run.
In this step no round adds a subagent, because subagents arrive in `c2-review` and `c3-split`: a round changes or adds a skill, or makes another change the skills need, such as an allow rule (Kind `other`).
Your first round can start from the tutor as it ships, so the baseline is the output without your first change.
The major review covers all four jobs, and its previous step is `c0-baseline`, so compare with your baseline runs.
What it finds becomes the checklists of your reviewer subagents in `c2-review`, so be specific.
`reviews/README.md` says how to write each part.
You write your thoughts, ratings and feedback; Claude Code writes only the What changed part of each round.
Keep every heading as it is, because `p3 check` reads them, and add a round by copying the last one with its marker lines.

## Quick rounds

### Round 1

**Run:** 

**My thoughts:**

Overall I was impressed. I thought that the way the examples were presented was helpful for my learning. Additonally I think that the quizes that were scattered throughout were helpful to make sure I was still on the right track. I didn't love the brown color scheme that was chosen. I don't have a suggestion for what it should be either, we'll have to keep experimenting. I would add more mini quizzes throughout, additionally I would get rid of this brown.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md
- Why: You found the quizzes scattered through the lesson helpful and asked for more, so the teach skill's lesson guide now asks for a mini quiz after every section and about one per 500 words of explanation.

### Round 2

**Run:** 

**My thoughts:**

This run seemed to fix nothing. I still like the quizzes and the graphics conceptually. However, the brown color scheme is still here which I don't like. Additionally, on this run many graphics have text overflowing out of the sides and various small scaling things throwing them off. I think roung 1 performed better.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md
- Why: You saw figure text overflowing its boxes and scaling off, so the teach skill's lesson guide now gives a label-width rule (about 10 units per character at size 18, with padding), says to split or shorten long labels, and adds a figure-fit check to the closing list.

### Round 3

**Run:** 

**My thoughts:**

I think this run is a big improvement. There is a lot of rich information in addition to good looking graphics that are sized and scaled correctly. The single only thing I would want you to change is the color scheme to not have this boring brown overtone.


**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/lesson-template.html, tutor/.claude/skills/teach/references/LESSONS.md
- Why: You wanted the brown overtone gone, so the lesson template's light and dark palettes are now cool slate neutrals with a blue accent, and the lesson guide says to keep them.

### Round 4

**Run:** 

**My thoughts:**

I like the change to the new color scheme. I think the replies for the tutor are good, they fit my preferences. I don't have anything to specifically ask you to change here. I think its time to build the skill for the tutor.


**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/tutor/SKILL.md, tutor/CLAUDE.md
- Why: You said it was time to build the tutor skill, so chat replies now come from a skill of their own that follows your PREFERENCES.md, keeps quiz answers closed and never opens `keys/`, and `tutor/CLAUDE.md` sends chat messages to it.

### Round 5

**Run:** 

**My thoughts:**

I think the tutoring is good. I'm not noticing a difference between what is being produced now and last run. For the quizzes, I think it would be better if the answers varied more from one another, with the answers being deeper more full and complete. I think this would help them from sounding the exact same.


**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/quiz/SKILL.md, tutor/CLAUDE.md
- Why: You asked for quiz answers that vary more and are fuller and deeper, so quizzes now come from a skill of their own that writes each option as a one-or-two-sentence argument with its own shape and its own misconception, and `tutor/CLAUDE.md` sends quiz requests to it.

### Round 6

**Run:** 

**My thoughts:**

I like how both the quiz and the grade sound. I think we should begin to build the grader skill now.


**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/grade/SKILL.md, tutor/CLAUDE.md
- Why: You liked how the grading sounds and asked to build the grader skill, so grading now comes from a skill of its own that keeps the feedback in your direct, reasoned style, and `tutor/CLAUDE.md` sends grading to it.


## Major review

**Run:** bench/runs/c1-skills/20261117-194349-agent-architecture-m30-r1

**Live tries:**

Claude did a very good job in a live try. I was pleasantly suprised with how well Claude was able to remember my preferences and the choices we made during the skill development in order to create an effective learning environment for me. Generally it did everything I expected of it.

### Lesson

#### Technical correctness and facts

Rating: 5

As far as I am aware, every fact presented was fully correct. I have no notes for this section.

#### Pedagogy

Rating: 5

I believe that claude did as good of a job as could be asked of it for this section.

#### Alignment with the learning goal

Rating: 5

The content aligned perfectly with the learning goal.

#### Overall quality

Rating: 5

Overall the quality was excelent and looked great after the several iteratons of the skill.

### Quiz

#### Difficulty

Rating: 4

The quiz was very good if not a little inconsistent in the difficulty of the questions.


#### Coverage of the lesson's core

Rating: 5

The quiz completely covered the lesson's core.

#### Wording and possible misreadings

Rating: 5

I don't believe there was any possible misreadings from the quiz.


#### Writing quality

Rating: 5

The writing quality was great and on par with the lesson.

#### Alignment with the learning goal

Rating: 5

The quiz fully alligned with the learning goal.

### Feedback

#### Useful

Rating: 5

The feedback was great and would be legitimately helpful in a real scenario where I was attempting to study or learn something new.

#### Explains enough

Rating: 5

I think it explains a good amount. For me, this is smaller sentences that don't drift which matches the preferences I set at the beginning of this project.

#### Personalized to how I like things explained

Rating: 5

It does a good job matching my preferences and provided feeback how I would like.

### Tutor

#### Guardrails

Rating: 5

The guardrails worked as would be expected.

#### Personalization

Rating: 5

The tutor aligned very well with the skill iterations that we had as well as the preferences that I set.

### Compared with the previous step

In order to compare against the previous step I was able to compare using the command. In this I saw that for the most part my skills have become more expensive but they lead to more accurate results. The results show that the current iterations of the skills are not producing as many errors, as well as fewer issues like deadlinks across the tests. However from this I can also see that my skills are noticably more expensive so running them more often could lead to reaching my claude limit sooner. This is an important consideration that I will have to make when choosing to modify these skills further as I don't want them to increase in cost with diminishing returns.

### What the next step should fix

I think the next step should fix the difficulty inconsistencies within the quiz. Some questions in the quiz had vastly different difficulty levels which I think should be tuned so that every question in the quiz is around the same level.
