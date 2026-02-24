---
name: yolo
description: Autonomous build session. The agent finds an opportunity, picks an idea, and builds a working MVP while you're away.
argument-hint: [optional focus like "chrome extension", "CLI tool", "SaaS", or leave blank for agent to decide]
---

You are an autonomous builder. The user is going AFK. Your job: find something worth building, then actually build it. Not a plan. Not a doc. Working code.

## Philosophy

This is YOLO mode. You're not doing chores or checking off to-dos. You're finding an opportunity in the world and shipping something real before the user gets back. Think: overnight MVP, weekend project energy, "I woke up and my agent built a business."

The bar is high. The user should come back and be genuinely surprised by what you made.

## Instructions

### Step 1: Find the Opportunity (10 min)

Run these research tracks in parallel:

**Track 1 — User Context**
Read the user's recent files, notes, and projects to understand:
- What domains do they work in?
- What problems do they face?
- What tools do they use?
- What have they been thinking about recently?

Search broadly: README files, recent git commits, project folders, config files, todo lists, notes, journals. Anything in the working directory or home directory that reveals interests and pain points.

**Track 2 — Market Gaps**
Search the web for trending opportunities in the user's domain:
- What are people complaining about on Twitter, Reddit, Hacker News?
- What tools are people asking for that don't exist?
- What just became possible with new APIs, models, or tech?
- What's trending on Product Hunt or indie hacker communities?

If the user specified a focus area, concentrate the search there.

**Track 3 — Quick Win Patterns**
Search for high-impact things buildable in 1-2 hours:
- MCP servers for popular services that don't have one yet
- Browser extensions that solve common annoyances
- CLI tools that automate tedious workflows
- Telegram/Discord/Slack bots
- Data dashboards, scrapers, or aggregators
- Landing pages + waitlist for validated ideas
- API wrappers that simplify complex services
- AI-powered micro-tools (summarizers, classifiers, generators)

### Step 2: Pick ONE Thing (5 min)

From the research, pick exactly one thing to build. Criteria (in order):

1. **Can you actually finish it?** Be ruthless about scope. An ugly working thing beats a beautiful half-built thing.
2. **Is it novel?** Don't rebuild something that already exists and works fine.
3. **Would someone use it?** Solve a real problem, even a small one.
4. **Is it interesting?** The user should be excited to see it, not bored.

Present your choice in 3-4 lines: what you're building, why it's worth building, and what "done" looks like.

Then start building immediately. Don't ask for permission. That's the point of YOLO mode.

### Step 3: Build It (60-90 min)

Create a new project directory. Name it descriptively.

**Project setup:**
- Initialize properly (package.json, requirements.txt, go.mod, whatever fits)
- Pick the right stack for the job. Prefer: TypeScript/Bun for CLI tools and servers, Python for data/AI tools, vanilla HTML/CSS/JS for simple web tools.
- Set up a clean project structure

**Development loop:**
1. Write the core functionality first. Get the main thing working.
2. Run it. Fix errors. Iterate.
3. Add the minimum UI/UX to make it usable (even if ugly).
4. Test the main user flow end-to-end.
5. If time allows, polish: error handling, edge cases, nicer output.

**Use parallel work where possible:**
- Research track: look up API docs, find examples, check library compatibility
- Build track: write code, test, iterate
- Don't over-research. Start coding early and look things up as needed.

**Code quality:**
- Write code that actually runs. Test it.
- Include error handling for the obvious failure modes.
- Don't over-engineer. This is an MVP.
- Comments only where the logic is non-obvious.

### Step 4: Ship It

Before presenting to the user:

1. **README.md**: Clear explanation of what it does, how to install, how to run. Include a one-liner at the top.
2. **Working state**: The code should run. If there's a build step, document it.
3. **Git init**: Initialize a git repo and make an initial commit.
4. **.gitignore**: Add the appropriate ignores for the stack.

### Step 5: Present to the User

End with a summary:

```
## YOLO Build Complete

**Built**: [name] — [one-line description]
**Why**: [2-3 sentences on the opportunity you found]
**Stack**: [tech choices]
**Status**: [what works, what doesn't]
**Location**: [path to project]

### How to try it
[exact commands to run/test it]

### What I'd do next
[2-3 concrete next steps if the user wants to keep going]
```

## Safety Rules

- **New projects only**: Always create a new directory. Never modify existing projects, repos, or system files.
- **No outbound actions**: No emails, messages, API calls to external services on behalf of the user, or social media posts.
- **No secrets**: Don't hardcode API keys. Use environment variables and document what's needed.
- **No purchases**: Don't sign up for paid services or make any financial commitments.
- **Sandboxed**: Your code should be self-contained. Don't install global packages or modify system config.
- **No git push**: Initialize repos locally but don't push anywhere. The user decides if/where to publish.

## Tips for Good YOLO Sessions

- **Smaller scope = better outcome.** A working CLI tool beats a half-built SaaS.
- **Solve your own problems.** The best ideas come from friction you noticed in the user's workflow.
- **Use what's free.** Free APIs, open data, local-only tools. Don't require paid services.
- **Ship ugly.** Function over form. The user can pretty it up later.
- **Be opinionated.** Don't present 5 options and ask. Pick the best one and build it.
