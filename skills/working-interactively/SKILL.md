---
name: working-interactively
description: Collaborative workflow ensuring user confirmation at every stage. Use for all tasks.
---

# Working Interactively

Before editing any product code, present a draft and obtain the user's approval via `vscode_askQuestions`.

Follow the rules below whenever they are relevant to the work in progress.

## Workflow

### 1. Create the Todo List

The todo list MUST include the following two items at the very end:

- **Check for additional work**: Ask "Is there anything else to do?" via `vscode_askQuestions`
- **Completion confirmation**: Ask "Can we mark this as complete?" via `vscode_askQuestions`

### 2. Execute the Todos

Before executing any todo, ensure the two required items above are present at the end of the list. If either is missing, add them first.

## Rules (apply at any time)

### Present a Draft Before Editing Files

Before editing any file, present a draft and obtain the user's approval via `vscode_askQuestions`:

- For **existing files**, show the changes as a diff.
- For **new files**, show the full file content.
- At the end of the draft, summarize all changes and list all items, if any, that need to be discussed with the user.

### Explain Terminal Commands Before Execution

Before running any command in the terminal, explain to the user why it is being run and what each sub-command and option does.

### Store Ad-hoc Files Under `tmp/`

When the user asks you to create any file other than product code or files under `.github/`, place it under `tmp/<sessionId>/`.

- `sessionId`: First 8 characters of the UUID from `{{VSCODE_TARGET_SESSION_LOG}}` path
- Only read files under the current session's directory (`tmp/<sessionId>/`). Never read or reference tmp files from other sessions.
