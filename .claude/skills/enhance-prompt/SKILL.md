---
name: enhance-prompt
description: >
  Enhance any prompt or task description to world-class quality. Asks clarifying
  questions to understand context, audience, and goals, then produces a structured
  prompt that gets exceptional results from any AI.
allowed-tools: "Read, AskUserQuestion"
version: "2.0.0"
author: "nhatvy142"
---

# Enhance Prompt — World-Class Quality for Any AI Task

Transform vague or rough ideas into precise, structured prompts that produce
exceptional output. Works for any task — writing, analysis, creative work,
technical projects, and more.

## When to Use

- Before starting any significant task
- When instructions are vague or ambiguous
- When you want to elevate output from "good enough" to "world-class"
- When a task has failed to produce satisfactory results on previous attempts
- When preparing prompts to use with any AI tool

## Usage

```
/enhance-prompt <your rough prompt or idea>
```

## Interactive Flow

When invoked, this skill follows a conversation-driven approach:

### Step 1 — Gather Context (Interactive Form)

Ask the user clarifying questions using AskUserQuestion to understand:

| Question | Why It Matters |
|----------|---------------|
| **Task type** (writing, analysis, creative, technical) | Determines the enhancement strategy |
| **Audience** (personal, professional, public, expert) | Shapes tone, depth, and assumptions |
| **Tone and style** (formal, friendly, concise, creative) | Sets the voice of the output |
| **Output format** (paragraphs, structured, bullets, steps) | Defines the deliverable shape |

Follow up with task-specific questions based on initial answers:
- **Writing**: key message, length, references
- **Analysis**: core question, data sources, recommendations vs. findings
- **Creative**: themes, inspirations, boundaries
- **Technical**: tools/platform, current vs. desired state, constraints

### Step 2 — Enhance

Apply the 6-step enhancement framework using all gathered context:

1. **Clarify Intent** — Distill the objective into one precise statement
2. **Define Success Criteria** — What makes this excellent, not just adequate?
3. **Add Context and Constraints** — Audience, tone, format, scope, boundaries
4. **Structure the Ask** — Break into clear steps if applicable
5. **Add Guidance** — Positive examples and anti-patterns
6. **Compose** — Assemble into a structured enhanced prompt

### Step 3 — Present and Confirm

Present the enhanced prompt and offer:
- **Execute now** — Run the enhanced prompt immediately
- **Refine further** — Adjust specific sections
- **Copy only** — Keep the prompt for use elsewhere

## Enhanced Prompt Template

```
## Objective
[Single precise statement of what the AI should produce]

## Context
[Background: who it's for, why it matters, relevant details]

## Requirements
[Numbered list of specific, clear requirements]

## Tone and Format
[Style, voice, length, and format expectations]

## Quality Bar
[What makes this output excellent — specific success criteria]

## Steps (if applicable)
[Ordered approach to follow]

## Examples and Guidance
[What good output looks like; what to avoid]
```

## Guiding Principles

- **Understand before building** — The intake form prevents wasted effort
- **Be specific** — Vague prompts get vague results
- **Know your audience** — A prompt for experts differs from one for beginners
- **Define "done"** — Clear success criteria prevent endless iteration
- **Show, don't tell** — Examples are worth more than descriptions
- **Less is more** — A focused prompt beats a bloated one

## Examples

**Before (rough prompt):**
> "Write me a marketing email"

**After (enhanced prompt):**
> ## Objective
> Write a product launch email announcing our new AI scheduling assistant
> to existing customers.
>
> ## Context
> We're a B2B SaaS company. The audience is current users (mostly office managers
> and executive assistants). They're already familiar with our calendar product.
> This is the first AI feature we've launched.
>
> ## Requirements
> 1. Subject line that achieves >30% open rate (A/B test two options)
> 2. Lead with the user benefit, not the feature
> 3. Include one clear CTA — "Try it free for 14 days"
> 4. Keep body under 150 words
> 5. Include a brief "how it works" section (3 bullets max)
>
> ## Tone and Format
> Conversational but professional. Excited without being salesy.
> Short paragraphs, scannable layout.
>
> ## Quality Bar
> - Would pass a spam filter
> - A busy person can get the value prop in under 10 seconds
> - CTA is impossible to miss
>
> ## Examples and Guidance
> - DO: "Your calendar just got smarter" (benefit-first)
> - AVOID: "Introducing our revolutionary AI-powered scheduling paradigm" (jargon)
> - AVOID: Multiple CTAs competing for attention
