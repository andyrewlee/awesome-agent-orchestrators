<!-- source-refs
  - README.md
-->

# Awesome Agent Orchestrators [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Uma lista curada de ferramentas e frameworks para orquestrar agentes.

Tudo aqui decide em que um agente trabalha, quando executa, onde executa ou o que acontece com sua saída, e assume qualquer tarefa para a qual você o aponte. Bots de propósito único e coisas que um agente apenas consome — backends de memória, servidores MCP, provedores de sandbox, bibliotecas de skills — estão fora do escopo.

## Como escolher

- **Execute vários agentes ao mesmo tempo e revise cada diff.** [Terminal](#parallel-coding-agents--terminal-tuicli) se você vive no tmux; [Desktop e Web](#parallel-coding-agents--desktop--web) se você prefere uma interface gráfica ou acesso pelo celular.
- **Mantenha um agente trabalhando enquanto você está ausente.** Os [Executores de Loop Autônomos](#autonomous-loop-runners) conduzem um único objetivo até verificá-lo. Os [Executores de Tarefas Autônomos](#autonomous-task-runners) puxam trabalho de um rastreador de issues, de um quadro ou de um agendamento.
- **Deixe os agentes dividirem um trabalho grande entre si.** [Enxames Multiagente](#multi-agent-swarms).
- **Mande mensagem para um agente em vez de abrir uma ferramenta.** Os [Assistentes Pessoais](#personal-assistants) permanecem em execução, lembram entre sessões e pegam trabalho de uma thread de chat — tarefas gerais, não apenas código.
- **Construa seu próprio orquestrador.** [Infraestrutura e Primitivas de Agentes](#agent-infrastructure--primitives) — planos de controle, protocolos de coordenação, adaptadores de harness e runtimes.

## Agentes de Codificação em Paralelo — Terminal (TUI/CLI)

Execute e supervisione várias sessões de agentes lado a lado a partir de um terminal — painéis tmux, git worktrees e dashboards TUI.

- [agent-console](https://github.com/buhuipao/agent-console) - TUI em Rust que encontra sessões do Codex e do Claude Code a partir das próprias transcrições dos provedores, inclusive as iniciadas em outro lugar, e retoma a interface nativa delas em vez de substituí-la. Sem tmux ou worktrees.
- [agent-deck](https://github.com/asheshgoplani/agent-deck) - Uma única TUI cobrindo sessões de Claude Code, Codex, Gemini e OpenCode, com status ao vivo e retomada para cada uma.
- [agent-of-empires](https://github.com/agent-of-empires/agent-of-empires) - Emparelha uma TUI com uma visão web correspondente, para que as mesmas sessões permaneçam acessíveis pelo celular. Claude Code, Codex, OpenCode, Gemini, Mistral Vibe.
- [agentbox](https://github.com/madarco/agentbox) - Dá a cada agente sua própria VM com sandbox — Docker local ou nuvem via Hetzner, Daytona, Vercel ou E2B — com inicialização de checkpoints em menos de um segundo.
- [agterm](https://github.com/umputun/agterm) - Terminal nativo para macOS com espaços de trabalho nomeados, dashboard ao vivo, estados de atenção e API de controle programável.
- [amux](https://github.com/andyrewlee/amux) - TUI mínima para lançar agentes de codificação em paralelo em git worktrees.
- [claude-squad](https://github.com/smtg-ai/claude-squad) - Executa cada agente como uma sessão em segundo plano destacada com seu próprio worktree, para que o trabalho continue depois que você fechar o painel. Claude Code, Codex, OpenCode, Amp.
- [cmux](https://github.com/manaflow-ai/cmux) - Terminal para macOS baseado em Ghostty, com abas verticais e notificações por agente, criado para manter muitas sessões simultâneas legíveis.
- [dmux](https://github.com/standardagents/dmux) - Multiplexador de agentes de desenvolvimento que combina agentes de codificação com git worktrees via tmux.
- [herdr](https://github.com/ogulcancelik/herdr) - Multiplexador ciente de agentes, com espaços de trabalho persistentes, abas, painéis e detecção de status para agentes de codificação de CLI.
- [openkanban](https://github.com/TechDufus/openkanban) - Quadro kanban para orquestrar agentes de codificação, renderizado inteiramente no terminal.
- [repomon](https://github.com/AliHamzaAzam/repomon) - TUI em Rust que supervisiona uma frota em vários repositórios ao mesmo tempo, em sessões tmux duráveis que você pode aprovar pelo celular.
- [thurbox](https://github.com/Thurbeen/thurbox) - Orquestrador TUI com sessões SSH remotas, mensagens entre sessões e visão nativa de revisão de código. Funciona com qualquer agente de CLI que você definir.
- [tmux-ide](https://github.com/wavyrai/tmux-ide) - Transforma qualquer projeto em uma IDE tmux a partir de um `ide.yml` versionado, incluindo layouts predefinidos de times de agentes.

## Agentes de Codificação em Paralelo — Desktop e Web

O mesmo fluxo de trabalho de sessões paralelas como aplicativo de desktop ou dashboard de navegador/celular, com revisão de diff e merge.

- [agent-orchestrator](https://github.com/Untrivial-ai/agent-orchestrator) - IDE de agentes para frotas que planeja o trabalho, lança os agentes e depois corrige falhas de CI e conflitos de merge sem que você precise pedir.
- [agent-squid](https://github.com/agent-squid/squid) - Interface de navegador organizada em faixas nomeadas (`#topic@agent`), com contexto compartilhado entre agentes e medidor de cota em tempo real.
- [AGX](https://github.com/ramarlina/agx) - Checkpointing wake-work-sleep mantém um time de agentes persistente em objetivos longos, com portões humanos entre ciclos.
- [ai-maestro](https://github.com/23blocks-OS/ai-maestro) - Dashboard que abrange várias máquinas, adicionando busca em memória, consultas a grafos de código e mensagens entre agentes. Claude, Aider, Cursor.
- [aizen](https://github.com/vivy-company/aizen) - Espaço de trabalho para macOS que organiza worktrees, ambientes e sessões de agentes por projeto.
- [Aperant](https://github.com/AndyMik90/Aperant) - Executa até 12 terminais de agentes com um loop de QA de autovalidação e resolução automática de conflitos ao mesclar de volta na main.
- [automaker](https://github.com/AutoMaker-Org/automaker) - Descreva funcionalidades em um quadro Kanban e os agentes as implementam em worktrees isoladas, executando testes e fazendo commits ao longo do caminho.
- [bb](https://github.com/get-bb/bb) - IDE autocontrolada que orquestra vários agentes de codificação em threads ao vivo que você pode acompanhar, direcionar ou repassar, dirigida por aplicativo de desktop, aplicativo web, CLI ou API HTTP.
- [Better Agent](https://github.com/ofekron/better-agent) - Espaço de trabalho web local com estado persistente, aprovações e recuperação após reinício para sessões nativas do Claude, Codex e Gemini.
- [Claude Command Center (CCC)](https://github.com/amirfish1/claude-command-center) - Dashboard local para lançar, monitorar e retomar sessões de Claude Code, Codex, Cursor, Antigravity e Kilo Code.
- [clave](https://github.com/codika-io/clave) - Aplicativo nativo para macOS com layouts em divisão e grade, grupos de sessões, sessões SSH remotas e análise de uso para Claude Code.
- [clideck](https://github.com/rustykuntz/clideck) - Dashboard no estilo de aplicativo de chat com roteamento automático entre agentes e controle total pelo celular. Claude Code, Codex, Gemini CLI, OpenCode.
- [CodeNomad](https://github.com/NeuralNomadsAI/CodeNomad) - Espaço de trabalho de desktop e web em torno do CLI do OpenCode cujos SideCars incorporam ferramentas locais como VS Code e terminais como abas.
- [collaborator](https://github.com/collabs-inc/collab-public) - Organiza terminais, editores e arquivos como blocos em uma tela infinita de pan-e-zoom em vez de abas.
- [constellagent](https://github.com/owengretzinger/constellagent) - Aplicativo para macOS que dá a cada agente seu próprio terminal, editor e git worktree em uma única janela.
- [diri](https://github.com/cristicretu/diri) - Aplicativo nativo para macOS que executa Claude Code, Codex, Cursor, Gemini e shells em paralelo em git worktrees ou hosts remotos, com status ao vivo, persistência de sessões entre reinícios, um resumo na barra de menus e um servidor MCP para os agentes lançarem uns aos outros.
- [dorothy](https://github.com/Charlie85270/Dorothy) - Aplicativo de desktop que combina orquestração de agentes com automações, gestão Kanban e servidores MCP.
- [Emdash](https://github.com/generalaction/emdash) - Ambiente de desenvolvimento orientado a agentes executando agentes em paralelo em qualquer provedor de modelos.
- [Fletch](https://github.com/fwdai/fletch) - IDE nativa para macOS que isola cada agente em seu próprio clone do repositório sob Seatbelt ou Docker, serve a cada um um índice compartilhado de símbolos e grafo de chamadas via MCP e condiciona cada passo a testes ou à sua aprovação. Claude Code, Codex, Cursor, OpenCode.
- [Garcon](https://github.com/cfal/garcon) - Espaço de trabalho auto-hospedado para navegador e celular com revisão de diff, fluxos de Git/PR, aprovações pelo celular, agendamento e transferências entre agentes. Sete agentes de CLI.
- [GraphCode](https://github.com/scgopi/GraphCode) - Aplicativo para macOS que conecta sessões de agentes em um grafo: cada nó é um terminal ao vivo ao qual você pode se anexar no meio da execução; cada aresta é uma passada de bastão, mensagem ou lançamento que dispara enquanto você está ausente. Claude Code, Copilot CLI, Codex.
- [humanlayer](https://github.com/humanlayer/humanlayer) - Controle com humano no processo para agentes de codificação em problemas difíceis; o repositório observa que seu código está em grande parte obsoleto em favor de uma reconstrução.
- [IM.codes](https://github.com/im4codes/imcodes) - Camada de controle para celular e web criada para continuidade fora do computador, com acesso a terminal, visualizações de git, pré-visualização de localhost e tarefas agendadas. Claude Code, Codex, Gemini CLI.
- [ivy-tendril](https://github.com/Ivy-Interactive/Ivy-Tendril) - Conduz agentes por um ciclo de vida baseado em planos com portões de verificação, memória que se autoaperfeiçoa e checkpoints humanos. Claude Code, Codex, Antigravity, Copilot, OpenCode.
- [jat](https://github.com/joewinke/jat) - Dashboard visual que combina sessões ao vivo, gestão de tarefas, editor de código e terminal, com fluxos de trabalho de enxame em paralelo.
- [jean](https://github.com/coollabsio/jean) - Aplicativo de desktop e web para orquestrar agentes em vários projetos e seus git worktrees. Claude, Codex, OpenCode.
- [kandev](https://github.com/kdlbs/kandev) - Bancada kanban cujos fluxos de trabalho de várias etapas atribuem um agente diferente por etapa atrás de portões humanos, executando localmente, no Docker, via SSH ou em executores de nuvem.
- [mux](https://github.com/coder/mux) - Aplicativo de desktop para desenvolvimento orientado a agentes isolado e paralelo.
- [nimbalyst](https://github.com/nimbalyst/nimbalyst) - Espaço de trabalho visual que combina sessões paralelas de worktrees com kanban e edição visual direta. Claude Code, Codex, OpenCode.
- [octomux](https://github.com/ShreyPaharia/octomux) - Dashboard local com visão de frota em kanban, uma caixa de entrada unificada de permissões entre agentes e revisão de diff no aplicativo.
- [Orca](https://github.com/stablyai/orca) - Ambiente de desenvolvimento orientado a agentes para executar uma frota na sua própria assinatura, disponível em desktop e celular.
- [Ouijit](https://github.com/ouijit/ouijit) - Quadro kanban e terminais conectados por hooks de ciclo de vida, scripts e um CLI ciente de sessões, para que uma tarefa seja executada manualmente, por script ou delegada ao agente. Worktrees por tarefa, sandbox de VM opcional. Claude Code, Codex, Pi, OpenCode.
- [parallel-code](https://github.com/johannesjo/parallel-code) - Aplicativo de desktop que executa Claude Code, Codex e Gemini CLI lado a lado em worktrees isoladas, com visualizador de diff integrado e merge em um clique.
- [Proliferate](https://github.com/proliferate-ai/proliferate) - IDE de agentes que executa sessões localmente ou na nuvem e permite que você construa fluxos de trabalho reutilizáveis a partir delas.
- [qm](https://github.com/yc-software/qm) - Harness multijogador em que cada colega de time recebe um espaço de trabalho isolado para executar agentes de forma independente, acionado pelo Slack ou pela web.
- [supacode](https://github.com/supabitapp/supacode) - Central de comando nativa para macOS para desenvolvimento de um worktree por agente.
- [superset](https://github.com/superset-sh/superset) - Editor de código construído em torno da execução de muitos agentes na sua máquina ao mesmo tempo.
- [synara](https://github.com/Emanuele-web04/synara) - Espaço de trabalho de desktop com GUI para executar e gerenciar agentes em projetos locais.
- [t3code](https://github.com/pingdotgg/t3code) - Superfície de controle de harness disponível como aplicativo web, mobile e desktop. Claude Code, Codex, Cursor, Grok Build, OpenCode.
- [takopi](https://github.com/banteg/takopi) - Ponte para Telegram que coloca sessões do Codex, Claude Code, OpenCode e Pi em uma thread de chat.
- [Tempest](https://github.com/tempestai-dev/tempest) - ADE de desktop em Tauri executando agentes de CLI em worktrees isoladas em paralelo, com um grafo local compartilhado de conhecimento de código que reduz o uso de tokens entre sessões, além de status ao vivo e revisão de diff/PR integrada.
- [tlbx](https://github.com/tlbx-ai/tlbx) - Espaço de trabalho de navegador auto-hospedado que mantém sessões PTY reais persistentes nas suas próprias máquinas, acessível de qualquer navegador ou celular.
- [Traycer](https://github.com/traycerai/traycer) - Espaço de trabalho traga-seu-próprio-agente executando muitas sessões em paralelo com contexto compartilhado entre modelos e provedores, além de mensagens entre agentes, quadros compartilháveis e sincronização entre dispositivos.
- [vibe-tree](https://github.com/sahithvibudhi/vibe-tree) - Um git worktree por agente, entregue em desktop, web e CLI.
- [vibecraft](https://github.com/rayzhudev/vibecraft) - Espaço de trabalho no estilo RTS para comandar agentes de codificação.

## Enxames Multiagente

Sistemas em que vários agentes especializados coordenam, comunicam e delegam ativamente em direção a um objetivo compartilhado.

- [5dive](https://github.com/5dive-ai/5dive) - Agentes nomeados em um organograma e backlog compartilhados passam trabalho uns aos outros e escalam para um humano via Telegram. Claude Code, Codex, Grok, Antigravity, OpenCode.
- [Agent Teams](https://github.com/777genius/agent-teams-ai) - Aplicativo de desktop em que os times recebem um comando de alto nível e o resolvem por conta própria via mensagens entre agentes, Kanban e revisão de código integrada.
- [agent-kanban](https://github.com/saltbo/agent-kanban) - Quadro de tarefas líder-trabalhador com identidade criptográfica de agente. Claude Code, Codex, Gemini CLI.
- [agentsmesh](https://github.com/AgentsMesh/AgentsMesh) - Estações de trabalho de IA remotas com sandboxes PTY e isolamento de worktrees, coordenando em canais e associações de pods. Claude Code, Codex, Gemini CLI, Aider, OpenCode.
- [Agon](https://github.com/AutoResearch-Factory/Agon) - Orquestra loops de cientista, programador e auditor, do tópico de pesquisa à proposta e ao experimento.
- [buzz](https://github.com/block/buzz) - Agentes são membros de primeira classe de canais compartilhados em um relay Nostr que você possui, com suas próprias chaves e trilhas de auditoria. Claude Code, Codex, Goose.
- [claude_codex_bridge](https://github.com/SeemSeam/claude_codex_bridge) - Espaço de trabalho para misturar agentes de CLI de diferentes fornecedores em uma única sessão de colaboração visível.
- [ClawTeam](https://github.com/HKUDS/ClawTeam) - Agentes lançam e gerenciam seus próprios colegas a partir de um único comando, coordenando por caixas de entrada baseadas em arquivos ou P2P em worktrees tmux.
- [CompanyHelm](https://github.com/CompanyHelm/companyhelm) - Orquestrador distribuído com gestão de tarefas e conversas diretas entre agentes.
- [Fusion](https://github.com/Runfusion/Fusion) - Orquestrador multinó com quadro kanban, portões de planejar-revisar-executar, worktrees por tarefa e missões hierárquicas.
- [gastown](https://github.com/gastownhall/gastown) - Escala até 20-30 agentes com um coordenador, rastreamento de issues baseado em git, supervisores de saúde e fila de merge no estilo Bors.
- [hcom](https://github.com/aannoo/hcom) - Permite que agentes enviem mensagens, observem e lancem uns aos outros entre terminais. Claude Code, Codex, Antigravity, Cursor, OpenCode, Kilo e outros.
- [kodo](https://github.com/ikamensh/kodo) - Dirige agentes por ciclos de trabalho em que um agente separado verifica cada resultado de forma independente. Claude Code, Codex, Gemini CLI.
- [loki-mode](https://github.com/asklokesh/loki-mode) - SDLC do PRD ao produto implantado com 41 agentes em 8 enxames, nove portões de qualidade e revisão de código cega com três revisores. Código-fonte disponível sob BUSL-1.1.
- [multi-agent-shogun](https://github.com/yohey-w/multi-agent-shogun) - Hierarquia de shogun, karo e ashigaru executando até 10 agentes via tmux sem custo de API de coordenação.
- [NXTG-Forge Orchestrator](https://github.com/nxtg-ai/forge-orchestrator) - Coordena Claude Code, Codex e Gemini CLI em um único repositório compartilhado por um pipeline de pesquisar-planejar-delegar-verificação-adversarial-implantar, com bloqueio de arquivos, captura de conhecimento e detecção de desvios. Um único binário Rust.
- [orc](https://github.com/spencermarx/orc) - Framework leve que se aproveita da sua configuração CLI existente para planejamento, decomposição de tarefas, worktrees e revisão.
- [ORCH](https://github.com/oxgeneral/ORCH) - Runtime de CLI que gerencia agentes como times tipados com uma máquina de estados e objetivos explícitos. Claude Code, Codex, Cursor.
- [Orkas](https://github.com/Orkas-AI/Orkas) - Um agente comandante decompõe objetivos e despacha especialistas com skills e memória isolados. Claude Code, Codex, OpenCode, Cline.
- [paperclip](https://github.com/paperclipai/paperclip) - Plataforma auto-hospedada em que agentes acordam por heartbeats para reivindicar tickets, governados por organogramas, orçamentos e portões de aprovação.
- [ruflo](https://github.com/ruvnet/ruflo) - Meta-harness para implantar enxames coordenados e fluxos de trabalho multiagente conversacionais. Antes chamado de claude-flow.
- [scion](https://github.com/GoogleCloudPlatform/scion) - Ambiente de testes de orquestração executando agentes em contêineres isolados em paralelo, com coordenação dinâmica e telemetria normalizada.
- [shire](https://github.com/victor36max/shire) - Espaços de trabalho de time persistentes com caixas de correio entre agentes e unidade compartilhada. Claude Code, OpenCode, Pi.
- [tutti](https://github.com/nutthouse/tutti) - Fluxos de trabalho orientados a configuração passando artefatos tipados entre agentes, cada um em seu próprio worktree.

## Executores de Loop Autônomos

O padrão "continue rodando até concluir" — um único objetivo conduzido por um loop de repetição até a verificação.

- [bernstein](https://github.com/sipyourdrink-ltd/bernstein) - Não mantém nenhum modelo no loop de coordenação, então a orquestração custa zero tokens. Verifica com testes e faz auto-commits em mais de 40 agentes de CLI.
- [Dex](https://github.com/francescoalemanno/dex) - Planejamento com portão humano, revisão de código com múltiplos revisores e loops de pesquisa cientes de becos sem saída, distribuído como binários multiplataforma para 7 backends de CLI.
- [fractal](https://github.com/plasma-ai/fractal) - Loops que delegam recursivamente subtarefas separáveis a agentes filhos, limitados por limites configuráveis de profundidade, custo e tempo.
- [LoopTroop](https://github.com/looptroop-ai/LoopTroop) - Um conselho de LLMs planeja o trabalho, e então loops no estilo Ralph repetem unidades com falha com contexto novo. Executa via worktrees do OpenCode.
- [MartinLoop](https://github.com/Keesan12/martin-loop) - Limita gastos, aplica políticas, verifica a saída e reverte falhas, deixando recibos de execução inspecionáveis.
- [ralph-claude-code](https://github.com/frankbria/ralph-claude-code) - Loop de desenvolvimento para Claude Code com detecção de saída que reconhece quando o trabalho está realmente concluído.
- [ralph-orchestrator](https://github.com/mikeyobrien/ralph-orchestrator) - Orquestração baseada em chapéus que mantém agentes em loop até concluir, como uma implementação mais completa da técnica Ralph Wiggum.
- [ralph-tui](https://github.com/subsy/ralph-tui) - Conduz um agente por uma lista de tarefas de forma autônoma, com uma TUI para observar o loop.
- [ralphex](https://github.com/umputun/ralphex) - Executa um plano de implementação de forma autônoma com uma sessão nova por tarefa, além de validação, repetições, revisão em várias fases e commits automáticos. Claude Code, Codex.
- [toryo](https://github.com/JesseRWeigel/toryo) - Delegação baseada em confiança com elevação progressiva de qualidade que commita melhorias e reverte regressões. Encadeia Claude Code, Aider, Gemini CLI, Ollama.

## Executores de Tarefas Autônomos

Agentes sem supervisão acionados por uma fonte externa — uma fila de issues, um quadro de trabalho ou um agendamento — que executam e sincronizam o estado de volta sem supervisão lado a lado.

- [aeon](https://github.com/aeonfun/aeon) - Executa sem supervisão no GitHub Actions; despacha skills para seis harnesses de agentes de codificação sob um único contrato (Claude Code, Grok, Codex, Pi, Vibe, Kimi), com pontuação de qualidade, memória persistida em git, loop de autocorreção e gatilhos reativos.
- [background-agents](https://github.com/ColeMurray/background-agents) - Sessões disparadas por uma interface web, Slack, GitHub, Linear, webhooks ou cron, executadas em sandboxes Modal, Daytona, Vercel, E2B ou OpenComputer, e abrem PRs atribuídos.
- [centaur](https://github.com/paradigmxyz/centaur) - Agentes auto-hospedados multijogador com conversas nativas do Slack, sandboxes Kubernetes, ferramentas compartilhadas e fluxos de trabalho duráveis.
- [claude-code-action](https://github.com/anthropics/claude-code-action) - GitHub Action oficial da Anthropic, detectando pelo contexto se deve responder, revisar ou implementar. Autenticação via Anthropic API, Bedrock, Vertex ou Foundry.
- [codex-action](https://github.com/openai/codex-action) - GitHub Action oficial da OpenAI, executando o Codex CLI de forma headless em sandboxes drop-sudo, de usuário sem privilégios ou totalmente somente leitura.
- [Contrabass](https://github.com/junhoyeo/contrabass) - Orquestrador que prioriza o terminal para execuções de agentes orientadas a issues, puxando trabalho do Linear, GitHub Issues ou de um quadro local para git worktrees, com modos TUI, headless e dashboard.
- [cyrus](https://github.com/cyrusagents/cyrus) - Observa issues do Linear, GitHub, GitLab e Slack atribuídas a ele, criando um worktree isolado por issue. Claude Code, Codex, Cursor, Gemini.
- [Factory](https://github.com/owainlewis/factory) - Mantém agentes de codificação trabalhando em um repositório sem exigir que um humano orquestre cada passo a partir de um terminal, puxando tarefas de filas de tickets confiáveis para espaços de trabalho Codex isolados.
- [gh-aw](https://github.com/github/gh-aw) - Compila fluxos de trabalho orientados a agentes escritos em Markdown em YAML do GitHub Actions. Somente leitura por padrão, com gravações apenas por safe-outputs sanitizados. Copilot, Claude, Codex, Gemini.
- [lalph](https://github.com/tim-smart/lalph) - Orquestrador impulsionado por qualquer fonte de issues para a qual você o apontar.
- [multica](https://github.com/multica-ai/multica) - Plataforma de agentes gerenciados em que você atribui tarefas, acompanha o progresso e deixa os agentes acumularem skills entre execuções.
- [open-swe](https://github.com/langchain-ai/open-swe) - Acionado por comentários no Slack, Linear ou GitHub; cada tarefa executa em sua própria sandbox na nuvem e termina em um PR de rascunho vinculado ao ticket.
- [OpenHands](https://github.com/OpenHands/OpenHands) - Central de controle auto-hospedável executando seu próprio agente ou dirigindo Claude Code, Codex e qualquer agente do Agent Client Protocol, por agendamentos ou webhooks.
- [remote-swe-agents](https://github.com/aws-samples/remote-swe-agents) - Plano de controle serverless no Lambda com um worker EC2 dedicado por sessão, acionado por comentários em issues, atribuições e revisões de PR.
- [run-gemini-cli](https://github.com/google-github-actions/run-gemini-cli) - GitHub Action oficial do Google, executando por gatilhos de evento ou agendamento ou sob demanda via `@gemini-cli /review` e `/triage`.
- [sortie](https://github.com/sortie-ai/sortie) - Transforma tickets de rastreadores em sessões de agentes. Agnóstico de agente e de rastreador, como um único binário Go com persistência SQLite.
- [symphony](https://github.com/openai/symphony) - Transforma o trabalho do projeto em execuções autônomas isoladas, para que os times gerenciem o trabalho em vez de supervisionar o agente.

## Infraestrutura e Primitivas de Agentes

Planos de controle, protocolos de coordenação, adaptadores de harness e runtimes — a camada abaixo dos seus agentes, e não a superfície na qual você trabalha.

- [agent-runbook](https://github.com/KnoxOps/agent-runbook) - Compila runbooks YAML com loops, ramificações e paralelismo em arquivos SKILL.md para Claude Code e Codex.
- [Agentlas OS](https://github.com/agentlas-ai/Agentlas-OS) - Mantém agentes especialistas em um hub e cria um orquestrador temporário por tarefa, com roteamento A2A e portões de memória governados. Antes chamado de Hephaestus.
- [agenttier](https://github.com/agenttier/agenttier) - Runtime Kubernetes que dá a cada agente seu próprio Pod e sandbox PVC atrás de uma NetworkPolicy de negação por padrão, com API de invocação SSE em streaming.
- [Archon](https://github.com/coleam00/Archon) - Construtor de harnesses para fluxos de trabalho de codificação com IA determinísticos, combinando etapas de agentes com scripts, portões de validação, aprovações e git worktrees isolados. Claude Code, Codex e outros.
- [Claudexor](https://github.com/razzant/claudexor) - Roteia uma thread de codificação entre harnesses com rotação ciente de cotas entre perfis de assinatura, execuções Best-of-N e revisão entre famílias.
- [codecast](https://github.com/codecast-sh/codecast) - Observa suas sessões locais reais e as exibe em uma caixa de entrada de triagem ao vivo, mantendo um registro pesquisável com atribuição de agente por linha. Claude Code, Codex, Cursor, Gemini.
- [guild](https://github.com/mathomhaus/guild) - Contexto, memória e coordenação de tarefas compartilhados como um único binário Go sobre SQLite local, com busca híbrida por palavras-chave e semântica.
- [handoff](https://github.com/dazuiba/handoff) - Delega uma tarefa ao DeepSeek, Codex ou Claude de dentro da sua sessão atual de Claude Code ou Codex, retornando o resultado automaticamente.
- [LionClaw](https://github.com/moshthepitt/lionclaw) - Plano de controle local executando agentes de codificação como workers duráveis e auditáveis, com estado, skills e checkpoints explícitos.
- [NemoClaw](https://github.com/NVIDIA/NemoClaw) - Executa Hermes, LangChain Deep Agents e OpenClaw dentro do NVIDIA OpenShell com inferência gerenciada.
- [neuralyzer](https://github.com/gintasz/neuralyzer) - Permite que um agente apague o próprio contexto da sessão e reexecute a primeira mensagem, facilitando a engenharia de loops Ralph.
- [omnigent](https://github.com/omnigent-ai/omnigent) - Meta-harness executando Claude Code, Codex, Cursor, OpenCode, Hermes, Pi ou agentes YAML personalizados contra backends de sandbox intercambiáveis, com aplicação de políticas.
- [openfang](https://github.com/RightNow-AI/openfang) - Sistema operacional de agentes de código aberto.
- [sandbox-agent](https://github.com/rivet-dev/sandbox-agent) - Daemon, API HTTP/SSE e SDK TypeScript para dirigir seis agentes de codificação dentro de E2B, Daytona, Modal, Cloudflare Containers ou Docker.
- [skillfold](https://github.com/byronxlg/skillfold) - Declara skills em YAML e fixa revisões exatas em um lockfile para que as instalações sejam reproduzíveis entre Claude Code e Codex.
- [sub-agents-skills](https://github.com/shinpr/sub-agents-skills) - Definições Markdown portáveis que roteiam uma tarefa para um backend, modelo, nível de esforço e conjunto de permissões escolhidos.

## Assistentes Pessoais

Agentes sempre ativos que você alcança por chat ou aplicativo de desktop. Eles lembram entre sessões, executam em sua própria agenda e repassam trabalho a ferramentas e a outros agentes — incluindo agentes de codificação, embora o trabalho não se limite a código.

- [assistant](https://github.com/kcosr/assistant) - Assistente baseado em painéis cujos plugins compartilham um único espaço de trabalho de notas, listas e objetos.
- [automata](https://github.com/sentientwave/automata) - Espaço de trabalho nativo do Matrix em que fluxos de trabalho duráveis baseados em Temporal sobrevivem a reinícios e mantêm tarefas longas em movimento.
- [Cloudflare OS](https://github.com/cloudflare/cloudflare-os) - "SO de empresa" auto-hospedável no Cloudflare Workers: uma interface de chat em que agentes pré-carregados com o contexto da sua empresa fazem tarefas, constroem aplicativos com sandbox e permanecem dentro de um framework de salvaguardas Gatekeepers.
- [Coworker](https://github.com/accomplish-ai/coworker) - Colega de trabalho de IA de código aberto que vive no seu desktop. Antes chamado de accomplish.
- [denchclaw](https://github.com/DenchHQ/DenchClaw) - Framework OpenClaw gerenciado voltado para CRM, automação de vendas e prospecção.
- [ghostclaw](https://github.com/b1rdmania/ghostclaw) - Uma IA que vive no seu computador e faz coisas por você.
- [hermes-agent](https://github.com/NousResearch/hermes-agent) - Harness que se autoaperfeiçoa com memória persistente entre sessões e documentos de skills gerados automaticamente.
- [Hivekeep](https://github.com/MarlBurroW/hivekeep) - Time auto-hospedado de agentes especializados com memória persistente que delegam tarefas e constroem suas próprias ferramentas e mini-aplicativos. Telegram, Slack, Discord, Matrix. Contêiner único, MIT.
- [ironclaw](https://github.com/nearai/ironclaw) - SO de agentes em Rust focado em privacidade, segurança e extensibilidade.
- [iva](https://github.com/smixs/iva) - Assistente de Telegram que transforma suas mensagens, notas de voz e fotos em um vault de markdown compatível com Obsidian que ele lembra entre sessões. Crons, skills, MCP e Google Workspace por um menu no chat. Auto-hospedado com um único comando, MIT.
- [lemon](https://github.com/z80dev/lemon) - Assistente e runtime de agente de codificação local-first.
- [leon](https://github.com/leon-ai/leon) - Assistente pessoal de código aberto de longa execução com interfaces de voz e texto.
- [lobsterai](https://github.com/netease-youdao/LobsterAI) - Agente em nível de desktop para análise de dados, apresentações, documentos e pesquisa na web.
- [lucinate](https://github.com/lucinate-ai/lucinate) - Cliente de chat nativo de terminal para OpenClaw, Hermes, Ollama e provedores compatíveis com OpenAI, com gestão de crons e navegação de sessões.
- [MetaClaw](https://github.com/aiming-lab/MetaClaw) - Assistente que aprende e evolui apenas com a conversa.
- [nanobot](https://github.com/HKUDS/nanobot) - Assistente auto-hospedado ultraleve em Python com WebUI, ferramentas, memória, MCP e fluxos de trabalho multiagente.
- [nanoclaw](https://github.com/nanocoai/nanoclaw) - Alternativa leve ao OpenClaw executando em contêineres, conectando-se a WhatsApp, Telegram, Slack, Discord e Gmail.
- [nullclaw](https://github.com/nullclaw/nullclaw) - Infraestrutura de assistente totalmente autônoma escrita em Zig.
- [openclaw](https://github.com/openclaw/openclaw) - Seu próprio assistente pessoal de IA, em qualquer SO e qualquer plataforma.
- [Ouroboros](https://github.com/razzant/ouroboros) - Agente de propósito geral com identidade e memória duráveis, automodificação revisada, coordenação multiagente e interfaces de desktop e headless.
- [picoclaw](https://github.com/sipeed/picoclaw) - Assistente minúsculo e rápido implantável em qualquer lugar.
- [QwenPaw](https://github.com/agentscope-ai/QwenPaw) - Assistente pessoal que implanta na sua própria máquina ou na nuvem e se conecta a vários aplicativos de chat. Antes chamado de CoPaw.
- [rho](https://github.com/mikeyobrien/rho) - Permanece em execução, lembra entre sessões e faz check-in por conta própria. macOS, Linux, Android.
- [rowboat](https://github.com/rowboatlabs/rowboat) - Colega de trabalho de IA de código aberto com memória.
- [zclaw](https://github.com/tnm/zclaw) - Assistente pessoal completo em 888 KiB, executando em um ESP32 com GPIO, cron e ferramentas personalizadas.
- [zeroclaw](https://github.com/zeroclaw-labs/zeroclaw) - Infraestrutura de assistente totalmente autônoma, rápida e pequena em Rust, implantável em qualquer lugar.

## Em Repouso

Uma lista de observação de projetos sem push nos últimos meses (verificado em 2026-07-28). Eles permanecem aqui até voltarem a ficar ativos, quando retornam para a lista principal.

- [1code](https://github.com/21st-dev/1code) - Camada de orquestração para Claude Code e Codex. _(último commit 2026-03; arquivado)_
- [antfarm](https://github.com/snarktank/antfarm) - Monte seu time de agentes no OpenClaw com um único comando. _(último commit 2026-02)_
- [ariana](https://github.com/ariana-dot-dev/ariana) - A IDE do futuro. _(último commit 2026-03)_
- [babyagi3](https://github.com/yoheinakajima/babyagi3) - Um agente de IA mínimo que você configura uma vez e depois executa por linguagem natural. _(último commit 2026-03)_
- [cashclaw](https://github.com/moltlaunch/cashclaw) - Um agente autônomo que pega trabalho, executa trabalho, é pago e melhora nisso. _(último commit 2026-03)_
- [clawe](https://github.com/getclawe/clawe) - Sistema de coordenação multiagente: pense em um Trello para agentes OpenClaw. _(último commit 2026-02)_
- [CodexMonitor](https://github.com/Dimillian/CodexMonitor) - Orquestre vários agentes Codex em espaços de trabalho locais. _(último commit 2026-03)_
- [gnap](https://github.com/farol-team/gnap) - Protocolo de agentes nativo de git que coordena agentes por um repositório compartilhado como quadro de tarefas, sem processo orquestrador. _(último commit 2026-03)_
- [lettabot](https://github.com/letta-ai/lettabot) - Assistente pessoal que lembra de tudo. _(último commit 2026-05; arquivado, substituído pelo Letta Code)_
- [mercury](https://github.com/Michaelliv/mercury) - Assistente pessoal de IA que vive onde você conversa. _(último commit 2026-03; arquivado)_
- [opengoat](https://github.com/marian2js/opengoat) - Construa organizações de agentes OpenClaw coordenando entre Codex, Claude Code, Cursor e OpenCode. _(último commit 2026-04)_
- [ralphy](https://github.com/michaelshimeles/ralphy) - Script Bash que coloca Claude Code, Codex, OpenCode, Cursor, Qwen ou Droid em loop até a tarefa ser concluída. _(último commit 2026-02)_
- [subtask](https://github.com/zippoxer/subtask) - Skill do Claude que executa suas tarefas por subagentes em git worktrees. _(último commit 2026-04)_
- [swarm-protocol](https://github.com/phuryn/swarm-protocol) - Coordenação headless via MCP: reivindicar trabalho, detectar conflitos de arquivos, heartbeat e passada de bastão entre sessões. _(último commit 2026-03)_
- [vibe-kanban](https://github.com/BloopAI/vibe-kanban) - Quadro kanban para gerenciar agentes de codificação de IA. _(último commit 2026-04)_
- [wit](https://github.com/amaar-mc/wit) - Bloqueia funções individuais em vez de arquivos via Tree-sitter, avisando os agentes sobre conflitos antes de escreverem. _(último commit 2026-03)_
- [wreckit](https://github.com/mikehostetler/wreckit) - Execute o loop Ralph Wiggum sobre o seu roadmap. _(último commit 2026-04)_