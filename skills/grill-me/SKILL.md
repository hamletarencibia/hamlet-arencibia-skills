---
name: grill-me
description: Stress-test a plan, proposal, design, or architecture through a dependency-ordered interview. Use when the user asks to be grilled, challenged, interviewed, or to poke holes in their thinking; not for a routine implementation or code review unless they request this interview style.
---

# Grill Me

## Approach

1. Extract the proposal, constraints, success criteria, stated assumptions, and open decisions from the conversation.
2. Inspect relevant local files or supplied material before asking questions whose answers are discoverable. Do not infer unstated product decisions merely because a technical option is visible.
3. Identify the decision branches that could materially change the outcome. Order them by dependency and impact: goals and constraints first, then architecture or product choices, then data, risk, operations, and validation details.
4. Ask one highest-priority unresolved question at a time. Explain briefly why it matters. When the context supports a clear choice, include a concise recommendation and its trade-off; otherwise, present the relevant options without inventing a preferred answer.
5. Incorporate each answer before choosing the next question. Skip branches that no longer affect a meaningful decision, and do not revisit a resolved choice without new evidence.
6. Stop when the remaining uncertainty is immaterial, explicitly accepted by the user, or can be handled safely during execution. Summarize the agreed direction, key assumptions, outstanding risks, and any next decision or action.

## Boundaries

- Keep the exchange constructive: test assumptions and consequences, not the user.
- Adapt the depth to the stakes. Do not manufacture edge cases simply to prolong the interview.
- Do not implement, change files, or make external commitments unless the user asks for that work separately.
