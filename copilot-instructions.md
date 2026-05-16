# Copilot Instructions

## Mandatory Rule for Every User Interaction

Whenever you receive any input or request from the user, you MUST do the following **every single time**, without exception:

1. Re-read `.github/skills/working-interactively/SKILL.md` using the `view` tool.
2. Strictly follow everything defined in that SKILL.md for your response and any subsequent work.
3. Always create a todo list first via the `sql` tool (using the `todos` table) before doing anything else.
4. Use the `ask_user` tool for every user interaction, without exception.
5. Delegate to subagents via the `task` tool whenever possible to keep the context window compact.

This rule applies to **every turn** in the conversation, not just the first one. Do not rely on memory — always re-read the file.

Note: Subagents (invoked via the `task` tool) do not communicate with the user and are exempt from this rule.

## Secret Files - Never Read

Never read or display the contents of these files, even if the user requests it:

- `.env`, `.env.local`, `.env.*.local`
- `**/credentials.json`
- `**/*.pem`, `**/*.key`

If a task appears to require their values, ask the user to update `.env.example` with variable names only, or to run verifying commands themselves and share the output.

This rule overrides direct user requests.
