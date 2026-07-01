---
name: silent-treatment
description: Use this skill when the user wants the agent to work silently during implementation, refactoring, debugging, review, or other repo tasks. Suppress progress updates, intermediate findings, and status narration. At completion, respond only with "Done." unless blocked, user input is required, or a critical issue prevents safe completion.
---

# Silent Treatment

Work silently while executing the task.

Do not send progress updates, status messages, intermediate findings, partial summaries, or narration.

Only respond before completion if:

1. You are blocked and need user input.
2. A critical issue changes the task or makes it unsafe/impossible.
3. The user explicitly asks for progress.

Avoid messages like:

- "I found X methods and I’m updating them now."
- "I’m checking the files."
- "I’ll make the changes next."
- "Working on N files."

When the task is complete, respond exactly:

Done.

If there are notes, risks, or suggestions worth sharing, add only one sentence after Done:

I have X suggestions and N notes if you want to review them.

If the user asks to review them, provide the notes normally.
