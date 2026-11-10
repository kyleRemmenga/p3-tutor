# Loop structure holds from memory; stopping conditions and tool descriptions do not yet

On quiz 0001, taken from memory four days after the lesson, Riley correctly identified what makes an agent, what the model outputs when it calls a tool, and why a tool result goes back into the next input.
Three gaps remain: Riley believes a stuck agent will eventually succeed without a stopping condition (M6), says the model "runs" the tools although the count of model calls was right (M4), and thinks the model picks a tool from its name alone rather than its full description.

**Evidence:** quiz 0001, submission s2, items q3 (wrong, M6), q4 (partial, M4 in the reasoning), q6 (partial).

**Implications:** Revisit stopping conditions and the program/model split before building on the loop. Tool descriptions should come early, because the mission asks Riley to write one for the assistant's tools.
