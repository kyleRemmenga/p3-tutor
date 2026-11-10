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

**Run:** TODO

**My thoughts:**

Overall I was impressed. I thought that the way the examples were presented was helpful for my learning. Additonally I think that the quizes that were scattered throughout were helpful to make sure I was still on the right track. I didn't love the brown color scheme that was chosen. I don't have a suggestion for what it should be either, we'll have to keep experimenting. I would add more mini quizzes throughout, additionally I would get rid of this brown.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md
- Why: You found the quizzes scattered through the lesson helpful and asked for more, so the teach skill's lesson guide now asks for a mini quiz after every section and about one per 500 words of explanation.

### Round 2

**Run:** TODO

**My thoughts:**

This run seemed to fix nothing. I still like the quizzes and the graphics conceptually. However, the brown color scheme is still here which I don't like. Additionally, on this run many graphics have text overflowing out of the sides and various small scaling things throwing them off. I think roung 1 performed better.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md
- Why: You saw figure text overflowing its boxes and scaling off, so the teach skill's lesson guide now gives a label-width rule (about 10 units per character at size 18, with padding), says to split or shorten long labels, and adds a figure-fit check to the closing list.

## Major review

**Run:** bench/runs/c1-skills/TODO

**Live tries:**

TODO

### Lesson

#### Technical correctness and facts

Rating: TODO

TODO

#### Pedagogy

Rating: TODO

TODO

#### Alignment with the learning goal

Rating: TODO

TODO

#### Overall quality

Rating: TODO

TODO

### Quiz

#### Difficulty

Rating: TODO

TODO

#### Coverage of the lesson's core

Rating: TODO

TODO

#### Wording and possible misreadings

Rating: TODO

TODO

#### Writing quality

Rating: TODO

TODO

#### Alignment with the learning goal

Rating: TODO

TODO

### Feedback

#### Useful

Rating: TODO

TODO

#### Explains enough

Rating: TODO

TODO

#### Personalized to how I like things explained

Rating: TODO

TODO

### Tutor

#### Guardrails

Rating: TODO

TODO

#### Personalization

Rating: TODO

TODO

### Compared with the previous step

TODO

### What the next step should fix

TODO
