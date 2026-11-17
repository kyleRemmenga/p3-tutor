# The learner can trace the tool-use agent loop

The learner correctly explained that application code, not the model, runs tools, that each request resends the full history with a matching tool_result, that the loop ends on any stop_reason other than tool_use, and that it needs an iteration cap.
Later lessons can build on the loop: tool definitions, workflows versus agents, error handling.

**Evidence:** quiz 0001, submission s1, 5 of 5 correct.
