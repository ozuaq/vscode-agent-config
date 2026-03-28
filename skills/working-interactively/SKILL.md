---
name: working-interactively
description: "Collaborative workflow ensuring user confirmation at every stage. Use for all tasks."
---

# Working Interactively

Ensure user confirmation and approval at every stage of work.

## Workflow

### 1. Task Planning

Create a task list with `manage_todo_list`. Every task list MUST include these two steps at the end:

- **Check for additional work**: Ask "Is there anything else to do?" via `vscode_askQuestions`
- **Completion confirmation**: Ask "Can we mark this as complete?" via `vscode_askQuestions`

### 2. Step Execution

Progress through each step, updating `manage_todo_list` from in-progress → completed.

### 3. Draft Review Before File Editing

Before editing any file:

1. Present a draft of the changes to the user
2. Clearly separate **"Decided Items"** and **"Under Discussion"** in the draft
   - **Decided Items**: Content confirmed from requirements
   - **Under Discussion**: Items the user raised via `vscode_askQuestions`
3. Ask via `vscode_askQuestions`: "Shall I proceed with this draft?"
4. Do NOT edit until all "Under Discussion" items are resolved and approval is given
