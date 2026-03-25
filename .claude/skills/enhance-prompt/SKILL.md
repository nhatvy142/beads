---
name: enhance-prompt
description: >
  Enhance any prompt or task description to world-class quality. Analyzes intent,
  adds precision, structures for clarity, and ensures Claude delivers exceptional results.
allowed-tools: "Read, AskUserQuestion"
version: "1.0.0"
author: "nhatvy142"
---

# Enhance Prompt — World-Class Quality Delivery

Transform vague or rough instructions into precise, structured prompts that produce
exceptional output. Use this skill whenever you want Claude to deliver at the highest
quality level.

## When to Use

- Before starting any significant task
- When instructions are vague or ambiguous
- When you want to elevate output from "good enough" to "world-class"
- When a task has failed to produce satisfactory results on previous attempts

## Usage

```
/enhance-prompt <your rough prompt or task description>
```

## Enhancement Framework

When this skill is invoked, apply the following 6-step enhancement process:

### Step 1 — Clarify Intent

Identify the **core objective**. Ask:
- What is the user actually trying to achieve?
- What does "done" look like?
- What would make this output exceptional vs. merely adequate?

Rewrite the goal as a single, precise statement.

### Step 2 — Define Quality Criteria

Establish explicit success metrics for world-class delivery:

| Dimension | Question |
|-----------|----------|
| **Correctness** | Is it factually/technically accurate? |
| **Completeness** | Does it cover all edge cases and requirements? |
| **Clarity** | Is it easy to understand and act on? |
| **Elegance** | Is the solution clean, minimal, and well-structured? |
| **Robustness** | Does it handle failures, edge cases, and future changes? |
| **Polish** | Are naming, formatting, and conventions consistent? |

### Step 3 — Add Constraints and Context

Make implicit assumptions explicit:
- **Scope boundaries**: What is IN scope vs. OUT of scope
- **Technical constraints**: Language, framework, style, performance requirements
- **Audience**: Who will consume this output?
- **Standards**: What coding standards, design patterns, or conventions apply?
- **Anti-patterns**: What should be explicitly avoided?

### Step 4 — Structure the Deliverable

Break the work into clear, ordered steps:
1. Define the sequence of actions
2. Specify intermediate checkpoints
3. Include verification steps (tests, reviews, validations)
4. Define the final deliverable format

### Step 5 — Add Examples and References

Where applicable, include:
- **Positive examples**: "Output should look like THIS"
- **Negative examples**: "Do NOT do THIS"
- **Reference implementations**: Point to existing code/patterns in the codebase
- **Prior art**: Link to relevant docs or standards

### Step 6 — Compose the Enhanced Prompt

Assemble the final enhanced prompt using this template:

```
## Objective
[Single precise statement of what needs to be done]

## Context
[Relevant background, constraints, and assumptions]

## Requirements
[Numbered list of specific, testable requirements]

## Quality Bar
[What makes this "world-class" — specific quality criteria]

## Approach
[Ordered steps to complete the work]

## Verification
[How to confirm the work meets the quality bar]

## Anti-patterns
[What to explicitly avoid]
```

## Output

When invoked, this skill follows an interactive flow:

1. **Read the user's rough prompt/task**
2. **Ask clarifying questions** using AskUserQuestion to gather missing context:
   - Objective and goal type (new feature, bug fix, refactor, etc.)
   - Scope of the change (single file, multi-package, architectural)
   - Quality priority (correctness, performance, maintainability, robustness)
   - Specific constraints (existing patterns, backward compat, performance reqs)
   - Follow-up questions based on initial answers (if needed)
3. **Research the codebase** — Read relevant files to understand patterns and conventions
4. **Apply the 6-step enhancement framework** using all gathered context
5. **Present the enhanced prompt** in the structured template
6. **Ask the user** if they want to execute, refine, or copy the enhanced prompt

## World-Class Delivery Principles

These principles guide every enhanced prompt:

- **Measure twice, cut once** — Invest in understanding before building
- **No half-measures** — Every detail matters; don't cut corners on edge cases
- **Show, don't tell** — Working code > descriptions of code
- **Leave it better** — The codebase should be cleaner after your change
- **Test the boundaries** — Verify behavior at limits, not just the happy path
- **Name things well** — Clear naming eliminates the need for comments
- **Minimize surprise** — Follow established patterns and conventions in the codebase

## Example

**Before (rough prompt):**
> "Add error handling to the API"

**After (enhanced prompt):**
> ## Objective
> Add comprehensive error handling to all public API endpoints in `internal/rpc/`
> that currently return raw errors to callers.
>
> ## Context
> The RPC layer uses Unix domain sockets. Callers are AI agents that need
> structured error responses to make decisions. Raw Go errors are not actionable.
>
> ## Requirements
> 1. All public RPC methods return structured error responses with error codes
> 2. Error codes follow a consistent enum (NOT_FOUND, INVALID_INPUT, INTERNAL, etc.)
> 3. Internal errors are logged server-side but not leaked to callers
> 4. Input validation errors include the specific field that failed
> 5. Existing tests continue to pass
>
> ## Quality Bar
> - Zero raw `error` returns from public methods
> - Every error path has a test
> - Error messages are actionable (tell caller what to fix)
>
> ## Verification
> - `go test ./internal/rpc/...` passes
> - Manual test: send malformed request, verify structured error response
>
> ## Anti-patterns
> - Don't wrap errors multiple times (no `fmt.Errorf("failed: %w", err)` chains)
> - Don't catch-all with a single generic error code
> - Don't add error handling to internal/private functions (only public API boundary)
