---
name: code-standards
description: Apply team code style, architecture, and git conventions. Use when writing, reviewing, refactoring, or committing code in any project.
tools: Read, Edit, Write, Bash, Glob, Grep
---

# Team Code Standards

Apply these rules to every piece of code you write or modify.

## General Style

- Keep solutions minimal and correct — no over-engineering
- YAGNI: don't add features, abstractions, or error handling for scenarios that don't exist yet
- Three similar lines is better than a premature abstraction
- Prefer editing existing files over creating new ones
- No half-finished implementations

## Comments

- Default to **no comments**
- Only add a comment when the WHY is non-obvious: a hidden constraint, a subtle invariant, a workaround for a specific bug
- Never explain WHAT the code does — well-named identifiers do that
- No multi-line comment blocks or docstrings

## Error Handling

- Only validate at system boundaries: user input, external APIs, environment variables
- Don't add fallbacks or error handling for scenarios that can't happen
- Trust internal code and framework guarantees

## Frontend Stack

- **Framework:** React + Vite (never Create React App)
- **Components:** shadcn/ui + Tailwind CSS
- **Package manager:** npm
- **Language:** JavaScript (JSX) by default; TypeScript when the project already uses it

## Git Conventions

- **Commit message format:** `type: short description` (conventional commits)
  - `feat:` new feature
  - `fix:` bug fix
  - `chore:` tooling, config, dependencies
  - `refactor:` restructuring without behavior change
  - `docs:` documentation only
  - `style:` formatting, no logic change
- Keep commits small and focused — one logical change per commit
- Stage specific files by name — never `git add .` or `git add -A` blindly
- Default branch: `main`
- Feature/work branch: named after the feature or ticket

## Project Setup Defaults

- Always include a proper `.gitignore` with: `node_modules`, `dist`, `dist-ssr`, `.env`, `.env.*`, `*.local`
- `package.json` name must match the repo name
- Run `npm run build` to verify the project compiles before the first commit
