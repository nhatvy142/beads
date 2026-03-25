---
description: Enhance any prompt to world-class quality before execution
allowed-tools: Read, AskUserQuestion
argument-hint: <your rough prompt or task description>
---

You are enhancing a prompt to world-class quality. The user's raw input is:

> $ARGUMENTS

## Phase 1 — Intake Form (MANDATORY)

Before enhancing, you MUST gather context by asking the user questions using the AskUserQuestion tool. Ask up to 4 questions at a time to understand what they need. Tailor the questions based on what's missing from their raw input.

### Round 1: Core Understanding

Use AskUserQuestion to ask about:

1. **Objective** — "What is the primary goal of this task?" with options like:
   - Build a new feature
   - Fix a bug
   - Refactor / improve existing code
   - Write tests or documentation

2. **Scope** — "How large is the scope of this change?" with options like:
   - Single file / function
   - Multiple files in one package
   - Cross-cutting across multiple packages
   - Architecture / design level

3. **Quality priority** — "Which quality dimension matters most?" with options like:
   - Correctness (no bugs, handles edge cases)
   - Performance (speed, memory efficiency)
   - Maintainability (clean, readable, extensible)
   - Robustness (error handling, resilience)

4. **Constraints** — "Are there specific constraints to follow?" with options like:
   - Must match existing code patterns
   - Must maintain backward compatibility
   - Has specific performance requirements
   - No special constraints

### Round 2: Deeper Context (if needed)

Based on answers from Round 1, ask follow-up questions to fill remaining gaps. For example:

- If scope is large: "Which packages or files are involved?"
- If it's a bug fix: "Can you describe the current vs. expected behavior?"
- If there are constraints: "What specific patterns or APIs must be used?"
- If it's a new feature: "Who or what will consume this feature?"

You may skip Round 2 if the raw input + Round 1 answers provide enough context.

## Phase 2 — Codebase Research

After gathering user input, read relevant files in the codebase to understand:
- Existing patterns and conventions
- Related code that the prompt should reference
- Test patterns used in the project

## Phase 3 — Compose Enhanced Prompt

Using ALL gathered context (raw input + form answers + codebase research), apply the 6-step enhancement framework:

1. **Clarify Intent** — Synthesize the objective from user answers
2. **Define Quality Criteria** — Prioritize based on user's quality preference
3. **Add Constraints and Context** — Incorporate user-specified constraints + codebase conventions
4. **Structure the Deliverable** — Break into ordered steps with checkpoints
5. **Add Examples and References** — Include relevant code references from the codebase
6. **Compose** — Assemble into the final template:

```
## Objective
[Single precise statement]

## Context
[Background, constraints, assumptions — informed by user answers]

## Requirements
[Numbered, testable requirements]

## Quality Bar
[Prioritized quality criteria based on user preference]

## Approach
[Ordered steps]

## Verification
[How to confirm quality]

## Anti-patterns
[What to avoid]
```

## Phase 4 — Present and Confirm

Present the enhanced prompt and ask the user:
- **Execute now** — Proceed with the enhanced prompt immediately
- **Refine further** — Adjust specific sections
- **Copy only** — Just keep the enhanced prompt for later use
