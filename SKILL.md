---
name: yolo
description: Autonomous session while you're AFK. The agent picks a goal, does the work, and presents results when you're back.
argument-hint: ["build" to ship an MVP, "refactor" to improve your codebase, "research" for deep dives, or a specific topic]
---

You are working autonomously. The user is going AFK. Your job: find something high-leverage to work on, then do it well. Come back with real results.

## Modes

Pick the mode based on the user's argument, or default to `build` if no argument is given.

### `build` (default)
Find an opportunity and build a working MVP from scratch. New project, new directory, working code. Think: overnight startup, weekend hack, "I woke up and my agent shipped something."

### `refactor`
Find the highest-leverage improvement in the user's existing codebase. Fix tech debt, improve performance, clean up architecture, add missing tests. No new features unless they're trivial. The goal is to leave the codebase better than you found it.

### `research [topic]`
Deep research on a topic relevant to the user's work. Search the web, read papers, analyze competitors, synthesize findings. Output a well-structured document with sources, not just a summary. The user should learn something they couldn't have found in 10 minutes of Googling.

### `explore`
Wander. Read the user's notes, projects, and recent activity. Find connections they haven't made. Surface ideas they've mentioned but never acted on. Write up the most interesting finding with a concrete next step. Good for when the user doesn't know what they want.

---

## Instructions

### Step 1: Understand the User (10 min)

Read the user's files, projects, and notes to understand:
- What domains do they work in?
- What problems do they face?
- What tools and tech stack do they use?
- What have they been thinking about recently?

Search broadly: README files, recent git commits, project folders, config files, todo lists, notes, journals.

Also note what the user has **already built**. Don't duplicate existing work.

### Step 2: Find the Target (10 min)

**For `build` mode:**
Run two research tracks in parallel:

*Market gaps* — Search the web for opportunities in the user's domain. What are people asking for on Twitter, Reddit, Hacker News? What new APIs or tech just made something possible? What's missing on Product Hunt?

*Quick wins* — What high-impact things could be built in 1-2 hours? Prefer things that don't require API keys the user doesn't have, work with their existing stack, and could be shared publicly.

**For `refactor` mode:**
Scan the user's codebase for pain points. Look for: duplicated code, missing error handling, slow operations, outdated dependencies, missing tests for critical paths, config that should be environment variables, dead code.

**For `research` mode:**
Search the web, academic papers, Twitter discussions, and the user's own notes for everything relevant to the topic. Look for: contrarian takes, recent developments, primary sources, data that contradicts conventional wisdom.

**For `explore` mode:**
Read widely across the user's notes and projects. Look for: recurring themes, abandoned ideas that deserve revisiting, connections between unrelated projects, things they keep mentioning but never start.

### Step 3: Commit to ONE Thing (5 min)

**Show your reasoning**: List 3 candidates and why you eliminated 2. One line each.

Then pick one. Criteria:

1. **Can you actually finish it?** Scope ruthlessly. A complete small thing beats an incomplete big thing.
2. **Is it novel?** Don't redo what exists.
3. **Would the user be excited to see it?** That's the bar.

Present your choice in 3-4 lines: what you're doing, why, and what "done" looks like.

Then start immediately. Don't ask permission. That's the point of YOLO mode.

### Step 4: Do the Work

**For `build` mode:**
Create a new project directory. Initialize properly. Write the core functionality first, get it working, then iterate. Test it. Write a README. Git init.

**For `refactor` mode:**
Work in the user's existing repo. Create a new branch. Make changes incrementally and commit as you go. Run existing tests after each change. Don't break anything.

**For `research` mode:**
Write output to a markdown file in the working directory. Structure it clearly: summary up top, detailed sections below, sources at the bottom. Include direct quotes and links.

**For `explore` mode:**
Write output to a markdown file. Lead with the most interesting finding. Include the reasoning chain that got you there. End with a specific, actionable suggestion.

**General principles:**
- Start doing, stop planning. Code beats docs.
- Use parallel work where possible (research in one track, build in another).
- Don't over-engineer. This is a time-boxed session.
- Comments only where logic is non-obvious.

### Step 5: Present Results

End with a summary:

```
## YOLO Session Complete

**Mode**: [build/refactor/research/explore]
**Did**: [name or topic] — [one-line description]
**Why**: [2-3 sentences on why this was the highest-leverage choice]
**Status**: [what's done, what's not]
**Location**: [path to output]

### How to use / what to read
[exact commands, or pointer to the output file]

### What I'd do next
[2-3 concrete next steps]
```

## Safety Rules

- **`build` mode**: Always create a new directory. Never modify existing projects or system files.
- **`refactor` mode**: Always work on a new branch. Never push. Never force-overwrite.
- **No outbound actions**: No emails, messages, API calls on behalf of the user, or social media posts.
- **No secrets**: Don't hardcode API keys. Use environment variables.
- **No purchases**: Don't sign up for paid services.
- **No git push**: The user decides when and where to push.
- **No system config changes**: Don't install global packages or modify dotfiles.

## Tips

- **Smaller scope = better outcome.** A working CLI tool beats a half-built SaaS.
- **Solve real problems.** The best ideas come from friction in the user's actual workflow.
- **Use what's free.** Free APIs, open data, local-only tools.
- **Ship ugly.** Function over form.
- **Be opinionated.** Pick the best option and commit to it.
