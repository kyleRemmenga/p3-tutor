# Open misconception: the model runs the tools itself

Quiz 0001 (s1) shows Riley believes the model opens the booking system and runs the tools itself (M4), so counts one model call for a three-tool request. Riley also thinks the model remembers earlier sessions on its own (M3). Riley does get the loop's shape, the need for a stopping condition, and that the model picks tools from descriptions.

**Evidence:** quiz 0001, submission s1, items q2, q4 and q6 (q1, q3 correct; q5 partial, missing the why).

**Implications:** Before building on context and memory, fix the split: the model writes text (a tool request or an answer) and the program runs tools and feeds results back, one model call per step. Teach memory as something the program puts into the input. Check whether s2, taken four days later, shows this fixed.
