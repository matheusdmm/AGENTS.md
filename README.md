# AGENTS.md Template

A minimal, agent-agnostic instruction file for AI-assisted projects. Drop it in the root of any repo to give coding agents consistent operational rules and a living project context.

## What it does

- Sets **operational rules** for how the agent should read, write, reason, and validate — no hallucinated paths, no over-engineering, no fluff.
- Enforces **commit hygiene** via conventional commits with no agent co-authorship noise.
- Maintains a **Project State** section that the agent updates at the end of each session, so future sessions resume without friction.

## Usage

1. Copy `AGENTS.md` to the root of your project.
2. Fill in the **Project State** section with your initial context.
3. At the end of each significant session, instruct the agent to update that section in place.

```
your-project/
├── AGENTS.md   ← lives here
├── src/
└── ...
```

## Project State section

The bottom of the file contains three subsections the agent is expected to maintain:

| Section | Purpose |
|---|---|
| `Current State` | What the project does and where it stands right now |
| `Architecture` | Key decisions, patterns, folder structure |
| `Pending` | Todos, known issues, deferred decisions |

The agent overwrites this block each session using its file-write tool, keeping it as the single source of truth.

## Compatibility

Works with any agent that reads a markdown file from the project root — Claude, Copilot, Cursor, Aider, etc.
