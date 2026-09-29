---
name: prompt-engineering
description: "Design, improve, test, and evaluate prompts for text, image, video, coding, agents, and structured outputs."
---
# Prompt Engineering Skill

## Purpose
Create prompts that are precise, testable, reusable, and resistant to ambiguity.

## Prompt design process
1. Define the task and desired outcome.
2. Define input variables and assumptions.
3. Set role only when it improves task performance.
4. Specify output format exactly.
5. Add constraints, quality rules, and failure conditions.
6. Provide examples only when they clarify the intended behavior.
7. Separate instructions from user-provided data.
8. Add validation or self-check steps when useful.

## Reliability rules
- Avoid contradictory instructions.
- Avoid vague words such as "best" without measurable criteria.
- Do not rely on hidden reasoning requests. Ask for concise decisions, checks, or explanations instead.
- Keep reusable prompts parameterized.
- Prefer deterministic structure for machine-consumed output.

## Testing
Evaluate prompts against:
- instruction adherence
- factuality
- formatting reliability
- edge cases
- ambiguity
- prompt injection resistance
- unnecessary verbosity

## Deliverables
When useful, provide a production prompt, variables, expected output schema, test cases, and failure cases.
