# Keep It Short

`keep-it-short` makes human-facing agent conversation concise without omitting information needed to understand, decide, or act. It leads with the answer, removes repetition, and preserves important reasoning, constraints, uncertainty, and next steps.

## When to use it

Use this skill for conversational responses, including explanations, research discussions, comparisons, recommendations, brainstorming, clarifying questions, and progress or completion messages.

The skill requires explicit opt-in: ask for it directly or enable it through project instructions such as `AGENTS.md`. It does not impose fixed word limits, and requests for more detail take precedence.

## How to use it

For a single conversation, invoke the skill explicitly:

> Use $keep-it-short for our discussion of these options. Include the trade-offs that affect the decision.

For ongoing use in a project, add this instruction to `AGENTS.md`:

```markdown
## Human-AI Communication

Use the `keep-it-short` skill for conversational
responses, including explanations, research
discussions, recommendations, and brainstorming.

Do not apply it to generated work products.
```

## Scope

The skill changes how the agent communicates with you. It does not reduce the depth of research, investigation, verification, or internal decision-making.

Generated work products—including code, tests, documentation, reports, proposals, specifications, implementation plans, and handoffs—must satisfy their own requirements. This applies even when a deliverable appears in chat. A brief message accompanying a deliverable may use the skill.

Clarity, completeness, and safety take precedence over concision. See [SKILL.md](SKILL.md) for the full instructions.
