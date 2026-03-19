---
description: Enhance any prompt to world-class quality before execution
allowed-tools: Read
argument-hint: <your rough prompt or task description>
---

Enhance the following prompt/task to world-class quality using the 6-step framework.

User's prompt to enhance: $ARGUMENTS

Apply the enhancement framework from the enhance-prompt skill:

1. **Clarify Intent** — What is the core objective? What does "done" look like? What makes this exceptional?

2. **Define Quality Criteria** — Score across: Correctness, Completeness, Clarity, Elegance, Robustness, Polish

3. **Add Constraints and Context** — Make implicit assumptions explicit. Define scope boundaries, technical constraints, audience, standards, and anti-patterns. Read relevant files in the codebase to understand existing patterns and conventions.

4. **Structure the Deliverable** — Break into ordered steps with checkpoints and verification.

5. **Add Examples and References** — Include positive/negative examples and reference implementations from the codebase.

6. **Compose the Enhanced Prompt** — Assemble using this template:

```
## Objective
[Single precise statement]

## Context
[Background, constraints, assumptions]

## Requirements
[Numbered, testable requirements]

## Quality Bar
[What makes this world-class]

## Approach
[Ordered steps]

## Verification
[How to confirm quality]

## Anti-patterns
[What to avoid]
```

Present the enhanced prompt and ask if the user wants to refine it or proceed with execution.
