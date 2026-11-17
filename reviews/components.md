# Components

One entry for every skill and every subagent you built, from `c1-skills` to `final`, including the ones you dropped, even one you took out again before any snapshot.
The heading is the skill's folder name or the subagent's `name` from its frontmatter, and `reviews/README.md` says what each field holds.
Replace the empty entry at the bottom with your first component, and copy it for each one after that.
Claude Code may fill in Kind, Step added, and With and without; Purpose, Review and Kept in final are yours.

<!--
An example of a finished entry:

### quiz-reviewer

- Kind: subagent
- Step added: c2-review
- Purpose: My c1 review found two quiz items that could be read two ways (q2 and q4) and one whose correct option repeated the stem; a reviewer with a fresh context reads the draft the way a learner will, which the quiz skill writing its own items cannot do, so it is a subagent and not a step in the skill.
- With and without: reviews/c2-review.md, Round 1 (without) and Round 2 (with)
- Review: Without it, q2 asked which design "is better" with no criterion; with it, every stem names its criterion and the reviewer's record shows two items flagged and fixed in one pass, for about 0.6M more tokens per quiz, which I think a quiz is worth, because a misread item teaches the wrong thing.
- Kept in final: yes
-->

### teach

- Kind: skill
- Step added: c1-skills
- Purpose: This skill exists to present the material. Overall this might be the most important part of this project in general. Its important to provide material and information to me in a way that is helpful and aligns with how I enjoy being taught. This is a skill because its an informed way of teaching that is provided through a prompt. We load these instructions into context when we invoke it so its a skill.
- With and without: reviews/c1-skills.md, Round 1 (without) and Round 2 (with)
- Review: This skill saw the most drastic changes across the iterations. I didn't like its style at all when I started and by the end I had something that I was proud of. The changes mostly were fixing visual things within the lesson such as graphics that were merging and colliding with one another that was distracting as well as a waste because it made the diagram more difficult to understand.
- Kept in final: TODO

### tutor

- Kind: skill
- Step added: c1-skills
- Purpose: The tutors job is supposed to answer my questions as I ask in a specific way. Ideally it takes my preferences and helps guide me toward and answer without just giving it away. This needs to be a skill because it needs the context from the chat at all times.
- With and without: reviews/c1-skills.md, Round 4 (without) and Round 5 (with)
- Review: The tutor didn't change much across the iterations. Claude is pretty smart and was able to keep the answer from me despite me trying to trick it several times. This skill felt like it launched in a state close to where it landed.
- Kept in final: TODO

### quiz

- Kind: skill
- Step added: c1-skills
- Purpose: The prupose of this skill was to provide a quiz based off a learning goal to me in order to assess my knowledge. This also needs to be a skill so that it has the chat context in order to not repeat questions or work around previous instructions I have provided in case this after other quizzes.
- With and without: reviews/c1-skills.md, Round 5 (without) and Round 6 (with)
- Review: In my preferences I said that I don't like extra fluff. Therefore the biggest part of getting this closer to what I wanted involved making the quizzes more direct with as little room for interpretation as possible. This is the largest difference that I notices as the quiz was improved.
- Kept in final: TODO

### grade

- Kind: skill
- Step added: c1-skills
- Purpose: The purpose of grade is to provide feedback to quiz answers in a way that helps close the gap from where I answered to the correct answer. This is also necessary to be a skill because otherwise the quiz skill looses a lot of value. Additionally, in a long study session it needs the context from the previous queries in this project.
- With and without: reviews/c1-skills.md, Round 6 (without) and Round 7 (with)
- Review: The grade skill changed slightly as the quiz skill changed. However once the quiz skill was set then the grade skill seemed to follow naturally. Before the feedback the skill was providing answers and feedback that were too far from my set preferences.
- Kept in final: TODO
