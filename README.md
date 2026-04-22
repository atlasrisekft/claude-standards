# claude-standards

Team Claude Code plugin for **atlasrisekft**. Enforces shared standards for UI/UX design, code style, and git conventions across all projects.

Once installed, Claude automatically applies these rules whenever you build UI or write code — no extra prompting needed.

---

## What's included

| Skill | Triggers when... |
|---|---|
| `design-standards` | Building or modifying any UI component, page, or layout |
| `code-standards` | Writing, reviewing, or committing code |

**Design standards cover:** shadcn/ui + Tailwind, dark mode by default, mobile-first, WCAG 2.1 AA accessibility, and 15 UX laws from [lawsofux.com](https://lawsofux.com).

**Code standards cover:** minimal style, no over-engineering, conventional commits, React + Vite stack defaults.

---

## Installation (do this once)

### Step 1 — Install nvm and Node (skip if already installed)

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
```

Then add nvm to your shell so it loads in every new terminal (run once):

```bash
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc && echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> ~/.zshrc
```

Close and reopen your terminal, then install Node:

```bash
nvm install --lts
```

> **Troubleshooting:** If `nvm` is still not found, run `export NVM_DIR="$HOME/.nvm" && source "$NVM_DIR/nvm.sh"` to load it in the current session, then retry.

### Step 2 — Install the Claude Code CLI

```bash
npm install -g @anthropic-ai/claude-code
```

Verify it works:

```bash
claude --version
```

### Step 3 — Add the team marketplace

```bash
claude plugin marketplace add github:atlasrisekft/claude-standards
```

### Step 4 — Install the plugin

```bash
claude plugin install claude-standards@atlasrisekft-standards
```

Done. Restart VS Code and the plugin is active in all your Claude Code sessions.

---

## Updating

When the plugin is updated, pull the latest version:

```bash
claude plugin update claude-standards
```

---

## Verifying the install

In any Claude Code session, ask:

> "What design standards should I follow for this project?"

Claude should respond with the team's shadcn/dark mode/UX laws rules without you having to explain them.

---

## Maintained by

[@atlasrisekft](https://github.com/atlasrisekft) — edit the skill files in `skills/` and push to update rules for the whole team.
