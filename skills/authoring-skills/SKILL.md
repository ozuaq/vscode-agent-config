---
name: authoring-skills
description: Create and improve SKILL.md files following best practices. Use when creating, reviewing, or refining agent skills.
---

# Authoring Skills

Create well-structured SKILL.md files that are concise, discoverable, and effective.

- **Write in English** — All content must be in English for broad compatibility
- **Only add what the agent doesn't already know** — Challenge each line: "Does this justify its token cost?"
- **Match freedom to fragility** — Strict steps for fragile operations, general guidance for flexible tasks
- **Progressive disclosure** — Keep SKILL.md under 500 lines; split into reference files when needed

## Frontmatter Guidelines

- `name`: must match the folder name; lowercase with hyphens; max 64 chars; gerund form preferred (e.g. `processing-pdfs`)
- `description`: max 1024 chars; written in third person (e.g. "Processes files", not "I help you" or "You can use this"); include WHAT the skill does AND WHEN to use it; use trigger keywords for discovery; avoid tool names and implementation details

## Body Guidelines

- Keep under 500 lines; move overflow to reference files (one level deep)
- Use consistent terminology throughout
- Avoid time-sensitive information
- For workflows, write clear sequential steps with feedback loops
