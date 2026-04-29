---
name: validating-frontend
description: Lints, builds, and formats frontend code. Use after editing frontend code.
---

# Validating Frontend

## Workflow

### 1. Lint

```
npm run lint -- --fix
```

- Fix remaining errors manually, then re-run until clean

### 2. Build

```
npm run build
```

- If build fails, fix the root cause
- After fixing, go back to step 1 (fixes may introduce new lint issues)
- Repeat until build succeeds

### 3. Format

```
npm run format
```

- Run once after lint and build are clean
- No need to re-lint or re-build after formatting
