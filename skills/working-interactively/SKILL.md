---
name: working-interactively
description: "Collaborative workflow ensuring user confirmation at every stage. Use for all tasks."
---

# Working Interactively

Ensure user confirmation and approval at every stage of work.

Every interaction with the user MUST go through `vscode_askQuestions`. Never proceed without user input between steps.

## Workflow

These steps represent the general flow of a task. Steps 1 and 2 typically happen in order. Other rules apply whenever relevant.

### 1. Task Planning

Create a task list with `manage_todo_list`. Every task list MUST include these two steps at the end:

- **Check for additional work**: Ask "Is there anything else to do?" via `vscode_askQuestions`
- **Completion confirmation**: Ask "Can we mark this as complete?" via `vscode_askQuestions`

### 2. Step Execution

Progress through each step, updating `manage_todo_list` from in-progress → completed.

## Rules (apply at any time)

### Code Block Backup

VS Code Chat UI may fail to render code blocks correctly. Whenever a chat message includes code blocks, always save a backup copy to `./tmp/<sessionId>/<chatNo>/<descriptive-name>.md`.

- Applies to **all code block outputs**: explanations, proposals, draft reviews, etc.
- `sessionId`: First 8 characters of the UUID from `{{VSCODE_TARGET_SESSION_LOG}}` path
- `chatNo`: Sequential number within the session (starting from 1)
- `descriptive-name`: A name reflecting the content (e.g., `auth-changes.md`)
- Save automatically without user confirmation

### Draft Review Before File Editing

Before editing any file:

1. Present a draft of the changes to the user, clearly separated into:
   - **Plan Overview**: Confirmed direction and scope of changes
   - **Undecided Items**: Open questions or items requiring user input via `vscode_askQuestions`
   - Present all code changes in **diff format**
2. Ask via `vscode_askQuestions`: "Shall I proceed with this draft?"
3. Do NOT edit until all "Undecided Items" are resolved and approval is given

### Terminal Command Explanation

Before running any command in the terminal:

1. Save a detailed explanation to `./tmp/<sessionId>/<chatNo>/<descriptive-name>.md` containing:
   - **Command**: The full command being executed
   - **Purpose**: What the command does and why it's being run
   - **Breakdown**: Each sub-command and option with a detailed explanation
2. Then execute the command in the terminal
