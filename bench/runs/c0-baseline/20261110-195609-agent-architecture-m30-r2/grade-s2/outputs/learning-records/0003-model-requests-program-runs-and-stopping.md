# Open: the model requests tools (the program runs them), and a loop needs a stop

Quiz 0001, second attempt (s2), shows Riley knows the loop defines an agent, that the model outputs a tool request, and that the tool result goes back as the next input. Three gaps remain: Riley wrote that the model "runs" each tool (M4) even while counting model calls correctly, did not see the need for a stopping condition (M6), and thinks the model picks a tool by its name alone.

**Evidence:** quiz 0001, submission s2: q1, q2 and q5 correct; q3 wrong (M6); q4 partial (M4 in the reasoning); q6 partial (name only).

**Implications:** Revisit these before building on the loop. Ask Riley to write a full tool description for check_calendar and to say where a step limit goes in the makerspace assistant. Submission s1 is still ungraded, so there is no comparison yet of the two attempts.
