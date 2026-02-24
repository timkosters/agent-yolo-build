# /yolo — Let Your Agent Build While You Sleep

A skill that turns your AI coding agent into an autonomous builder. Run `/yolo`, walk away, come back to a working MVP.

Inspired by [the overnight build pattern](https://x.com/bobbyhansenjr/status/2017585853418152313) — give your agent a YOLO task before bed, wake up to something shipped.

## What it does

1. **Scans your projects and the web** to find something worth building
2. **Picks one idea** based on novelty, feasibility, and usefulness
3. **Actually builds it** — working code, not a plan or a doc
4. **Presents the result** with a README, install instructions, and next steps

The agent works in a sandbox: new project directory, no modifications to your existing code, no outbound actions.

## Install

### Claude Code

```bash
mkdir -p ~/.claude/skills/yolo
cp SKILL.md ~/.claude/skills/yolo/SKILL.md
```

Or clone and symlink:

```bash
git clone https://github.com/timourkosters/agent-yolo-build.git
mkdir -p ~/.claude/skills
ln -s "$(pwd)/agent-yolo-build" ~/.claude/skills/yolo
```

### Other agents

The skill is a single markdown file (`SKILL.md`) with structured instructions any coding agent can follow. Copy it into whatever prompt/skill format your agent uses, or paste it directly as a system prompt.

## Usage

```
/yolo
```

Optionally focus the session:

```
/yolo chrome extension
/yolo CLI tool for my workflow
/yolo MCP server
/yolo something with the Hacker News API
```

Then walk away. The agent will:
- Research opportunities in your domain
- Pick the most promising idea
- Build a working MVP in a new project directory
- Summarize what it built when you come back

## Requirements

- A coding agent with file write access and web search (Claude Code, Cursor, Windsurf, Codex, etc.)
- Recommended: run with auto-approve / skip permissions so the agent can work uninterrupted
- Web search access for the research phase

## How it works

1. **Research phase** (10 min): Three parallel tracks scan your local context, trending market gaps, and quick-win build patterns
2. **Decision phase** (5 min): Pick one thing, state why, start building
3. **Build phase** (60-90 min): Write actual code, test it, iterate
4. **Ship phase**: README, git init, present results

Everything goes in a new directory. Your existing projects are never touched.

## Safety

- Creates new project directories only — never modifies existing code
- No outbound actions (no emails, messages, posts, API calls on your behalf)
- No paid services or financial commitments
- No global package installs or system config changes
- No git push — repos stay local until you decide to publish
- No secrets hardcoded — uses environment variables

## Examples of what it might build

- An MCP server for a service that doesn't have one yet
- A CLI tool that automates something tedious in your workflow
- A browser extension that fixes a common annoyance
- A data dashboard pulling from public APIs
- A Telegram/Discord/Slack bot
- A landing page + waitlist for a validated idea
- An AI-powered micro-tool (summarizer, classifier, search)

## Customization

Edit `SKILL.md` to:
- Change the default focus areas
- Adjust scope expectations (more/less ambitious)
- Add preferred tech stacks
- Add your own safety rules

It's just a markdown file. Fork it, make it yours.

## Credits

Concept inspired by [Bobby Hansen Jr.](https://x.com/bobbyhansenjr) and the overnight autonomous build movement.

## License

MIT
