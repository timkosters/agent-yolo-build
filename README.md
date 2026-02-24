# /yolo — Let Your Agent Build While You Sleep

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that turns your AI agent into an autonomous builder. Run `/yolo`, walk away, come back to a working MVP.

Inspired by [the overnight build pattern](https://x.com/bobbyhansenjr/status/2017585853418152313) — give your agent a YOLO task before bed, wake up to something shipped.

## What it does

1. **Scans your projects and the web** to find something worth building
2. **Picks one idea** based on novelty, feasibility, and usefulness
3. **Actually builds it** — working code, not a plan or a doc
4. **Presents the result** with a README, install instructions, and next steps

The agent works in a sandbox: new project directory, no modifications to your existing code, no outbound actions.

## Install

```bash
# Create the skill directory
mkdir -p ~/.claude/skills/yolo

# Copy the skill file
cp SKILL.md ~/.claude/skills/yolo/SKILL.md
```

Or clone this repo and symlink:

```bash
git clone https://github.com/timourkosters/claude-yolo-skill.git
mkdir -p ~/.claude/skills
ln -s $(pwd)/claude-yolo-skill ~/.claude/skills/yolo
```

## Usage

In Claude Code, just run:

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

Then go do something else. The agent will:
- Research opportunities in your domain
- Pick the most promising idea
- Build a working MVP in a new project directory
- Summarize what it built when you come back

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) (Anthropic's CLI)
- Recommended: run with `--dangerously-skip-permissions` or approve permissions before walking away
- The agent will use `WebSearch` to research ideas — this requires an active internet connection

## How it works

The skill is a structured prompt in `SKILL.md` that Claude Code loads when you run `/yolo`. It instructs the agent to:

1. **Research phase** (10 min): Three parallel agents scan your local context, trending market gaps, and quick-win patterns
2. **Decision phase** (5 min): Pick one thing, state why, start building
3. **Build phase** (60-90 min): Write actual code, test it, iterate
4. **Ship phase**: README, git init, present results

The agent creates everything in a new directory and never touches your existing projects.

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
- A Telegram bot for your community
- A landing page + waitlist for a validated idea
- An AI-powered micro-tool (summarizer, classifier, search)

## Customization

Edit `SKILL.md` to:
- Change the default focus areas in Step 1
- Adjust scope expectations (more/less ambitious)
- Add preferred tech stacks
- Add your own safety rules

The skill is just a markdown file. Fork it, make it yours.

## Credits

Concept inspired by [Bobby Hansen Jr.](https://x.com/bobbyhansenjr) and the overnight autonomous build movement.

## License

MIT
