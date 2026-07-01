# Token saving Skill

## Purpose

Minimize the output tokens by preventing the agent to answer the user

## When to use

- Small tasks that do not require an answer from the agent
- Tasks that can be easily tested or just by looking at the changes you can tell if it was successful

## When NOT to use

- Do not use for planning. Planning needs feedback
- Large tasks that will result in many changes across multiple files

## Examples

Rename X variable or constant.
Add logs to some service.
Create a react component with Card styling that receives title and body props.

## Notes

- If the agent have suggestions or notes regarding the completed task it will prompt a question asking the user if they want to see them.
