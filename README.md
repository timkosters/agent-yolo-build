# /yolo — Autonomous Agent Sessions

Run `/yolo`, walk away, come back to results. Your AI coding agent picks a goal and works on it while you're gone.

Inspired by [the overnight build pattern](https://x.com/bobbyhansenjr/status/2017585853418152313).

## Modes

| Command | What the agent does |
|---|---|
| `/yolo` or `/yolo build` | Finds an opportunity and builds a working MVP from scratch |
| `/yolo refactor` | Finds the highest-leverage improvement in your codebase |
| `/yolo research [topic]` | Deep research with sources, not just a summary |
| `/yolo explore` | Reads your notes and projects, surfaces connections you missed |

You can also pass a focus: `/yolo build chrome extension` or `/yolo research state of MCP servers`.

## Install

### Claude Code

```bash
mkdir -p ~/.claude/skills/yolo
curl -o ~/.claude/skills/yolo/SKILL.md \
  https://raw.githubusercontent.com/timkosters/agent-yolo-build/main/SKILL.md
```

Or clone and symlink:

```bash
git clone https://github.com/timkosters/agent-yolo-build.git
mkdir -p ~/.claude/skills
ln -s "$(pwd)/agent-yolo-build" ~/.claude/skills/yolo
```

### Other agents

`SKILL.md` is a single markdown file with structured instructions. Copy it into whatever prompt or skill format your agent uses, or paste it as a system prompt. It works with any coding agent that can read files, search the web, and write code.

## How it works

1. **Understand** (10 min): Scans your projects, notes, and recent work to learn your context
2. **Target** (10 min): Researches opportunities (for build) or pain points (for refactor) or sources (for research)
3. **Commit** (5 min): Lists 3 candidates, eliminates 2 with reasons, picks one
4. **Work** (60-90 min): Does the actual work. Code, tests, iteration.
5. **Present**: Summary of what was done, how to use it, what's next

## Safety

All modes:
- No outbound actions (no emails, messages, posts)
- No paid services or purchases
- No git push (you decide when to publish)
- No global installs or system config changes
- No hardcoded secrets

Mode-specific:
- `build` creates a new directory, never touches existing projects
- `refactor` works on a new branch, never pushes or force-overwrites

## Requirements

- A coding agent with file access and web search (Claude Code, Cursor, Windsurf, Codex, etc.)
- Auto-approve or skip-permissions mode recommended so the agent can work uninterrupted
- Internet connection for the research phase

## Customization

`SKILL.md` is just a markdown file. Fork it to:
- Add your own modes
- Change the default tech stack preferences
- Adjust scope and ambition level
- Add custom safety rules

## License

MIT
