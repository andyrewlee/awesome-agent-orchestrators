# Awesome Agent Orchestrators [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of tools and frameworks for orchestrating AI coding agents.

## Parallel Coding Agents — Terminal (TUI/CLI)

Run and supervise multiple independent coding-agent sessions side-by-side from a terminal — tmux panes, git worktrees, and TUI/CLI dashboards.

- [agent-deck](https://github.com/asheshgoplani/agent-deck) - Terminal session manager for AI coding agents.
- [agent-of-empires](https://github.com/njbrake/agent-of-empires) - A terminal session manager for AI coding agents on Linux and macOS.
- [agentbox](https://github.com/madarco/agentbox) - Run multiple coding agents in parallel, each teleported into its own sandboxed box (local Docker or cloud VMs via Hetzner/Daytona/Vercel/E2B) with sub-1s checkpoint starts. Works with Claude Code, Codex, and OpenCode.
- [amux](https://github.com/andyrewlee/amux) - TUI for easily running parallel coding agents.
- [claude-squad](https://github.com/smtg-ai/claude-squad) - Manage multiple AI terminal agents in background.
- [dmux](https://github.com/standardagents/dmux) - Parallel agents with tmux and worktrees.
- [herdr](https://github.com/ogulcancelik/herdr) - Agent-aware terminal multiplexer with persistent workspaces, tabs, panes, and status detection for CLI coding agents.
- [openkanban](https://github.com/techdufus/openkanban) - TUI kanban board for orchestrating AI coding agents.
- [repomon](https://github.com/AliHamzaAzam/repomon) - A Rust TUI that spawns and supervises many AI coding agents at once across multiple repositories and git worktrees. Agents run in durable tmux sessions; the ones waiting on you float to the top, and you can approve a prompt from your phone.
- [subtask](https://github.com/zippoxer/subtask) - Claude Skill to do tasks with subagents in Git worktrees.
- [thurbox](https://github.com/Thurbeen/thurbox) - Multi-session TUI orchestrator that runs many coding-agent CLIs (Claude Code, Codex, opencode, Aider, Copilot, and any CLI you define) in persistent tmux sessions, with git worktree isolation, remote SSH sessions, inter-session messaging, and a native code-review view. ([thurbox.thurbeen.eu](https://thurbox.thurbeen.eu))
- [tmux-ide](https://github.com/wavyrai/tmux-ide) - Tmux-powered terminal IDE with `ide.yml` layouts, agent-team templates, and Claude Code integration.

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
- [dorothy](https://github.com/Charlie85270/Dorothy) - Desktop app to orchestrate multiple AI CLI agents with automations, Kanban management, and MCP servers.
- [Emdash](https://github.com/generalaction/emdash) - Run multiple coding agents in parallel.
- [Garcon](https://github.com/cfal/garcon) - Self-hosted browser and mobile workspace for running and steering parallel Claude Code, Codex, Cursor Agent, OpenCode, Amp, Droid, and Pi sessions, with integrated terminal, files, diff review, Git/PR workflows, mobile approvals, scheduling, and cross-agent transfers.
- [humanlayer](https://github.com/humanlayer/humanlayer) - Get AI coding agents to solve hard problems in complex codebases.
- [Hyperlane](https://github.com/Akkento/hyperlane) - A VS Code-based IDE that runs coding agents in parallel across worktrees. In-editor PR review, terminal multiplexer, Node and React profilers, design-mode inspector, indexed search, extensions. Supports Claude Code, Codex, OpenCode, Gemini CLI, and any CLI or ACP agent.
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

- [5dive](https://github.com/5dive-ai/5dive) - Run a company of named AI agents on a server you own, each with its own model, memory, and role. Agents share an org chart and backlog, hand work to each other, and escalate to a human over Telegram. Multi-runtime (Claude Code, Codex, Grok, Antigravity, opencode).
- [Agent Teams](https://github.com/777genius/agent-teams-ai) - Desktop app where you give high-level commands to autonomous AI agent teams across Claude, Codex, and OpenCode, and agents handle the work themselves with inter-agent messaging, Kanban task management, and built-in code review. Supports 200+ models and 75+ LLM providers.
- [agent-kanban](https://github.com/saltbo/agent-kanban) - Agent-first kanban board with leader-worker model, cryptographic agent identity, and multi-runtime support (Claude Code, Codex, Gemini CLI).
- [agentsmesh](https://github.com/AgentsMesh/AgentsMesh) - The AI Agent Workforce Platform. Spin up remote AI workstations (AgentPods) with PTY sandboxes and git worktree isolation, coordinate multi-agent collaboration across channels and pod bindings, and manage tasks with a built-in Kanban. Self-hostable with BYOK. Supports Claude Code, Codex CLI, Gemini CLI, Aider, and OpenCode.
- [Agon](https://github.com/AutoResearch-Factory/Agon) - Autonomous research system that orchestrates scientist, coder, and auditor loops from topic to idea, proposal, and experiment.
- [buzz](https://github.com/block/buzz) - Self-hosted workspace where humans and AI agents collaborate in shared channels on a Nostr relay you own. Agents are first-class members with their own keys and audit trails, and can open repos, send patches, review code, run workflows, and orchestrate each other. Works with Claude Code, Codex, and Goose across desktop, web, CLI, and mobile.
- [claude-flow](https://github.com/ruvnet/claude-flow) - Deploy multi-agent swarms with coordinated workflows.
- [claude_code_bridge](https://github.com/bfly123/claude_code_bridge) - Real-time multi-AI collaboration.
- [ClawTeam](https://github.com/HKUDS/ClawTeam) - Agent Swarm Intelligence (One Command → Full Automation).
- [Fusion](https://github.com/Runfusion/Fusion) - Multi-node, multi-platform agent orchestrator with a kanban board, plan-review-execute workflow gates, per-task git worktrees, and hierarchical missions.
- [gastown](https://github.com/steveyegge/gastown) - Multi-agent orchestration system with persistent work tracking.
- [hcom](https://github.com/aannoo/hcom) - Hook your AI coding agents together so they can message, watch, and spawn each other across terminals.
- [kodo](https://github.com/ikamensh/kodo) - Autonomous multi-agent coding orchestrator that directs Claude Code, Codex, and Gemini CLI agents through work cycles with independent verification.
- [loki-mode](https://github.com/asklokesh/loki-mode) - Autonomous SDLC orchestrator: PRD-to-deployed-product. 41 specialized agents in 8 swarms (engineering, ops, business, data, product, growth, review, orchestration), RARV cycles (Reason-Act-Reflect-Verify), 9 quality gates, blind 3-reviewer code review, anti-sycophancy completion council. Multi-provider (Claude Code full; Codex/Gemini/Cline/Aider degraded). Local-first, open-source, BUSL-1.1.
- [multi-agent-shogun](https://github.com/yohey-w/multi-agent-shogun) - Samurai-inspired tmux orchestrator with a shogun → karo → ashigaru hierarchy for running up to 10 parallel AI coding agents (Claude Code, Codex, Copilot, Kimi) with zero coordination API cost.
- [orc](https://github.com/spencermarx/orc) - Hierarchical multi-agent orchestrator that coordinates AI coding agents through planning, task decomposition, isolated worktrees, and review pipelines.
- [ORCH](https://github.com/oxgeneral/ORCH) - CLI runtime for managing Claude Code, Codex, and Cursor as typed agent teams with state machine, goals, and TUI.
- [Orkas](https://github.com/Orkas-AI/Orkas) - Open-source, local-first desktop AI workforce where a Commander decomposes goals and coordinates specialist agents in parallel or sequence with isolated skills and memory. Supports BYOK and local model endpoints, and can drive Claude Code, Codex, OpenCode, and Cline across macOS, Windows, and Linux. ([orkas.ai](https://orkas.ai?source=github_awesome_agent_orchestrators))
- [paperclip](https://github.com/paperclipai/paperclip) - Orchestration for zero-human companies.
- [scion](https://github.com/GoogleCloudPlatform/scion) - Multi-agent orchestration testbed that runs AI agents in parallel isolated containers with separate workspaces, dynamic coordination, and normalized telemetry.
- [shire](https://github.com/victor36max/shire) - Persistent workspaces for AI agent teams with inter-agent mailboxes, shared drive, and full context preservation. Supports Claude Code, OpenCode, Pi Agent and more.
- [tutti](https://github.com/nutthouse/tutti) - Multi-agent orchestration CLI with config-driven workflows, git worktree isolation, and typed artifact flow between agents.

## Autonomous Loop Runners

Projects implementing the "keep running until done" pattern — a single goal driven through a retry-until-verified loop.

- [bernstein](https://github.com/chernistry/bernstein) - Deterministic orchestrator — spawns parallel AI coding agents (Claude Code, Codex CLI, Gemini CLI), verifies with tests, auto-commits. Zero LLM tokens on coordination.
- [Dex](https://github.com/francescoalemanno/dex) - Structured Ralph orchestrator with human-gated planning, programmatic task tracking, parallel multi-reviewer code review, automatic retries with backoff, and autonomous dead-end-aware research loops inspired by Karpathy's autoresearch; supports 7 CLI backends and ships cross-platform binaries.
- [LoopTroop](https://github.com/looptroop-ai/LoopTroop) - Local GUI orchestrator for long-running AI coding tasks with LLM council planning, OpenCode execution in isolated git worktrees, and Ralph-style recovery loops that retry failed beads with fresh context.
- [MartinLoop](https://github.com/Keesan12/martin-loop) - Control plane for AI coding agents with hard budget stops, verifier gates, rollback evidence, and inspectable run receipts.
- [ralph-claude-code](https://github.com/frankbria/ralph-claude-code) - Autonomous AI development loop for Claude Code with intelligent exit detection.
- [ralph-orchestrator](https://github.com/mikeyobrien/ralph-orchestrator) - Hat-based orchestration that keeps agents in a loop until done.
- [ralph-tui](https://github.com/subsy/ralph-tui) - Orchestrate AI coding agents to work through task lists autonomously.
- [toryo](https://github.com/JesseRWeigel/toryo) - Intelligent agent orchestrator with trust-based delegation, quality ratcheting (git commit/revert), and Ralph Loop retries. Chains Claude Code, Aider, Gemini CLI, Ollama.

## Autonomous Task Runners

Unattended agents driven by an external source — an issue queue, a work board, or a schedule — that run and sync state back without side-by-side supervision.

- [aeon](https://github.com/aaronjmars/aeon) - Autonomous agent framework that runs unattended on GitHub Actions; 90+ skills with quality scoring, self-healing, persistent memory, and reactive triggers.
- [centaur](https://github.com/paradigmxyz/centaur) - Self-hosted team agent platform with Slack-native conversations, Kubernetes sandboxes, shared tools, and durable workflows.
- [lalph](https://github.com/tim-smart/lalph) - LLM agent orchestrator driven by your chosen source of issues.
- [multica](https://github.com/multica-ai/multica) - Agent-first kanban board, multi-runtime support.
- [sortie](https://github.com/sortie-ai/sortie) - Turns issue tracker tickets into autonomous coding agent sessions. Agent-agnostic, tracker-agnostic, single Go binary with SQLite persistence.
- [symphony](https://github.com/openai/symphony) - Turns project work into isolated, autonomous implementation runs.

## Agent Infrastructure & Primitives

Building blocks rather than runnable orchestrators: coordination protocols, sandboxes and runtimes, shared-memory backends, and skill compilers other tools build on.

- [agent-runbook](https://github.com/KnoxOps/agent-runbook) - Python CLI that compiles contract-based YAML runbooks into SKILL.md files for Claude Code and Codex. Define multi-step agent workflows with loops, branching, parallelism, and file-based state passing — write the runbook once, generate executable skills with one command.
- [agenttier](https://github.com/agenttier/agenttier) - Kubernetes-native runtime that runs each AI coding agent in its own Pod + PVC sandbox, with default-deny NetworkPolicy and a streaming SSE invoke API. Run multiple agents in parallel by creating multiple Sandbox CRs.
- [codecast](https://github.com/codecast-sh/codecast) - See, steer, and remember every coding agent session across machines. Watches your real local Claude Code, Codex, Cursor, and Gemini sessions, surfaces them in a live triage inbox you can steer from web, desktop, or phone, and keeps a searchable team record with line-level agent attribution (cast blame). MIT and self-hostable. ([codecast.sh](https://codecast.sh))
- [guild](https://github.com/mathomhaus/guild) - Shared context, memory, and task coordination across AI coding agents. Single Go binary, local SQLite, hybrid keyword and semantic search.
- [handoff](https://github.com/dazuiba/handoff) - Delegate tasks to DeepSeek V4, Codex, or Claude Opus right inside your Claude Code / Codex session. Runs in background; result returns automatically.
- [Hephaestus](https://github.com/agentlas-ai/Hephaestus) - Open Agent OS for Claude Code, Codex, and Cursor with a meta-agent builder, A2A Hub routing, local ontology, and governed memory/security gates.
- [LionClaw](https://github.com/moshthepitt/lionclaw) - Secure-first local AI assistant with durable sessions and installable skills.
- [MetaClaw](https://github.com/aiming-lab/MetaClaw) - Just talk to your agent — it learns and evolves.
- [NemoClaw](https://github.com/NVIDIA/NemoClaw) - NVIDIA plugin for secure installation of OpenClaw.
- [neuralyzer](https://github.com/gintasz/neuralyzer) - Allow agent to wipe its own session context and re-run the first message. Easier and more ergonomic Ralph loop engineering.
- [openfang](https://github.com/RightNow-AI/openfang) - Open-source Agent Operating System.
- [skillfold](https://github.com/byronxlg/skillfold) - Configuration language and compiler for multi-agent AI pipelines. Compiles YAML config into agent skills for Claude Code, Cursor, Codex, Copilot, Gemini CLI, and Windsurf.

## Personal Assistants

General-purpose assistants you reach through messaging platforms or a desktop/terminal surface, backed by memory, skills, and scheduling.

- [accomplish](https://github.com/accomplish-ai/accomplish) - Open source AI coworker that lives on your desktop.
- [assistant](https://github.com/kcosr/assistant) - Panel-based personal assistant with a plugin architecture for productivity workflows.
- [automata](https://github.com/sentientwave/automata) - Agent swarming organization system.
- [CoPaw](https://github.com/agentscope-ai/CoPaw) - Your Personal AI Assistant.
- [denchclaw](https://github.com/DenchHQ/denchclaw) - Managed OpenClaw framework for CRM, sales automation, and outreach agents.
- [ghostclaw](https://github.com/b1rdmania/ghostclaw) - An AI agent that lives on your computer and works for you.
- [hermes-agent](https://github.com/NousResearch/hermes-agent) - The agent that grows with you.
- [ironclaw](https://github.com/nearai/ironclaw) - OpenClaw-inspired implementation in Rust focused on privacy and security.
- [lemon](https://github.com/z80dev/lemon) - Local-first assistant and coding agent system.
- [leon](https://github.com/leon-ai/leon) - Open-source personal assistant with voice and text interfaces.
- [lettabot](https://github.com/letta-ai/lettabot) - Your personal AI assistant that remembers everything.
- [lobsterai](https://github.com/netease-youdao/lobsterai) - Your 24/7 all-scenario AI agent that gets work done for you.
- [lucinate](https://github.com/lucinate-ai/lucinate) - Go-based terminal-native TUI chat client for OpenClaw, Hermes, and any OpenAI-compatible endpoint. Streaming responses, markdown rendering, tool call cards, local skills, cron management, session browsing, thinking control, and multi-agent support. Cross-platform, MIT licensed.
- [nanobot](https://github.com/HKUDS/nanobot) - Ultra-lightweight personal AI assistant.
- [nanoclaw](https://github.com/gavrielc/nanoclaw) - Lightweight alternative to OpenClaw that runs in Apple containers for security.
- [nullclaw](https://github.com/nullclaw/nullclaw) - Fastest, smallest, and fully autonomous AI assistant infrastructure.
- [openclaw](https://github.com/openclaw/openclaw) - Your own personal AI assistant.
- [picoclaw](https://github.com/sipeed/picoclaw) - Ultra-efficient AI assistant.
- [rho](https://github.com/mikeyobrien/rho) - An AI agent that stays running, remembers across sessions, and checks in on its own.
- [rowboat](https://github.com/rowboatlabs/rowboat) - Open-source AI coworker, with memory.
- [zclaw](https://github.com/tnm/zclaw) - The smallest possible AI personal assistant for ESP32.
- [zeroclaw](https://github.com/zeroclaw-labs/zeroclaw) - Fast, small, and fully autonomous AI assistant infrastructure.

## Resting

A watchlist of projects without a push in the last few months (checked 2026-07-21). They stay here until they're active again, then move back up.

- [1code](https://github.com/21st-dev/1code) - UI for Claude Code with local and remote agent execution. _(last commit 2026-03; archived)_
- [antfarm](https://github.com/snarktank/antfarm) - Build your agent team in OpenClaw with one command. _(last commit 2026-02)_
- [ariana](https://github.com/ariana-dot-dev/ariana) - The IDE of the future. _(last commit 2026-03)_
- [babyagi3](https://github.com/yoheinakajima/babyagi3) - A minimal AI agent you configure once, then run through natural language. _(last commit 2026-03)_
- [cashclaw](https://github.com/moltlaunch/cashclaw) - An autonomous agent that takes work, does work, gets paid, and gets better at it. _(last commit 2026-03)_
- [clawe](https://github.com/getclawe/clawe) - Multi-agent coordination system: think Trello for OpenClaw agents. _(last commit 2026-02)_
- [CodexMonitor](https://github.com/Dimillian/CodexMonitor) - Orchestrate multiple Codex agents across local workspaces. _(last commit 2026-03)_
- [crystal](https://github.com/stravu/crystal) - Run multiple Codex and Claude Code sessions in parallel git worktrees. _(last commit 2026-02)_
- [gnap](https://github.com/farol-team/gnap) - Git-Native Agent Protocol: coordinate multiple agents via a shared git repo acting as a persistent task board (todo/doing/done), no orchestrator process required. _(last commit 2026-03)_
- [mercury](https://github.com/Michaelliv/mercury) - Personal AI assistant that lives where you chat. _(last commit 2026-03; archived)_
- [opengoat](https://github.com/marian2js/opengoat) - Build AI autonomous organizations of OpenClaw agents. _(last commit 2026-04)_
- [ralphy](https://github.com/michaelshimeles/ralphy) - Runs AI agents on tasks until done. _(last commit 2026-02)_
- [swarm-protocol](https://github.com/phuryn/swarm-protocol) - Headless coordination layer exposed as MCP server: claim work, detect file conflicts, heartbeat, and hand off tasks across agent sessions. _(last commit 2026-03)_
- [wit](https://github.com/amaar-mc/wit) - Coordination protocol that locks specific functions (not files) via Tree-sitter AST parsing. Agents declare intents, acquire symbol level locks, and get conflict warnings before writing code. _(last commit 2026-03)_
- [wreckit](https://github.com/mikehostetler/wreckit) - Run Ralph Wiggum Loop over your roadmap. _(last commit 2026-04)_
