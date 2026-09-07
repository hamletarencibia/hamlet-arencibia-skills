# Grill Me

`grill-me` is a decision-focused interview skill. It stress-tests a plan, proposal, product idea, or technical design by uncovering the assumptions and choices that could materially affect the result.

It works through one question at a time, in dependency order. Before asking something the user may already have supplied, the agent checks the conversation and relevant local material. Each question explains why the answer matters and includes a recommendation only when the available context genuinely supports one.

## When to use it

Use this skill when you want an assistant to challenge your thinking before you commit to a direction. Typical requests include:

- "Grill my launch plan for a new pricing model."
- "Interview me about this API design and find the risky assumptions."
- "Poke holes in this migration proposal before we start building."
- "Use $grill-me to pressure-test this architecture."

It is not intended for a normal implementation task or a conventional code review unless you specifically want the interactive interview format.

## How the session works

1. Share the plan, design, or proposal, including any constraints, goals, and supporting files or links that matter.
2. Ask the assistant to grill, challenge, interview, or pressure-test it. You may invoke it explicitly as `$grill-me`.
3. Answer one question at a time. The next question adapts to your answer, so important dependencies are resolved before lower-impact details.
4. At the end, you receive a concise summary of the agreed direction, assumptions, risks, and the next decision or action.

## Example

> Use $grill-me to stress-test my plan to replace our in-house authentication with a hosted provider. We need to ship in six weeks, support enterprise SSO, and avoid downtime for existing users.

The skill will begin with the highest-impact unresolved choice—such as the migration and rollback strategy—rather than jumping directly into lower-level configuration questions.

## Scope

The skill guides a constructive conversation; it does not modify files, implement the plan, or make external commitments by itself. Request those follow-on actions separately when you are ready.
