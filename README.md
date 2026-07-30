# Awesome Agent Orchestrators [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of tools and frameworks for orchestrating AI coding agents.

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
- [agent-of-empires](https://github.com/agent-of-empires/agent-of-empires) - Pairs a TUI with a matching web view, so the same sessions stay reachable from a phone. Claude Code, Codex, OpenCode, Gemini, Mistral Vibe.
- [agentbox](https://github.com/madarco/agentbox) - Gives each agent its own sandboxed VM — local Docker or cloud via Hetzner, Daytona, Vercel, or E2B — with sub-second checkpoint starts.
- [agterm](https://github.com/umputun/agterm) - Native macOS terminal with named workspaces, a live dashboard, attention states, and a scriptable control API.
- [amux](https://github.com/andyrewlee/amux) - Minimal TUI for spawning parallel coding agents in git worktrees.
- [claude-squad](https://github.com/smtg-ai/claude-squad) - Runs each agent as a detached background session with its own worktree, so work continues after you close the pane. Claude Code, Codex, OpenCode, Amp.
- [cmux](https://github.com/manaflow-ai/cmux) - Ghostty-based macOS terminal with vertical tabs and per-agent notifications, built for keeping many concurrent sessions legible.
- [dmux](https://github.com/standardagents/dmux) - Dev agent multiplexer pairing coding agents with git worktrees over tmux.
- [herdr](https://github.com/ogulcancelik/herdr) - Agent-aware multiplexer with persistent workspaces, tabs, panes, and status detection for CLI coding agents.
- [openkanban](https://github.com/TechDufus/openkanban) - Kanban board for orchestrating coding agents, rendered entirely in the terminal.
- [repomon](https://github.com/AliHamzaAzam/repomon) - Rust TUI that supervises a fleet across many repositories at once, in durable tmux sessions you can approve from your phone.
- [thurbox](https://github.com/Thurbeen/thurbox) - TUI orchestrator with remote SSH sessions, inter-session messaging, and a native code-review view. Works with any CLI agent you define.
- [tmux-ide](https://github.com/wavyrai/tmux-ide) - Turns any project into a tmux IDE from a checked-in `ide.yml`, including preset agent-team layouts.

## Parallel Coding Agents — Desktop & Web

The same parallel-sessions workflow delivered as a desktop app or a browser/mobile dashboard, with diff review and one-click merge.

- [agent-orchestrator](https://github.com/ComposioHQ/agent-orchestrator) - Agentic orchestrator for parallel coding agents.
- [AGX](https://github.com/ramarlina/agx) - Local-first agent orchestrator with parallel execution, wake-work-sleep checkpointing, and human-in-the-loop gates.
- [ai-maestro](https://github.com/23blocks-OS/ai-maestro) - Dashboard for orchestrating Claude, Aider, and Cursor agents across machines.
- [aizen](https://github.com/vivy-company/aizen) - macOS workspace for managing git worktrees with integrated agent sessions.
- [Aperant](https://github.com/AndyMik90/Aperant) - Autonomous multi-session AI coding.
- [automaker](https://github.com/AutoMaker-Org/automaker) - Autonomous AI development studio.
- [Better Agent](https://github.com/ofekron/better-agent) - Local web workspace for running and supervising native Claude, Codex, and Gemini sessions with parallel delegation, persistent state, approvals, files, and restart recovery.
- [Claude Command Center (CCC)](https://github.com/amirfish1/claude-command-center) - Local dashboard for spawning, monitoring, and resuming parallel Claude Code, Codex, Cursor, Antigravity, and Kilo Code sessions.
- [clave](https://github.com/codika-io/clave) - Native macOS app for running multiple Claude Code sessions in parallel with split/grid layouts, session groups, SSH remote sessions, and usage analytics. Local-first and MIT.
- [clideck](https://github.com/rustykuntz/clideck) - WhatsApp-like dashboard for managing multiple AI coding agents (Claude Code, Codex, Gemini CLI, OpenCode) in one browser window. Live status, session resume, autopilot routing between agents, and full control from a phone while away.
- [cmux](https://github.com/manaflow-ai/cmux) - Open-source platform for running multiple coding agents in parallel.
- [CodeNomad](https://github.com/NeuralNomadsAI/CodeNomad) - The command center that puts AI coding on steroids.
- [collaborator](https://github.com/collaborator-ai/collab-public) - A place to create with agents.
- [CompanyHelm](https://github.com/CompanyHelm/companyhelm) - Distributed multi-agent orchestrator with task management and agent-to-agent conversations
- [constellagent](https://github.com/owengretzinger/constellagent) - macOS app for running multiple AI agents with their own terminal, editor, and git worktree.
- [crystal](https://github.com/stravu/crystal) - Run multiple Codex and Claude Code sessions in parallel git worktrees.
- [defract](https://defract.dev) — macOS app that runs your Claude Code agents through a structured story → design → architecture → implementation → review lifecycle, with a visual design stage. Local-first; bring your own Anthropic key.
- [dmux](https://github.com/standardagents/dmux) - Parallel agents with tmux and worktrees.
- [dorothy](https://github.com/Charlie85270/Dorothy) - Desktop app to orchestrate multiple AI CLI agents with automations, Kanban management, and MCP servers.
- [Emdash](https://github.com/generalaction/emdash) - Run multiple coding agents in parallel.
- [humanlayer](https://github.com/humanlayer/humanlayer) - Get AI coding agents to solve hard problems in complex codebases.
- [IM.codes](https://github.com/im4codes/imcodes) - Mobile/web control layer for Claude Code, Codex, Gemini CLI, and other terminal-based coding agents, built for away-from-desk continuation with terminal access, file browsing, git views, localhost preview, notifications, scheduled tasks, and multi-agent workflows.
- [ivy-tendril](https://github.com/Ivy-Interactive/Ivy-Tendril) - Open-source AI coding orchestrator that manages Claude Code, Codex, Antigravity, Copilot, and OpenCode through a plan-based lifecycle with verification gates, self-improving memory, and human-in-the-loop checkpoints. ([tendril.ivy.app](https://tendril.ivy.app))
- [jat](https://github.com/joewinke/jat) - The World's First Agentic IDE.
- [jean](https://github.com/coollabsio/jean) - Desktop & web app for orchestrating coding agents (Claude, Codex, OpenCode) across projects and git worktrees.
- [mux](https://github.com/coder/mux) - A desktop app for isolated, parallel agentic development.
- [nimbalyst](https://github.com/nimbalyst/nimbalyst) - The open-source visual workspace for building with Codex, Claude Code. Parallel sessions, git worktrees, kanban, visual editing.
- [octomux](https://github.com/ShreyPaharia/octomux) - Local dashboard for running parallel Claude Code and Cursor agents, each in its own git worktree, with a unified permission inbox, live monitor grid, and in-app diff review. MIT.
- [Orca](https://github.com/stablyai/orca) - IDE for running multiple CLI coding agents side-by-side across isolated git worktrees.
- [parallel-code](https://github.com/johannesjo/parallel-code) - Desktop app for orchestrating multiple AI coding agents (Claude Code, Codex CLI, Gemini CLI) simultaneously in isolated git worktrees with built-in diff viewer and one-click merge.
- [Proliferate](https://github.com/proliferate-ai/proliferate) - Open-source local and cloud agent IDE for running Claude Code, Codex, Gemini CLI, and other coding agents in parallel across isolated workspaces.
- [supacode](https://github.com/supabitapp/supacode) - Native macOS coding agent orchestrator.
- [superset](https://github.com/superset-sh/superset) - A terminal built for coding agents.
- [synara](https://github.com/Emanuele-web04/synara) - A GUI desktop workspace for running and managing AI coding agents across local projects.
- [t3code](https://github.com/pingdotgg/t3code) - Minimal web GUI for coding agents.
- [takopi](https://github.com/banteg/takopi) - Telegram bridge for codex, claude code, opencode, pi.
- [tlbx](https://github.com/tlbx-ai/tlbx) - Self-hosted browser workspace for running Claude Code, Codex, OpenCode, and other CLI agents in parallel across persistent real PTY sessions on your own machines, with control from any browser or phone.
- [vibe-kanban](https://github.com/BloopAI/vibe-kanban) - Kanban board for managing AI coding agents.
- [vibe-tree](https://github.com/sahithvibudhi/vibe-tree) - Vibe code with Claude in parallel git worktrees.
- [vibecraft](https://github.com/rayzhudev/vibecraft) - An RTS-style workspace for managing AI coding agents.

## Multi-Agent Swarms

Systems where multiple specialized agents actively coordinate, communicate, and delegate toward a shared goal.

- [5dive](https://github.com/5dive-ai/5dive) - Named agents on a shared org chart and backlog hand work to each other and escalate to a human over Telegram. Claude Code, Codex, Grok, Antigravity, OpenCode.
- [Agent Teams](https://github.com/777genius/agent-teams-ai) - Desktop app where teams take a high-level command and handle it themselves via inter-agent messaging, Kanban, and built-in code review.
- [agent-kanban](https://github.com/saltbo/agent-kanban) - Leader-worker task board with cryptographic agent identity. Claude Code, Codex, Gemini CLI.
- [agentsmesh](https://github.com/AgentsMesh/AgentsMesh) - Remote AI workstations with PTY sandboxes and worktree isolation, coordinating across channels and pod bindings. Claude Code, Codex, Gemini CLI, Aider, OpenCode.
- [Agon](https://github.com/AutoResearch-Factory/Agon) - Orchestrates scientist, coder, and auditor loops from research topic through proposal to experiment.
- [buzz](https://github.com/block/buzz) - Agents are first-class members of shared channels on a Nostr relay you own, with their own keys and audit trails. Claude Code, Codex, Goose.
- [claude_codex_bridge](https://github.com/SeemSeam/claude_codex_bridge) - Workspace for mixing different vendors' CLI agents in one visible collaboration session.
- [ClawTeam](https://github.com/HKUDS/ClawTeam) - Agents spawn and manage their own teammates from one command, coordinating through file-based or P2P inboxes across tmux worktrees.
- [CompanyHelm](https://github.com/CompanyHelm/companyhelm) - Distributed orchestrator with task management and direct agent-to-agent conversations.
- [Fusion](https://github.com/Runfusion/Fusion) - Multi-node orchestrator with a kanban board, plan-review-execute gates, per-task worktrees, and hierarchical missions.
- [gastown](https://github.com/gastownhall/gastown) - Scales to 20-30 agents with a coordinator, git-backed issue tracking, health watchdogs, and a Bors-style merge queue.
- [hcom](https://github.com/aannoo/hcom) - Lets agents message, watch, and spawn each other across terminals. Claude Code, Codex, Antigravity, Cursor, OpenCode, Kilo, and more.
- [kodo](https://github.com/ikamensh/kodo) - Directs agents through work cycles where a separate agent independently verifies each result. Claude Code, Codex, Gemini CLI.
- [loki-mode](https://github.com/asklokesh/loki-mode) - PRD-to-deployed-product SDLC with 41 agents in 8 swarms, nine quality gates, and blind three-reviewer code review. Source-available under BUSL-1.1.
- [multi-agent-shogun](https://github.com/yohey-w/multi-agent-shogun) - Shogun to karo to ashigaru hierarchy running up to 10 agents over tmux with no coordination API cost.
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
- [LoopTroop](https://github.com/looptroop-ai/LoopTroop) - An LLM council plans the work, then Ralph-style loops retry failed units with fresh context. Executes via OpenCode worktrees.
- [MartinLoop](https://github.com/Keesan12/martin-loop) - Caps spend, enforces policy, verifies output, and rolls back failures, leaving inspectable run receipts.
- [ralph-claude-code](https://github.com/frankbria/ralph-claude-code) - Development loop for Claude Code with exit detection that recognizes when the work is actually finished.
- [ralph-orchestrator](https://github.com/mikeyobrien/ralph-orchestrator) - Hat-based orchestration that keeps agents looping until done, as a fuller implementation of the Ralph Wiggum technique.
- [ralph-tui](https://github.com/subsy/ralph-tui) - Drives an agent through a task list autonomously, with a TUI for watching the loop.
- [ralphex](https://github.com/umputun/ralphex) - Executes an implementation plan autonomously with a fresh session per task, plus validation, retries, multi-phase review, and automatic commits. Claude Code, Codex.
- [toryo](https://github.com/JesseRWeigel/toryo) - Trust-based delegation with quality ratcheting that commits improvements and reverts regressions. Chains Claude Code, Aider, Gemini CLI, Ollama.

## Autonomous Task Runners

Unattended agents driven by an external source — an issue queue, a work board, or a schedule — that run and sync state back without side-by-side supervision.

- [aeon](https://github.com/aeonfun/aeon) - Runs unattended on GitHub Actions with 90+ skills, quality scoring, self-healing, and reactive triggers.
- [background-agents](https://github.com/ColeMurray/background-agents) - Sessions trigger from a web UI, Slack, GitHub, Linear, webhooks, or cron, run in Modal, Daytona, Vercel, E2B, or OpenComputer sandboxes, and open attributed PRs.
- [centaur](https://github.com/paradigmxyz/centaur) - Multiplayer self-hosted agents with Slack-native conversations, Kubernetes sandboxes, shared tools, and durable workflows.
- [claude-code-action](https://github.com/anthropics/claude-code-action) - Anthropic's official GitHub Action, detecting from context whether to answer, review, or implement. Auth via Anthropic API, Bedrock, Vertex, or Foundry.
- [codex-action](https://github.com/openai/codex-action) - OpenAI's official GitHub Action, running Codex CLI headlessly under drop-sudo, unprivileged-user, or fully read-only sandboxes.
- [cyrus](https://github.com/cyrusagents/cyrus) - Watches Linear, GitHub, GitLab, and Slack issues assigned to it, spinning up an isolated worktree per issue. Claude Code, Codex, Cursor, Gemini.
- [gh-aw](https://github.com/github/gh-aw) - Compiles agentic workflows written in Markdown into GitHub Actions YAML. Read-only by default, with writes only through sanitized safe-outputs. Copilot, Claude, Codex, Gemini.
- [lalph](https://github.com/tim-smart/lalph) - Orchestrator driven by whichever source of issues you point it at.
- [multica](https://github.com/multica-ai/multica) - Managed agents platform where you assign tasks, track progress, and let agents compound skills between runs.
- [open-swe](https://github.com/langchain-ai/open-swe) - Invoked from Slack, Linear, or GitHub comments; each task runs in its own cloud sandbox and ends in a draft PR linked to the ticket.
- [OpenHands](https://github.com/OpenHands/OpenHands) - Self-hostable control center running its own agent or driving Claude Code, Codex, and any Agent Client Protocol agent, on schedules or webhooks.
- [remote-swe-agents](https://github.com/aws-samples/remote-swe-agents) - Serverless control plane on Lambda with a dedicated EC2 worker per session, triggered by issue comments, assignments, and PR reviews.
- [run-gemini-cli](https://github.com/google-github-actions/run-gemini-cli) - Google's official GitHub Action, running on event or schedule triggers or on demand via `@gemini-cli /review` and `/triage`.
- [sortie](https://github.com/sortie-ai/sortie) - Turns tracker tickets into agent sessions. Agent-agnostic and tracker-agnostic, as a single Go binary with SQLite persistence.
- [symphony](https://github.com/openai/symphony) - Turns project work into isolated autonomous runs, so teams manage the work rather than supervise the agent.

## Agent Infrastructure & Primitives

Control planes, coordination protocols, harness adapters, and runtimes — the layer beneath your agents rather than the surface you work in.

- [agent-runbook](https://github.com/KnoxOps/agent-runbook) - Compiles YAML runbooks with loops, branching, and parallelism into SKILL.md files for Claude Code and Codex.
- [Agentlas OS](https://github.com/agentlas-ai/Agentlas-OS) - Keeps specialist agents in a hub and spins up a temporary orchestrator per task, with A2A routing and governed memory gates. Formerly Hephaestus.
- [agenttier](https://github.com/agenttier/agenttier) - Kubernetes runtime giving each agent its own Pod and PVC sandbox behind a default-deny NetworkPolicy, with a streaming SSE invoke API.
- [Claudexor](https://github.com/razzant/claudexor) - Routes one coding thread across harnesses with quota-aware rotation between subscription profiles, Best-of-N runs, and cross-family review.
- [codecast](https://github.com/codecast-sh/codecast) - Watches your real local sessions and surfaces them in a live triage inbox, keeping a searchable record with line-level agent attribution. Claude Code, Codex, Cursor, Gemini.
- [guild](https://github.com/mathomhaus/guild) - Shared context, memory, and task coordination as a single Go binary over local SQLite with hybrid keyword and semantic search.
- [handoff](https://github.com/dazuiba/handoff) - Delegates a task to DeepSeek, Codex, or Claude from inside your current Claude Code or Codex session, returning the result automatically.
- [LionClaw](https://github.com/moshthepitt/lionclaw) - Local control plane running coding agents as durable, auditable workers with explicit state, skills, and checkpoints.
- [NemoClaw](https://github.com/NVIDIA/NemoClaw) - Runs Hermes, LangChain Deep Agents, and OpenClaw inside NVIDIA OpenShell with managed inference.
- [neuralyzer](https://github.com/gintasz/neuralyzer) - Lets an agent wipe its own session context and re-run the first message, making Ralph loops easier to engineer.
- [omnigent](https://github.com/omnigent-ai/omnigent) - Meta-harness running Claude Code, Codex, Cursor, OpenCode, Hermes, Pi, or custom YAML agents against swappable sandbox backends, with policy enforcement.
- [openfang](https://github.com/RightNow-AI/openfang) - Open-source agent operating system.
- [sandbox-agent](https://github.com/rivet-dev/sandbox-agent) - Daemon, HTTP/SSE API, and TypeScript SDK for driving six coding agents inside E2B, Daytona, Modal, Cloudflare Containers, or Docker.
- [skillfold](https://github.com/byronxlg/skillfold) - Declares skills in YAML and pins exact revisions in a lockfile so installs are reproducible across Claude Code and Codex.
- [sub-agents-skills](https://github.com/shinpr/sub-agents-skills) - Portable Markdown definitions that route a task to a chosen backend, model, effort level, and permission set.

## Personal Assistants

Always-on agents you reach over chat or a desktop app. They remember across sessions, run on their own schedule, and hand work off to tools and other agents — coding agents included, though the work isn't limited to code.

- [assistant](https://github.com/kcosr/assistant) - Panel-based assistant whose plugins share one workspace of notes, lists, and objects.
- [automata](https://github.com/sentientwave/automata) - Matrix-native workspace where Temporal-backed durable workflows survive restarts and keep long tasks moving.
- [Coworker](https://github.com/accomplish-ai/coworker) - Open source AI coworker that lives on your desktop. Formerly accomplish.
- [denchclaw](https://github.com/DenchHQ/DenchClaw) - Managed OpenClaw framework aimed at CRM, sales automation, and outreach.
- [ghostclaw](https://github.com/b1rdmania/ghostclaw) - An AI that lives on your computer and does things for you.
- [hermes-agent](https://github.com/NousResearch/hermes-agent) - Self-improving harness with persistent cross-session memory and auto-generated skill documents.
- [Hivekeep](https://github.com/MarlBurroW/hivekeep) - Self-hosted team of specialized agents with persistent memory that delegate and build their own tools and mini-apps. Telegram, Slack, Discord, Matrix. Single container, MIT.
- [ironclaw](https://github.com/nearai/ironclaw) - Agent OS in Rust focused on privacy, security, and extensibility.
- [lemon](https://github.com/z80dev/lemon) - Local-first assistant and coding agent runtime.
- [leon](https://github.com/leon-ai/leon) - Long-running open-source personal assistant with voice and text interfaces.
- [lobsterai](https://github.com/netease-youdao/LobsterAI) - Desktop-grade agent for data analysis, slides, docs, and web research.
- [lucinate](https://github.com/lucinate-ai/lucinate) - Terminal-native chat client for OpenClaw, Hermes, Ollama, and OpenAI-compatible providers, with cron management and session browsing.
- [MetaClaw](https://github.com/aiming-lab/MetaClaw) - Assistant that learns and evolves from conversation alone.
- [nanobot](https://github.com/HKUDS/nanobot) - Ultra-lightweight self-hosted assistant in Python with WebUI, tools, memory, MCP, and multi-agent workflows.
- [nanoclaw](https://github.com/nanocoai/nanoclaw) - Lightweight OpenClaw alternative running in containers, connecting to WhatsApp, Telegram, Slack, Discord, and Gmail.
- [nullclaw](https://github.com/nullclaw/nullclaw) - Fully autonomous assistant infrastructure written in Zig.
- [openclaw](https://github.com/openclaw/openclaw) - Your own personal AI assistant, on any OS and any platform.
- [picoclaw](https://github.com/sipeed/picoclaw) - Tiny and fast assistant deployable anywhere.
- [QwenPaw](https://github.com/agentscope-ai/QwenPaw) - Personal assistant that deploys to your own machine or the cloud and plugs into multiple chat apps. Formerly CoPaw.
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
