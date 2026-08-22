# Contributing

Thanks for helping keep this list useful. We curate **agent orchestrators** — tools that decide what an agent works on, when it runs, where it runs, or what happens to its output, and take whatever task you point them at.

If you're unsure whether something belongs, skim [How to choose](README.md#how-to-choose) and open an issue first.

## What belongs here

**In scope**

- Parallel session managers (terminal, desktop, or web)
- Autonomous loop / task runners that keep agents working without babysitting
- Multi-agent swarms that split work across agents
- Personal assistants that stay running, remember across sessions, and pick up work from chat
- Infrastructure and primitives that act as control planes, coordination protocols, harness adapters, or runtimes for orchestration

**Out of scope** (please don't open a PR for these alone)

- Single-purpose bots
- Memory backends, MCP servers, sandbox providers, or skill libraries as standalone products
- Things an agent merely *consumes* rather than a surface that *orchestrates* agents

## Categories

Pick one section (use these exact names):

| Category | Use when |
| --- | --- |
| Parallel Coding Agents — Terminal (TUI/CLI) | Side-by-side coding agents from a terminal (tmux, worktrees, TUI dashboards) |
| Parallel Coding Agents — Desktop & Web | Same idea as a desktop app or browser/mobile dashboard |
| Multi-Agent Swarms | Agents split a large job between themselves |
| Autonomous Loop Runners | One goal, driven until verified |
| Autonomous Task Runners | Work pulled from an issue tracker, board, or schedule |
| Agent Infrastructure & Primitives | Control planes, protocols, harness adapters, runtimes |
| Personal Assistants | Always-on chat/desktop agents; general tasks, not only code |

**Resting** is maintainer-managed. Don't submit new entries there — it's a watchlist for projects without recent pushes.

## How to add an entry

1. Fork the repo and create a branch.
2. Add **one** line to the right section of `README.md`, alphabetized by name:

   ```markdown
   - [project-name](https://github.com/owner/repo) - Short description of what it orchestrates and how.
   ```

3. Keep the description concrete (what it decides / runs / reviews), not marketing fluff.
4. Open a PR using the template. Fill in why it is an orchestrator, which category, and a freshness signal (recent push or last-commit month).

## PR quality bar

We'll look for:

- Clear fit to the inclusion criteria (not adjacent tooling)
- Correct category and alphabetical placement
- No duplicate of an existing listing (including Resting)
- A real public repo with enough signal to evaluate (README, activity)

PRs that are a bulk dump of many tools, or that only wrap an MCP/sandbox/memory product, will usually be closed with a pointer back here.

## Questions

Open an issue if the category is ambiguous or you want a maintainer take before writing the PR.
