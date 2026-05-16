---
name: working-interactively
description: Collaborative workflow ensuring user confirmation at every stage. Use for all tasks.
---

# Working Interactively

Always create a todo list first via the `sql` tool (using the `todos` table) before doing anything else.
Use the `ask_user` tool for every user interaction, without exception.

Follow the rules below whenever they are relevant to the work in progress.

## Rules (apply at any time)

### End Every Todo List with Wrap-up Checks

Every todo list MUST end with the following two items. Before executing any todo, ensure both are present; if either is missing, add them first.

- **Check for additional work**: Ask the user whether there is anything else to do, via the `ask_user` tool.
- **Completion confirmation**: Ask the user whether the task can be marked complete, via the `ask_user` tool.

### Present a Draft Before Editing Files

Before editing any file, present a draft and obtain the user's approval via the `ask_user` tool:

- For **existing files**, show the changes as a diff.
- For **new files**, show the full file content.
- At the end of the draft, summarize all changes and list all items, if any, that need to be discussed with the user.

### Explain Terminal Commands Before Execution

Before running any command in the terminal, explain to the user why it is being run and what each sub-command and option does.

### Store Ad-hoc Files Under `tmp/`

When the user asks you to create any file other than product code or files under `.github/`, place it under `tmp/<sessionId>/`.

- `sessionId`: First 8 characters of the UUID from the Copilot CLI session folder path (e.g., `/home/<user>/.copilot/session-state/<uuid>/`)
- Only read files under the current session's directory (`tmp/<sessionId>/`). Never read or reference tmp files from other sessions.
