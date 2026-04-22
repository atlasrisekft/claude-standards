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

## Installation — macOS

### Step 1 — Install nvm and Node (skip if already installed)

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash
```

Create your zsh profile if it doesn't exist, then add nvm to it:

```bash
touch ~/.zshrc
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc && echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> ~/.zshrc
```

Close and reopen your terminal, then install Node:

```bash
nvm install --lts
```

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
claude plugin marketplace add atlasrisekft/claude-standards
```

### Step 4 — Install the plugin

```bash
claude plugin install claude-standards@atlasrisekft-standards
```

Restart VS Code — the plugin is now active in all Claude Code sessions.

---

## Installation — Windows

### Step 1 — Install Node.js

Download and run the installer from [nodejs.org](https://nodejs.org) (LTS version). This installs both `node` and `npm` automatically.

Verify in PowerShell:

```powershell
node --version
npm --version
```

### Step 2 — Install the Claude Code CLI

Open PowerShell and run:

```powershell
npm install -g @anthropic-ai/claude-code
```

Verify:

```powershell
claude --version
```

### Step 3 — Add the team marketplace

```powershell
claude plugin marketplace add atlasrisekft/claude-standards
```

### Step 4 — Install the plugin

```powershell
claude plugin install claude-standards@atlasrisekft-standards
```

Restart VS Code — the plugin is now active.

---

## Updating

When the plugin is updated, run:

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
