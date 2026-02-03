# Expo + NativeWind + Supabase Template

Mobile app template with Expo SDK 54, NativeWind, Supabase, and Claude Code integration.

## Tech Stack

- **Expo SDK 54** - React Native framework
- **Expo Router** - File-based routing
- **NativeWind** - Tailwind CSS for React Native
- **Zustand** - State management
- **Supabase** - Backend (PostgreSQL, Auth, Storage)

## Quick Start

```bash
# Install
npm install

# Setup environment
cp .env.example .env
# Edit .env with your Supabase credentials

# Run
npm start
```

## Project Structure

```
app/          # Pages (Expo Router)
components/   # UI components
lib/          # Supabase client, API
store/        # Zustand stores
docs/         # ADR documents
.claude/      # Claude Code config
```

## Scripts

| Command | Description |
|---------|-------------|
| `npm start` | Dev server |
| `npm run ios` | iOS simulator |
| `npm run android` | Android emulator |
| `npm run lint` | Lint check |
| `npm run format` | Auto-fix |

---

## Claude Code Setup

### 1. Environment Files

```bash
cp .env.example .env
cp .mcp.example.json .mcp.json
cp .claude/settings.local.example.json .claude/settings.local.json
```

### 2. MCP Server (Supabase)

Edit `.mcp.json` with your Supabase MCP URL.

### 3. Project Context

Edit `CLAUDE.md` with your project details.

---

## Creating Custom Skills

Skills teach Claude domain-specific knowledge. Located in `.claude/skills/`.

### Skill Structure

```
.claude/skills/
└── skill-name/
    ├── SKILL.md           # Required: Main definition
    ├── references/        # Optional: Detailed docs
    │   └── patterns.md
    └── examples/          # Optional: Code examples
        └── example.ts
```

### Step 1: Create Directory

```bash
mkdir -p .claude/skills/my-skill/{references,examples}
```

### Step 2: Create SKILL.md

```markdown
---
name: My Skill Name
description: This skill should be used when the user asks to "do X", "create Y", or mentions Z.
version: 0.1.0
---

# Skill Title

Brief instructions for Claude.

- Key point 1
- Key point 2
```

### Step 3: Add References (Optional)

Create `.claude/skills/my-skill/references/patterns.md`:

```markdown
# Patterns

## Pattern 1
Code or explanation...

## Pattern 2
Code or explanation...
```

### Step 4: Add Examples (Optional)

Create `.claude/skills/my-skill/examples/example.ts`:

```typescript
// Working code example
```

### Skill Tips

- **description**: Include exact trigger phrases users would say
- **references/**: Detailed documentation Claude can read
- **examples/**: Working code Claude can reference

---

## Creating Custom Commands

Commands are slash commands like `/component Button`.

### Command Structure

Create `.claude/commands/command-name.md`:

```markdown
---
description: Brief description (max 60 chars)
allowed-tools: Read, Write
argument-hint: [arg1] [arg2]
---

Instructions for Claude.

Use $1, $2 for arguments or $ARGUMENTS for all.
```

### Example: /component

```markdown
---
description: Create a new component
allowed-tools: Write, Read
argument-hint: [ComponentName]
---

Create `components/$1.tsx` with:
- Functional component
- Props interface
- NativeWind styling
```

Usage: `/component Button`

---

## Creating Hookify Rules

Rules validate Claude's actions. Located in `.claude/`.

### Rule Format

Create `.claude/hookify.rule-name.local.md`:

```markdown
---
name: rule-name
enabled: true
event: bash|file|stop|prompt
pattern: regex-pattern
action: warn|block
---

Message shown when rule triggers.
```

### Example: Warn on console.log

```markdown
---
name: no-console
enabled: true
event: file
pattern: console\.log
action: warn
---

Remove console.log before committing.
```

---

## License

MIT
