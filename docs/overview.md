# Claude Code CLI – TL;DR Cheat-Sheet

## What & Why

* Terminal-native AI coding agent (Anthropic Claude)
* Reads/edits code, runs commands, handles git → “brilliant intern”
* Best for speeding rote work, debugging, quick prototypes

## Installation & Setup

⚠️ **Platform Requirements**: Claude Code requires a Unix-like environment
* **Windows users**: Install WSL2 (Windows Subsystem for Linux) first
  * Work directly in WSL filesystems for optimal performance
  * WSL→Windows filesystem access is extremely slow - avoid mounting Windows drives

### Claude Code CLI Installation

```bash
npm install -g @anthropic-ai/claude-code
```
Requires Node.js 18+

### Authentication 
* **Recommended**: Claude Max subscription (unlimited usage)
  * Run `claude` → automatically prompts to log into your Claude account
  * No API key needed, authentication handled via browser login
* **Alternative**: Use API key (pay-per-use)
  * `export ANTHROPIC_API_KEY=your-key-here`

### MCP Server Setup (Optional but Recommended)

MCP servers extend Claude's capabilities:

```bash
# Context7 - Up-to-date library documentation
claude mcp add --scope user --transport sse context7 https://mcp.context7.com/sse

# Atlassian - Jira/Confluence integration  
claude mcp add atlassian https://mcp.atlassian.com/v1/sse --scope user --transport sse

# Verify installation
claude mcp list
```

**Note:** Within claude you can use the `/mcp` command to see and log in to your MCP servers.

**Note:** Remember Claude can run command line tools as well.  I find that I don't need a GitHub MCP server -- Claude just runs `git`

### VS Code Setup

Install the Claude plugin.  (you can just run Claude in a terminal and it will do it automatically).

* Drag and drop files (including images) into the chat terminal
* visual diffs


### Essential Configuration

* Create `CLAUDE.md` in project root → Define project-specific rules, build commands, conventions

### Essential Tips

**Tip:** If you see it doing something you don't like, hit `[ESC]` and tell it to undo stuff or do something different.  Do this liberally.

**Tip:** Use revision control.  Commit frequently, get used to throwing away lots of Claude-generated code.

**Tip:** Claude can do more things than you expect.  "Don't do the thing, tell it to do the thing."

## Core Workflow

1. **Explore** – ask questions, open files, build mental model
2. **Plan** – prompt Claude to outline multiple approaches (“think hard”)
3. **Review** – have Claude critique its own plan; pick the best
4. **Implement** – let Claude code/tests; approve actions
5. **Self-check** – prompt for edge-case review, run tests
6. **Commit** – small batches, descriptive messages
7. **Iterate / Refactor** – polish, simplify, document

## Guiding Principles

* Treat Claude like a junior dev: clear specs, guardrails
* Ask for **options** (# proposals > 1) before coding
* Use **self-review loops** (“Find mistakes in above diff”)
* **Autonomy dial:** manual → allow common tools → full auto (sandbox/YOLO)
* Break big tasks into checkpoints; commit often

## High-Leverage Prompts

* “Explain module X; no code changes”
* “Suggest 3 ways to fix error Y; compare trade-offs”
* “Write failing tests first, then implement”
* “Refactor function Z for readability; think step-by-step”
* “Review your own patch for bugs/perf issues”

## Context Tips

* Name files explicitly in prompts
* Keep `CLAUDE.md` concise & current (add repeated clarifications)
* Use `/clear` between unrelated tasks to avoid context bleed
* Pipe logs/data: `cat log.txt | claude` for analysis

## Safe Autonomy

* Default ask-before-action → good for new users
* Auto-accept mode for low-risk chores (linting, docs)
* `--dangerously-skip-permissions` only in disposable envs

## Common Wins

* Rapid onboarding: “How does auth work here?”
* Bulk test generation & CI review comments
* Automated lint/dep upgrades
* Debugging via pasted stack traces, screen shots(!) + follow-up fixes

## Mindset Shift

* You **manage tasks & quality**; Claude does grunt work
* Iterate conversationally; clarity & feedback drive quality
* Goal: make Claude as autonomous as safety allows, while you steer

