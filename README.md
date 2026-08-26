# Awesome Agent Orchestrators [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of tools and frameworks for orchestrating agents.

Everything here decides what an agent works on, when it runs, where it runs, or what happens to its output, and takes whatever task you point it at. Single-purpose bots, and things an agent merely consumes — memory backends, MCP servers, sandbox providers, skill libraries — are out of scope.

## How to choose

- **Run several agents at once and review each diff.** [Terminal](#parallel-coding-agents--terminal-tuicli) if you live in tmux, [Desktop & Web](#parallel-coding-agents--desktop--web) if you want a GUI or phone access.
- **Keep an agent working while you're away.** [Autonomous Loop Runners](#autonomous-loop-runners) drive one goal until it verifies. [Autonomous Task Runners](#autonomous-task-runners) pull work from an issue tracker, board, or schedule.
- **Have agents split a large job between themselves.** [Multi-Agent Swarms](#multi-agent-swarms).
- **Message an agent instead of opening a tool.** [Personal Assistants](#personal-assistants) stay running, remember across sessions, and pick up work from a chat thread — general tasks, not only code.
- **Build your own orchestrator.** [Agent Infrastructure & Primitives](#agent-infrastructure--primitives) — control planes, coordination protocols, harness adapters, and runtimes.

## Parallel Coding Agents — Terminal (TUI/CLI)

Run and supervise several agent sessions side by side from a terminal — tmux panes, git worktrees, and TUI dashboards.

- [agent-console](https://github.com/buhuipao/agent-console) - Rust TUI that finds Codex and Claude Code sessions from the providers' own transcripts, including ones started elsewhere, and resumes their native UI rather than replacing it. No tmux or worktrees.
- [agent-deck](https://github.com/asheshgoplani/agent-deck) - One TUI covering sessions across Claude Code, Codex, Gemini, and OpenCode, with live status and resume for each.
- [agent-manager](https://github.com/YoanWai/agent-manager) - tmux TUI with live status, a prompt that lands in the pane without attaching, and in-terminal diff review that sends line comments back to the agent. Claude Code, Codex, OpenCode, Grok, Gemini CLI, Pi, Hermes.
- [agent-of-empires](https://github.com/agent-of-empires/agent-of-empires) - Pairs a TUI with a matching web view, so the same sessions stay reachable from a phone. Claude Code, Codex, OpenCode, Gemini, Mistral Vibe.
- [agentbox](https://github.com/madarco/agentbox) - Gives each agent its own sandboxed VM — local Docker or cloud via Hetzner, Daytona, Vercel, or E2B — with sub-second checkpoint starts.
- [agterm](https://github.com/umputun/agterm) - Native macOS terminal with named workspaces, a live dashboard, attention states, and a scriptable control API.
- [amux](https://github.com/andyrewlee/amux) - Minimal TUI for spawning parallel coding agents in git worktrees.
- [claude-squad](https://github.com/smtg-ai/claude-squad) - Runs each agent as a detached background session with its own worktree, so work continues after you close the pane. Claude Code, Codex, OpenCode, Amp.
- [cmux](https://github.com/manaflow-ai/cmux) - Ghostty-based macOS terminal with vertical tabs and per-agent notifications, built for keeping many concurrent sessions legible.
- [dmux](https://github.com/standardagents/dmux) - Dev agent multiplexer pairing coding agents with git worktrees over tmux.
- [herdr](https://github.com/herdrdev/herdr) - Background runtime that owns your agents' terminals: sessions survive reboot and reattach from any terminal or SSH, panes are marked working/blocked/idle, and agents themselves spawn panes and prompt each other over a CLI and socket API. One Rust binary.
- [openkanban](https://github.com/TechDufus/openkanban) - Kanban board for orchestrating coding agents, rendered entirely in the terminal.
- [repomon](https://github.com/AliHamzaAzam/repomon) - Rust TUI that supervises a fleet across many repositories at once, in durable tmux sessions you can approve from your phone.
- [thurbox](https://github.com/Thurbeen/thurbox) - TUI orchestrator with remote SSH sessions, inter-session messaging, and a native code-review view. Works with any CLI agent you define.
- [tmux-ide](https://github.com/wavyrai/tmux-ide) - Turns any project into a tmux IDE from a checked-in `ide.yml`, including preset agent-team layouts.

## Parallel Coding Agents — Desktop & Web

The same parallel-sessions workflow as a desktop app or browser/mobile dashboard, with diff review and merge.

- [agent-orchestrator](https://github.com/Untrivial-ai/agent-orchestrator) - Agent IDE for fleets that plans the work, spawns the agents, then fixes CI failures and merge conflicts without being asked.
- [agent-squid](https://github.com/agent-squid/squid) - Browser UI organized into named lanes (`#topic@agent`), with context shared across agents and a realtime quota gauge.
- [AGX](https://github.com/ramarlina/agx) - Wake-work-sleep checkpointing keeps a persistent agent team on long objectives, with human gates between cycles.
- [ai-maestro](https://github.com/23blocks-OS/ai-maestro) - Dashboard spanning multiple machines, adding memory search, code-graph queries, and agent-to-agent messaging. Claude, Aider, Cursor.
- [aizen](https://github.com/vivy-company/aizen) - macOS workspace that organizes worktrees, environments, and agent sessions per project.
- [Alethe](https://github.com/Kc1t/alethe-agents) - Local-first desktop workspace where agents and shells run as real PTYs in split panes and custom grids across projects, surviving pane close and app restart. Suspend idle groups to reclaim memory and resume with scrollback intact. Claude Code, Codex, OpenCode.
- [Aperant](https://github.com/AndyMik90/Aperant) - Runs up to 12 agent terminals with a self-validating QA loop and automatic conflict resolution when merging back to main.
- [automaker](https://github.com/AutoMaker-Org/automaker) - Describe features on a Kanban board and agents implement them in isolated worktrees, running tests and committing as they go.
- [bb](https://github.com/get-bb/bb) - Self-controlling agentic IDE that orchestrates multiple coding agents in live threads you can follow, steer, or hand off, driven from a desktop app, web app, CLI, or HTTP API.
- [Berd](https://github.com/block/berd) - Block's open-source desktop app for working with AI agents: project chats with per-folder worktree behavior over the Goose backend, with agents, skills, connections, and agent sharing in one place.
- [Better Agent](https://github.com/ofekron/better-agent) - Local web workspace with persistent state, approvals, and restart recovery for native Claude, Codex, and Gemini sessions.
- [Claude Command Center (CCC)](https://github.com/amirfish1/claude-command-center) - Local dashboard for spawning, monitoring, and resuming sessions across Claude Code, Codex, Cursor, Antigravity, and Kilo Code.
- [clave](https://github.com/codika-io/clave) - Native macOS app with split and grid layouts, session groups, SSH remote sessions, and usage analytics for Claude Code.
- [clideck](https://github.com/rustykuntz/clideck) - Chat-app-style dashboard with autopilot routing between agents and full control from a phone. Claude Code, Codex, Gemini CLI, OpenCode.
- [CodeNomad](https://github.com/NeuralNomadsAI/CodeNomad) - Desktop and web workspace around the OpenCode CLI whose SideCars embed local tools like VS Code and terminals as tabs.
- [collaborator](https://github.com/collabs-inc/collab-public) - Arranges terminals, editors, and files as tiles on an infinite pan-and-zoom canvas instead of tabs.
- [Comet](https://github.com/zeronsh/comet) - Cross-device control plane for coding agents, syncing sessions across machines and keeping agents running on an always-on daemon. Claude Code, Codex, Cursor, Grok, Hermes, Pi.
- [constellagent](https://github.com/owengretzinger/constellagent) - macOS app giving each agent its own terminal, editor, and git worktree in a single window.
- [diri](https://github.com/cristicretu/diri) - Native macOS app running Claude Code, Codex, Cursor, Gemini, and shells in parallel across git worktrees or remote hosts, with live status, session persistence across restarts, a menu-bar rollup, and an MCP server for agents to spawn others.
- [dorothy](https://github.com/Charlie85270/Dorothy) - Desktop app combining agent orchestration with automations, Kanban management, and MCP servers.
- [Emdash](https://github.com/generalaction/emdash) - Agentic development environment running parallel agents against any model provider.
- [Fletch](https://github.com/fwdai/fletch) - Native macOS IDE that seals each agent in its own repo clone under Seatbelt or Docker, serves each a shared symbol and call-graph index over MCP, and gates every step on tests or your approval. Claude Code, Codex, Cursor, OpenCode.
- [Garcon](https://github.com/cfal/garcon) - Self-hosted browser and mobile workspace with diff review, Git/PR workflows, mobile approvals, scheduling, and cross-agent transfers. Seven CLI agents.
- [GraphCode](https://github.com/scgopi/GraphCode) - macOS app that wires agent sessions into a graph: each node is a live terminal you can attach to mid-run, each edge a hand-off, message, or spawn that fires while you're away. Claude Code, Copilot CLI, Codex.
- [humanlayer](https://github.com/humanlayer/humanlayer) - Human-in-the-loop control for coding agents on hard problems; the repo notes its code is now largely deprecated in favor of a rebuild.
- [IM.codes](https://github.com/im4codes/imcodes) - Mobile and web control layer built for away-from-desk continuation, with terminal access, git views, localhost preview, and scheduled tasks. Claude Code, Codex, Gemini CLI.
- [intentic](https://github.com/intentic/intentic) - Browser and mobile workspace where every agent gets a persistent Docker sandbox on a machine you own plus a git worktree of its own, reached over an outbound-only Cloudflare tunnel, so runs keep going after you close the tab. Plan mode, per-hunk diff review, an environment Dockerfile the agent proposes and you approve, credential capabilities injected per turn, and schedule, webhook or event triggers. Claude Code, Codex, Grok, Kimi Code, Gemini. MIT.
- [ivy-tendril](https://github.com/Ivy-Interactive/Ivy-Tendril) - Drives agents through a plan-based lifecycle with verification gates, self-improving memory, and human checkpoints. Claude Code, Codex, Antigravity, Copilot, OpenCode.
- [jat](https://github.com/joewinke/jat) - Visual dashboard combining live sessions, task management, code editor, and terminal, with parallel swarm workflows.
- [jean](https://github.com/coollabsio/jean) - Desktop and web app for orchestrating agents across multiple projects and their git worktrees. Claude, Codex, OpenCode.
- [kandev](https://github.com/kdlbs/kandev) - Kanban workbench whose multi-step workflows assign a different agent per step behind human gates, running locally, in Docker, over SSH, or in cloud executors.
- [mux](https://github.com/coder/mux) - Desktop app for isolated, parallel agentic development.
- [nimbalyst](https://github.com/nimbalyst/nimbalyst) - Visual workspace pairing parallel worktree sessions with kanban and direct visual editing. Claude Code, Codex, OpenCode.
- [octomux](https://github.com/ShreyPaharia/octomux) - Local dashboard with a kanban fleet view, one unified permission inbox across agents, and in-app diff review.
- [OpenChamber](https://github.com/openchamber/openchamber) - Open-source workspace for running, supervising, and reviewing AI coding work across desktop, browser, editor, and mobile, with parallel model runs and per-run worktrees.
- [Orca](https://github.com/stablyai/orca) - Agentic development environment for running a fleet on your own subscription, available on desktop and mobile.
- [Paseo](https://github.com/getpaseo/paseo) - Self-hosted daemon running agents in parallel on your own machines, driven from desktop, iOS/Android, web, or CLI, with voice control, diff review, and no telemetry or forced log-ins. Claude Code, Codex, Copilot, OpenCode, Pi.
- [Ouijit](https://github.com/ouijit/ouijit) - Kanban board and terminals wired together by lifecycle hooks, scripts, and a session-aware CLI, so a task runs by hand, on a script, or delegated to the agent. Per-task worktrees, optional VM sandboxing. Claude Code, Codex, Pi, OpenCode.
- [parallel-code](https://github.com/johannesjo/parallel-code) - Desktop app running Claude Code, Codex, and Gemini CLI side by side in isolated worktrees, with a built-in diff viewer and one-click merge.
- [Proliferate](https://github.com/proliferate-ai/proliferate) - Agent IDE that runs sessions locally or in the cloud and lets you build reusable workflows from them.
- [qm](https://github.com/yc-software/qm) - Multiplayer harness where each teammate gets an isolated workspace to run agents independently, driven from Slack or the web.
- [supacode](https://github.com/supabitapp/supacode) - Native macOS command center for worktree-per-agent development.
- [superset](https://github.com/superset-sh/superset) - Code editor built around running many agents on your machine at once.
- [synara](https://github.com/Emanuele-web04/synara) - GUI desktop workspace for running and managing agents across local projects.
- [t3code](https://github.com/pingdotgg/t3code) - Harness control surface available as web, mobile, and desktop app. Claude Code, Codex, Cursor, Grok Build, OpenCode.
- [takopi](https://github.com/banteg/takopi) - Telegram bridge that puts Codex, Claude Code, OpenCode, and Pi sessions in a chat thread.
- [Tempest](https://github.com/tempestai-dev/tempest) - Tauri desktop ADE running CLI agents in parallel isolated worktrees, with a shared local code-knowledge graph that cuts token use across sessions, plus live status and built-in diff/PR review.
- [tlbx](https://github.com/tlbx-ai/tlbx) - Self-hosted browser workspace holding persistent real PTY sessions on your own machines, reachable from any browser or phone.
- [Tortie](https://github.com/gregce/tortie) - Native macOS agent multiplexer with familiar IDE features: all projects in one window, agents that survive restarts, and organized terminal sessions without tmux.
- [Traycer](https://github.com/traycerai/traycer) - Bring-your-own-agent workspace running many sessions in parallel with context shared across models and providers, plus agent-to-agent messaging, shareable boards, and cross-device sync.
- [vibe-tree](https://github.com/sahithvibudhi/vibe-tree) - One git worktree per agent, delivered as desktop, web, and CLI.
- [vibecraft](https://github.com/rayzhudev/vibecraft) - RTS-style workspace for commanding coding agents.
- [Waku](https://github.com/egoist/waku) - Native macOS desktop app for working with local coding agents, keeping projects, sessions, and transcripts on your machine. Supports Amp, Claude Code, Codex CLI, Cursor CLI, Grok Build, OpenCode, and Pi.
- [Zaivern Code](https://github.com/tacyan/zaivern-code) - Cross-platform Rust desktop cockpit for running Claude Code, Codex, Gemini CLI, and 30+ coding agents in parallel, with fleet monitoring, mobile control, and line-level ownership to prevent merge conflicts.

## Multi-Agent Swarms

Systems where multiple specialized agents actively coordinate, communicate, and delegate toward a shared goal.

- [5dive](https://github.com/5dive-ai/5dive) - Named agents on a shared org chart and backlog hand work to each other and escalate to a human over Telegram. Claude Code, Codex, Grok, Antigravity, OpenCode.
- [Agent Teams](https://github.com/777genius/agent-teams-ai) - Desktop app where you give high-level commands to autonomous coding-agent teams across Claude Code, Codex, OpenCode, Cursor, Grok, GitHub Copilot, Kiro, Z.AI, MiniMax, Kimi, 200+ models, and 75+ LLM providers. Agents coordinate through inter-agent messaging, Kanban tasks, and built-in code review.
- [agent-kanban](https://github.com/saltbo/agent-kanban) - Leader-worker task board with cryptographic agent identity. Claude Code, Codex, Gemini CLI.
- [agentsmesh](https://github.com/AgentsMesh/AgentsMesh) - Remote AI workstations with PTY sandboxes and worktree isolation, coordinating across channels and pod bindings. Claude Code, Codex, Gemini CLI, Aider, OpenCode.
- [Agon](https://github.com/AutoResearch-Factory/Agon) - Orchestrates scientist, coder, and auditor loops from research topic through proposal to experiment.
- [buzz](https://github.com/block/buzz) - Agents are first-class members of shared channels on a Nostr relay you own, with their own keys and audit trails. Claude Code, Codex, Goose.
- [claude_codex_bridge](https://github.com/SeemSeam/claude_codex_bridge) - Workspace for mixing different vendors' CLI agents in one visible collaboration session.
- [ClawTeam](https://github.com/HKUDS/ClawTeam) - Agents spawn and manage their own teammates from one command, coordinating through file-based or P2P inboxes across tmux worktrees.
- [CompanyHelm](https://github.com/CompanyHelm/companyhelm) - Distributed orchestrator with task management and direct agent-to-agent conversations.
- [corellis](https://github.com/CorellisOrg/corellis) - Multi-agent governance framework for OpenClaw — goal decomposition, fleet-wide memory, correction propagation, and approval workflows for 20+ agent fleets.
- [Fusion](https://github.com/Runfusion/Fusion) - Multi-node orchestrator with a kanban board, plan-review-execute gates, per-task worktrees, and hierarchical missions.
- [gastown](https://github.com/gastownhall/gastown) - Scales to 20-30 agents with a coordinator, git-backed issue tracking, health watchdogs, and a Bors-style merge queue.
- [hcom](https://github.com/aannoo/hcom) - Lets agents message, watch, and spawn each other across terminals. Claude Code, Codex, Antigravity, Cursor, OpenCode, Kilo, and more.
- [kodo](https://github.com/ikamensh/kodo) - Directs agents through work cycles where a separate agent independently verifies each result. Claude Code, Codex, Gemini CLI.
- [loki-mode](https://github.com/asklokesh/loki-mode) - PRD-to-deployed-product SDLC with 41 agents in 8 swarms, nine quality gates, and blind three-reviewer code review. Source-available under BUSL-1.1.
- [multi-agent-shogun](https://github.com/yohey-w/multi-agent-shogun) - Shogun to karo to ashigaru hierarchy running up to 10 agents over tmux with no coordination API cost.
- [NXTG-Forge Orchestrator](https://github.com/nxtg-ai/forge-orchestrator) - Coordinates Claude Code, Codex, and Gemini CLI on one shared repo through a research-plan-delegate-adversarial-verify-deploy pipeline, with file locking, knowledge capture, and drift detection. Single Rust binary.
- [orc](https://github.com/spencermarx/orc) - Lightweight framework that piggybacks your existing CLI setup for planning, task decomposition, worktrees, and review.
- [ORCH](https://github.com/oxgeneral/ORCH) - CLI runtime managing agents as typed teams with an explicit state machine and goals. Claude Code, Codex, Cursor.
- [Orkas](https://github.com/Orkas-AI/Orkas) - A commander agent decomposes goals and dispatches specialists with isolated skills and memory. Claude Code, Codex, OpenCode, Cline.
- [paperclip](https://github.com/paperclipai/paperclip) - Self-hosted platform where agents wake on heartbeats to claim tickets, governed by org charts, budgets, and approval gates.
- [ruflo](https://github.com/ruvnet/ruflo) - Meta-harness for deploying coordinated swarms and conversational multi-agent workflows. Formerly claude-flow.
- [scion](https://github.com/GoogleCloudPlatform/scion) - Orchestration testbed running agents in parallel isolated containers with dynamic coordination and normalized telemetry.
- [shire](https://github.com/victor36max/shire) - Persistent team workspaces with inter-agent mailboxes and a shared drive. Claude Code, OpenCode, Pi.
- [tutti](https://github.com/nutthouse/tutti) - Config-driven workflows passing typed artifacts between agents, each in its own worktree.

## Autonomous Loop Runners

The "keep running until done" pattern — a single goal driven through a retry-until-verified loop.

- [bernstein](https://github.com/sipyourdrink-ltd/bernstein) - Keeps no model in the coordination loop, so orchestration costs zero tokens. Verifies with tests and auto-commits across 40+ CLI agents.
- [Dex](https://github.com/francescoalemanno/dex) - Human-gated planning, multi-reviewer code review, and dead-end-aware research loops, shipped as cross-platform binaries for 7 CLI backends.
- [fractal](https://github.com/plasma-ai/fractal) - Loops that recursively delegate separable subtasks to child agents, bounded by configurable depth, cost, and time limits.
- [Loop Engineering](https://github.com/cobusgreyling/loop-engineering) - Designs repeatable coding-agent loops around automation, worktrees, skills, state, and verification, with starters and a Loop Ready score for Grok, Claude Code, Codex, and OpenCode.
- [LoopTroop](https://github.com/looptroop-ai/LoopTroop) - An LLM council plans the work, then Ralph-style loops retry failed units with fresh context. Executes via OpenCode worktrees.
- [MartinLoop](https://github.com/Keesan12/martin-loop) - Caps spend, enforces policy, verifies output, and rolls back failures, leaving inspectable run receipts.
- [ralph-claude-code](https://github.com/frankbria/ralph-claude-code) - Development loop for Claude Code with exit detection that recognizes when the work is actually finished.
- [ralph-orchestrator](https://github.com/mikeyobrien/ralph-orchestrator) - Hat-based orchestration that keeps agents looping until done, as a fuller implementation of the Ralph Wiggum technique.
- [ralph-tui](https://github.com/subsy/ralph-tui) - Drives an agent through a task list autonomously, with a TUI for watching the loop.
- [ralphex](https://github.com/umputun/ralphex) - Executes an implementation plan autonomously with a fresh session per task, plus validation, retries, multi-phase review, and automatic commits. Claude Code, Codex.
- [toryo](https://github.com/JesseRWeigel/toryo) - Trust-based delegation with quality ratcheting that commits improvements and reverts regressions. Chains Claude Code, Aider, Gemini CLI, Ollama.

## Autonomous Task Runners

Unattended agents driven by an external source — an issue queue, a work board, or a schedule — that run and sync state back without side-by-side supervision.

- [aeon](https://github.com/aeonfun/aeon) - Runs unattended on GitHub Actions; dispatches skills to six coding-agent harnesses behind one contract (Claude Code, Grok, Codex, Pi, Vibe, Kimi), with quality scoring, git-persisted memory, a self-healing loop, and reactive triggers.
- [background-agents](https://github.com/ColeMurray/background-agents) - Sessions trigger from a web UI, Slack, GitHub, Linear, webhooks, or cron, run in Modal, Daytona, Vercel, E2B, or OpenComputer sandboxes, and open attributed PRs.
- [centaur](https://github.com/paradigmxyz/centaur) - Multiplayer self-hosted agents with Slack-native conversations, Kubernetes sandboxes, shared tools, and durable workflows.
- [claude-code-action](https://github.com/anthropics/claude-code-action) - Anthropic's official GitHub Action, detecting from context whether to answer, review, or implement. Auth via Anthropic API, Bedrock, Vertex, or Foundry.
- [codex-action](https://github.com/openai/codex-action) - OpenAI's official GitHub Action, running Codex CLI headlessly under drop-sudo, unprivileged-user, or fully read-only sandboxes.
- [Contrabass](https://github.com/junhoyeo/contrabass) - Terminal-first orchestrator for issue-driven agent runs, pulling work from Linear, GitHub Issues, or a local board into git worktrees with TUI, headless, and dashboard modes.
- [cyrus](https://github.com/cyrusagents/cyrus) - Watches Linear, GitHub, GitLab, and Slack issues assigned to it, spinning up an isolated worktree per issue. Claude Code, Codex, Cursor, Gemini.
- [Factory](https://github.com/owainlewis/factory) - Keeps coding agents working on a repository without making a human orchestrate every step from a terminal, pulling tasks from trusted ticket queues into isolated Codex workspaces.
- [gh-aw](https://github.com/github/gh-aw) - Compiles agentic workflows written in Markdown into GitHub Actions YAML. Read-only by default, with writes only through sanitized safe-outputs. Copilot, Claude, Codex, Gemini.
- [lalph](https://github.com/tim-smart/lalph) - Orchestrator driven by whichever source of issues you point it at.
- [multica](https://github.com/multica-ai/multica) - Managed agents platform where you assign tasks, track progress, and let agents compound skills between runs.
- [open-swe](https://github.com/langchain-ai/open-swe) - Invoked from Slack, Linear, or GitHub comments; each task runs in its own cloud sandbox and ends in a draft PR linked to the ticket.
- [OpenHands](https://github.com/OpenHands/OpenHands) - Self-hostable control center running its own agent or driving Claude Code, Codex, and any Agent Client Protocol agent, on schedules or webhooks.
- [remote-swe-agents](https://github.com/aws-samples/remote-swe-agents) - Serverless control plane on Lambda with a dedicated EC2 worker per session, triggered by issue comments, assignments, and PR reviews.
- [run-gemini-cli](https://github.com/google-github-actions/run-gemini-cli) - Google's official GitHub Action, running on event or schedule triggers or on demand via `@gemini-cli /review` and `/triage`.
- [sortie](https://github.com/sortie-ai/sortie) - Turns tracker tickets into agent sessions. Agent-agnostic and tracker-agnostic, as a single Go binary with SQLite persistence.
- [symphony](https://github.com/openai/symphony) - Turns project work into isolated autonomous runs, so teams manage the work rather than supervise the agent.
- [Taskuary](https://github.com/ldbumble/taskuary) - Local-first work inbox that triages email, chat, issue trackers, and scheduled reports into supervised Claude Code, Codex, Gemini, Cursor, or Copilot CLI runs, with conflict-aware queuing, live terminals, and approval-gated replies.

## Agent Infrastructure & Primitives

Control planes, coordination protocols, harness adapters, and runtimes — the layer beneath your agents rather than the surface you work in.

- [agent-runbook](https://github.com/KnoxOps/agent-runbook) - Compiles YAML runbooks with loops, branching, and parallelism into SKILL.md files for Claude Code and Codex.
- [Agentlas OS](https://github.com/agentlas-ai/Agentlas-OS) - Keeps specialist agents in a hub and spins up a temporary orchestrator per task, with A2A routing and governed memory gates. Formerly Hephaestus.
- [agenttier](https://github.com/agenttier/agenttier) - Kubernetes runtime giving each agent its own Pod and PVC sandbox behind a default-deny NetworkPolicy, with a streaming SSE invoke API.
- [aGiTrack](https://github.com/core-aix/agitrack) - Takes what a coding agent produces and commits each turn to git, recording the prompt, model, and that turn's token cost in the commit message, with the agent confined to its own worktree. Claude Code, Codex, and OpenCode.
- [Archon](https://github.com/coleam00/Archon) - Harness builder for deterministic AI coding workflows, combining agent steps with scripts, validation gates, approvals, and isolated git worktrees. Claude Code, Codex, and more.
- [Claudexor](https://github.com/razzant/claudexor) - Routes one coding thread across harnesses with quota-aware rotation between subscription profiles, Best-of-N runs, and cross-family review.
- [codecast](https://github.com/codecast-sh/codecast) - Watches your real local sessions and surfaces them in a live triage inbox, keeping a searchable record with line-level agent attribution. Claude Code, Codex, Cursor, Gemini.
- [Crewplane](https://github.com/crewplaneai/crewplane) - CLI-first control plane that turns one-off coding-agent calls into reviewable Markdown workflows spanning Claude Code, Codex, Gemini CLI, or Copilot CLI. Explicit artifact handoffs keep execution inspectable on disk, while validated completed nodes let failed workflows resume instead of starting over.
- [guild](https://github.com/mathomhaus/guild) - Shared context, memory, and task coordination as a single Go binary over local SQLite with hybrid keyword and semantic search.
- [handoff](https://github.com/dazuiba/handoff) - Delegates a task to DeepSeek, Codex, or Claude from inside your current Claude Code or Codex session, returning the result automatically.
- [LionClaw](https://github.com/moshthepitt/lionclaw) - Local control plane running coding agents as durable, auditable workers with explicit state, skills, and checkpoints.
- [NemoClaw](https://github.com/NVIDIA/NemoClaw) - Runs Hermes, LangChain Deep Agents, and OpenClaw inside NVIDIA OpenShell with managed inference.
- [neuralyzer](https://github.com/gintasz/neuralyzer) - Lets an agent wipe its own session context and re-run the first message, making Ralph loops easier to engineer.
- [omnigent](https://github.com/omnigent-ai/omnigent) - Meta-harness running Claude Code, Codex, Cursor, OpenCode, Hermes, Pi, or custom YAML agents against swappable sandbox backends, with policy enforcement.
- [Open Multi-Agent](https://github.com/open-multi-agent/open-multi-agent) - TypeScript-native runtime where a coordinator turns a goal into a task DAG and a deterministic scheduler runs specialized agents, with approvals, traces, evaluation, checkpoints, and resume support.
- [openfang](https://github.com/RightNow-AI/openfang) - Open-source agent operating system.
- [sandbox-agent](https://github.com/rivet-dev/sandbox-agent) - Daemon, HTTP/SSE API, and TypeScript SDK for driving six coding agents inside E2B, Daytona, Modal, Cloudflare Containers, or Docker.
- [skillfold](https://github.com/byronxlg/skillfold) - Declares skills in YAML and pins exact revisions in a lockfile so installs are reproducible across Claude Code and Codex.
- [sub-agents-skills](https://github.com/shinpr/sub-agents-skills) - Portable Markdown definitions that route a task to a chosen backend, model, effort level, and permission set.

## Personal Assistants

Always-on agents you reach over chat or a desktop app. They remember across sessions, run on their own schedule, and hand work off to tools and other agents — coding agents included, though the work isn't limited to code.

- [assistant](https://github.com/kcosr/assistant) - Panel-based assistant whose plugins share one workspace of notes, lists, and objects.
- [automata](https://github.com/sentientwave/automata) - Matrix-native workspace where Temporal-backed durable workflows survive restarts and keep long tasks moving.
- [Cloudflare OS](https://github.com/cloudflare/cloudflare-os) - Self-hostable "company OS" on Cloudflare Workers: a chat UI where agents preloaded with your company context do tasks, build sandboxed apps, and stay inside a Gatekeepers guardrail framework.
- [Coworker](https://github.com/accomplish-ai/coworker) - Open source AI coworker that lives on your desktop. Formerly accomplish.
- [denchclaw](https://github.com/DenchHQ/DenchClaw) - Managed OpenClaw framework aimed at CRM, sales automation, and outreach.
- [ghostclaw](https://github.com/b1rdmania/ghostclaw) - An AI that lives on your computer and does things for you.
- [hermes-agent](https://github.com/NousResearch/hermes-agent) - Self-improving harness with persistent cross-session memory and auto-generated skill documents.
- [Hivekeep](https://github.com/MarlBurroW/hivekeep) - Self-hosted team of specialized agents with persistent memory that delegate and build their own tools and mini-apps. Telegram, Slack, Discord, Matrix. Single container, MIT.
- [ironclaw](https://github.com/nearai/ironclaw) - Agent OS in Rust focused on privacy, security, and extensibility.
- [iva](https://github.com/smixs/iva) - Telegram assistant that turns your messages, voice notes and photos into an Obsidian-compatible markdown vault it remembers across sessions. Crons, skills, MCP and Google Workspace from an in-chat menu. Self-hosted in one command, MIT.
- [lemon](https://github.com/z80dev/lemon) - Local-first assistant and coding agent runtime.
- [leon](https://github.com/leon-ai/leon) - Long-running open-source personal assistant with voice and text interfaces.
- [lobsterai](https://github.com/netease-youdao/LobsterAI) - Desktop-grade agent for data analysis, slides, docs, and web research.
- [lucinate](https://github.com/lucinate-ai/lucinate) - Terminal-native chat client for OpenClaw, Hermes, Ollama, and OpenAI-compatible providers, with cron management and session browsing.
- [MetaClaw](https://github.com/aiming-lab/MetaClaw) - Assistant that learns and evolves from conversation alone.
- [nanobot](https://github.com/HKUDS/nanobot) - Ultra-lightweight self-hosted assistant in Python with WebUI, tools, memory, MCP, and multi-agent workflows.
- [nanoclaw](https://github.com/nanocoai/nanoclaw) - Lightweight OpenClaw alternative running in containers, connecting to WhatsApp, Telegram, Slack, Discord, and Gmail.
- [nullclaw](https://github.com/nullclaw/nullclaw) - Fully autonomous assistant infrastructure written in Zig.
- [openclaw](https://github.com/openclaw/openclaw) - Your own personal AI assistant, on any OS and any platform.
- [OpenMausBot](https://github.com/milind-soni/OpenMausBot) - Open-source Grok Bot-style team of bots in a chat-app sidebar, where every bot is a real local agent — Claude or Codex — with its own personality, model, cloud computer, and connected apps, behind approval gates. Local-first, bring-your-own-agent.
- [Ouroboros](https://github.com/razzant/ouroboros) - General-purpose agent with durable identity and memory, reviewed self-modification, multi-agent coordination, and desktop and headless interfaces.
- [picoclaw](https://github.com/sipeed/picoclaw) - Tiny and fast assistant deployable anywhere.
- [QwenPaw](https://github.com/agentscope-ai/QwenPaw) - Personal assistant that deploys to your own machine or the cloud and plugs into multiple chat apps. Formerly CoPaw.
- [Rakazo](https://github.com/elie222/rakazo) - Self-hosted platform for persistent AI teammates with their own conversations, memory, and routines, running on shared team computers or isolated private ones, reachable from web, desktop, and mobile with voice mode. Bots delegate to peer bots or short-lived subagents. BYO model and sandbox.
- [rho](https://github.com/mikeyobrien/rho) - Stays running, remembers across sessions, and checks in on its own. macOS, Linux, Android.
- [rowboat](https://github.com/rowboatlabs/rowboat) - Open-source AI coworker with memory.
- [zclaw](https://github.com/tnm/zclaw) - Complete personal assistant in 888 KiB, running on an ESP32 with GPIO, cron, and custom tools.
- [zeroclaw](https://github.com/zeroclaw-labs/zeroclaw) - Fast, small, fully autonomous assistant infrastructure in Rust, deployable anywhere.

## Resting

A watchlist of projects without a push in the last few months (checked 2026-07-28). They stay here until they're active again, then move back up.

- [1code](https://github.com/21st-dev/1code) - Orchestration layer for Claude Code and Codex. _(last commit 2026-03; archived)_
- [antfarm](https://github.com/snarktank/antfarm) - Build your agent team in OpenClaw with one command. _(last commit 2026-02)_
- [ariana](https://github.com/ariana-dot-dev/ariana) - The IDE of the future. _(last commit 2026-03)_
- [babyagi3](https://github.com/yoheinakajima/babyagi3) - A minimal AI agent you configure once, then run through natural language. _(last commit 2026-03)_
- [cashclaw](https://github.com/moltlaunch/cashclaw) - An autonomous agent that takes work, does work, gets paid, and gets better at it. _(last commit 2026-03)_
- [clawe](https://github.com/getclawe/clawe) - Multi-agent coordination system: think Trello for OpenClaw agents. _(last commit 2026-02)_
- [CodexMonitor](https://github.com/Dimillian/CodexMonitor) - Orchestrate multiple Codex agents across local workspaces. _(last commit 2026-03)_
- [gnap](https://github.com/farol-team/gnap) - Git-native agent protocol coordinating agents through a shared repo as a task board, with no orchestrator process. _(last commit 2026-03)_
- [lettabot](https://github.com/letta-ai/lettabot) - Personal assistant that remembers everything. _(last commit 2026-05; archived, replaced by Letta Code)_
- [mercury](https://github.com/Michaelliv/mercury) - Personal AI assistant that lives where you chat. _(last commit 2026-03; archived)_
- [opengoat](https://github.com/marian2js/opengoat) - Build organizations of OpenClaw agents coordinating across Codex, Claude Code, Cursor, and OpenCode. _(last commit 2026-04)_
- [ralphy](https://github.com/michaelshimeles/ralphy) - Bash script that loops Claude Code, Codex, OpenCode, Cursor, Qwen, or Droid until the task is done. _(last commit 2026-02)_
- [subtask](https://github.com/zippoxer/subtask) - Claude Skill that runs your tasks through subagents in git worktrees. _(last commit 2026-04)_
- [swarm-protocol](https://github.com/phuryn/swarm-protocol) - Headless coordination over MCP: claim work, detect file conflicts, heartbeat, and hand off across sessions. _(last commit 2026-03)_
- [vibe-kanban](https://github.com/BloopAI/vibe-kanban) - Kanban board for managing AI coding agents. _(last commit 2026-04)_
- [wit](https://github.com/amaar-mc/wit) - Locks individual functions rather than files via Tree-sitter, warning agents of conflicts before they write. _(last commit 2026-03)_
- [wreckit](https://github.com/mikehostetler/wreckit) - Run the Ralph Wiggum loop over your roadmap. _(last commit 2026-04)_
