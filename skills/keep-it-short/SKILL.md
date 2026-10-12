---
name: keep-it-short
description: >-
  Makes human-facing agent conversation concise without omitting necessary information.
  Use only when the user explicitly requests this skill or project instructions
  (such as AGENTS.md) explicitly opt in for the current conversational response.
  Applies to answers, explanations, discussions, questions, and progress updates;
  never to code, documentation, reports, plans, handoffs, or other work products.
---

# Keep It Short

**Keep it short, not incomplete.** Communicate what the human needs to know at the depth the situation requires, with as little unnecessary language as possible.

## Scope

This skill changes **only the presentation of human-facing conversation**: answers, technical explanations, research summaries in chat, comparisons, recommendations, brainstorming, clarifying questions, and progress or completion messages.

Do **not** apply brevity requirements to work products, including:

- Code, tests, configurations, generated content, and their correctness.
- Documentation, reports, proposals, specifications, implementation plans, and handoffs.
- Research depth, tool use, investigation, verification, or internal decision-making.
- Any requested artifact or deliverable, even when it is displayed in chat.

A short message *accompanying* an artifact may use this skill; the artifact itself must satisfy its own requirements. If the human explicitly requests a shorter deliverable, treat that as a separate task requirement, not an effect of this skill.

## How to respond

1. **Lead with the answer.** State the result, recommendation, or next meaningful decision before background information.
2. **Give enough reasoning.** Explain the decisive reasons and trade-offs, not every intermediate thought or every alternative investigated.
3. **Preserve decision-critical details.** Include relevant facts, numbers, constraints, dependencies, assumptions, uncertainty, caveats, meaningful risks, blockers, and required actions. Never conceal bad news or weaken a warning for brevity.
4. **Match the situation.** A straightforward question may need one sentence. A complex, consequential, or unfamiliar topic may require substantial explanation. Do not enforce word, paragraph, or bullet limits.
5. **Remove redundancy.** Skip restating the prompt, obvious context, repetitive conclusions, boilerplate introductions, and unnecessary closing summaries.
6. **Use structure selectively.** Prefer plain language and short paragraphs. Use bullets or tables only when they improve comprehension; avoid decorative headings and elaborate formatting.
7. **Support collaboration.** In brainstorming, explore meaningful alternatives and challenge assumptions, but focus each response on moving the discussion forward. Ask only questions that matter to the next step.
8. **Expand when asked.** If the user asks for detail, examples, evidence, walkthroughs, or an exhaustive answer, provide them fully. The user's requested depth takes precedence.

## Research and technical discussion

Investigate thoroughly before answering. Distinguish established findings from estimates or uncertain conclusions. Cite or point to supporting evidence when needed. Present the conclusion and strongest supporting facts first; keep less important detail available for follow-up.

For comparisons, include the criteria that actually change the choice. For recommendations, state the choice, why it fits, and the most important downside or condition. Do not make a recommendation appear more certain or universally applicable than the evidence warrants.

For technical explanations, retain the details needed to understand, verify, or act on the answer. Never shorten a procedure by omitting required steps, prerequisites, commands, failure modes, or safety checks.

## Progress and completion messages

Keep routine status updates brief and substantive. Mention meaningful progress, blockers, or decisions rather than narrating every action. On completion, clearly state what was done and any important limitations; do not reproduce the entire deliverable in the message.

## Final check before sending

- Does the first part answer the actual question?
- Can any sentence be removed without losing useful meaning?
- Are important uncertainty, risks, exceptions, prerequisites, and next actions still visible?
- Is the response sufficiently complete that the human can act without asking for information that should already have been included?
- Have all work products remained unaffected?

**When concision conflicts with clarity, completeness, or safety, choose clarity, completeness, and safety.**
