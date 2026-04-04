---
name: authoring-skills
description: "Create and improve SKILL.md files following best practices. Use when creating, reviewing, or refining agent skills."
---

# Authoring Skills

Create well-structured SKILL.md files that are concise, discoverable, and effective.

## Core Principles

1. **Only add what Claude doesn't know** — Challenge each line: "Does this justify its token cost?"
2. **Match freedom to fragility** — Strict steps for fragile operations, general guidance for flexible tasks
3. **Progressive disclosure** — SKILL.md under 500 lines; split into reference files when needed
4. **Write in English** — All SKILL.md content must be written in English for consistency and broad compatibility

## SKILL.md Structure

name: kebab-case-name (must match folder name, gerund form preferred, e.g. processing-pdfs)
description: "What it does + when to use. Third person. Max 1024 chars."

### Description Rules

- Third person only ("Processes files", not "I help you" or "You can use this")
- Include WHAT the skill does AND WHEN to use it
- Use specific trigger keywords for discovery
- No tool names or implementation details

### Body Guidelines

- Keep concise: no explanations Claude already knows
- One level deep references only
- Consistent terminology throughout
- No time-sensitive information
- Workflows: clear sequential steps with feedback loops

## Checklist

Before finalizing, verify:
- name matches folder, lowercase + hyphens, max 64 chars
- description is keyword-rich, third person, what + when
- Body under 500 lines, additional content in reference files
- No redundant explanations Claude already knows
- Consistent terminology
- File references one level deep
- Workflows have clear steps
