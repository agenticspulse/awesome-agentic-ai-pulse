<div align="center">

# ⚡ Awesome Agentic AI Pulse

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/agenticspulse/awesome-agentic-ai-pulse?style=flat-square)](https://github.com/agenticspulse/awesome-agentic-ai-pulse/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/agenticspulse/awesome-agentic-ai-pulse?style=flat-square)](https://github.com/agenticspulse/awesome-agentic-ai-pulse/commits/main)
[![Maintained by AgenticsPulse](https://img.shields.io/badge/Maintained%20by-AgenticsPulse-blue?style=flat-square)](https://agenticspulse.com)

<br/>

> **The definitive curated list of production-grade autonomous multi-agent frameworks, protocols, observability tools, and architectural patterns for 2026.**

<p align="center">
Agentic systems have moved beyond demos. This repository tracks the frameworks, protocols, and tooling that actually ship in production — with emphasis on state management, observability, safety, and measurable reliability. Maintained by <a href="https://agenticspulse.com"><b>AgenticsPulse</b></a>.
</p>

</div>

---

## 📑 Table of Contents

- [2026 Agent Frameworks Benchmark](#-definitive-2026-agent-frameworks-benchmark)
- [Model Context Protocol (MCP) Ecosystem](#-model-context-protocol-mcp-production-ecosystem)
- [Agent Observability, Evaluation & Safety](#-agent-observability-evaluation--safety-stack)
- [Architectural Guides & Tools](#-exclusive-architectural-guides--tools)
- [Multi-Agent Orchestration Frameworks](#-multi-agent-orchestration-frameworks)
- [Autonomous Coding & Developer Agents](#-autonomous-coding--developer-agents)
- [Browser & Desktop Automation](#-browser--desktop-automation-agents)
- [Memory, RAG & Knowledge Layers](#-agent-memory-rag--vector-layers)
- [Contributing](#-contributing)
- [License](#-license)

---

## 📊 Definitive 2026 Agent Frameworks Benchmark

Comparison of the most widely adopted frameworks for building production multi-agent systems (as of mid-2026). Scores reflect real-world enterprise adoption, state durability, and operational maturity.

| Framework              | Core Architecture                  | State / Checkpointing                          | Multi-Model Support      | Enterprise Score (1-10) | Best For                                      |
|------------------------|------------------------------------|------------------------------------------------|--------------------------|-------------------------|-----------------------------------------------|
| **LangGraph**          | Explicit directed graphs           | Excellent – durable checkpoints, time-travel, human-in-the-loop | Strong (any LangChain-compatible) | **9.2**                | Complex, long-running, auditable workflows    |
| **CrewAI**             | Role-based hierarchical crews      | Good – shared memory + task context            | Strong                   | **8.4**                | Rapid multi-specialist content & research pipelines |
| **AutoGen**            | Conversational multi-agent         | Moderate – conversation history + external stores | Strong                 | **7.6**                | Exploratory research & human-collaborative agents |
| **Semantic Kernel**    | Plugin + planner oriented          | Good – native with enterprise backends         | Excellent (C#/Python/Java) | **8.7**              | Enterprise integration with existing .NET/Java stacks |
| **LlamaIndex Workflows**| Event-driven workflows            | Good – event state + persistence options       | Strong                   | **8.1**                | Data-intensive & RAG-centric agent pipelines  |
| **OpenAI Swarm / Operator** | Lightweight agent handoff       | Lightweight – external state required          | Native OpenAI            | **7.3**                | Fast, tool-centric operators & simple swarms  |

> **Notes**: Enterprise Score combines production readiness, observability hooks, documentation quality, and observed adoption in regulated environments. LangGraph currently leads for systems that require deterministic audit trails and GEO-style compliance gates.

---

## 🔌 Model Context Protocol (MCP) Production Ecosystem

[Model Context Protocol](https://modelcontextprotocol.io) has become the standard way for agents to discover and call external tools securely. Below are high-utility, production-oriented MCP servers.

### Databases & Structured Data
- **[MCP Postgres](https://github.com/modelcontextprotocol/servers)** — Official reference server for PostgreSQL (query, schema inspection, safe writes).
- **[MCP SQLite](https://github.com/modelcontextprotocol/servers)** — Lightweight local database access.
- **[Supabase MCP](https://github.com/supabase-community)** — Community servers for Supabase (Auth, DB, Storage).

### Web Scraping & Browser
- **[Browserbase / Stagehand MCP](https://www.browserbase.com)** — Reliable browser sessions with stealth and observability.
- **[Firecrawl MCP](https://www.firecrawl.dev)** — Clean markdown extraction and site crawling for agent context.
- **[Playwright MCP servers](https://github.com/microsoft/playwright)** — Community wrappers exposing Playwright capabilities via MCP.

### File Systems & Developer Workflows
- **[Filesystem MCP](https://github.com/modelcontextprotocol/servers)** — Controlled file read/write with path allow-listing.
- **[GitHub MCP](https://github.com/modelcontextprotocol/servers)** — Repo inspection, PR creation, issue management.
- **[Git MCP](https://github.com/modelcontextprotocol/servers)** — Local git operations for coding agents.

### Productivity & Knowledge
- **[Notion / Slack / Linear MCP servers](https://github.com/modelcontextprotocol/servers)** — Growing set of official and community connectors.
- **[Memory MCP patterns](https://modelcontextprotocol.io)** — Reference implementations for persistent agent memory.

> Prefer servers that implement proper authentication, rate limiting, and structured error responses. Avoid unmaintained community servers in production paths.

---

## 🔍 Agent Observability, Evaluation & Safety Stack

Production multi-agent systems fail in non-obvious ways: infinite loops, silent tool failures, cost explosions, and subtle hallucinations. These tools are currently the strongest options for visibility and control.

### Tracing & Observability
- **[Langfuse](https://langfuse.com)** — Open-source LLM engineering platform. Excellent self-hosted tracing, prompt management, and cost analytics.
- **[Arize Phoenix](https://phoenix.arize.com)** — Open-source observability focused on tracing, evaluations, and latency analysis. Strong OpenTelemetry support.
- **[LangSmith](https://smith.langchain.com)** — Deep integration with LangChain/LangGraph ecosystems. Dataset-based evaluation and production monitoring.
- **[AgentOps](https://www.agentops.ai)** — Agent-specific analytics, session replay, and cost tracking.

### Evaluation & Safety
- **[Braintrust](https://www.braintrust.dev)** — Enterprise evaluation platform with strong support for agent trajectories.
- **[Helicone](https://www.helicone.ai)** — Proxy-based cost monitoring, caching, and rate limiting.
- **[Guardrails AI](https://www.guardrailsai.com)** / **[NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails)** — Input/output validation and topical control.
- **Loop & recursion detection** — Prefer frameworks with native step limits and graph-level cycle detection (LangGraph checkpointing is particularly effective here).

### Recommended Minimal Stack (2026)
1. LangGraph or CrewAI for orchestration
2. Langfuse or Phoenix for tracing
3. Structured output + tool-call validation
4. Explicit recursion limits + human-in-the-loop checkpoints on high-stakes paths

---

## 📖 Exclusive Architectural Guides & Tools

In-depth technical blueprints and free tools published by the AgenticsPulse team:

- **[Generative Engine Optimization (GEO) in 2026 Guide](https://agenticspulse.com/posts/generative-engine-optimization-geo-ai-agents-guide-2026.html)** — How to optimize content and agent pipelines for citations in Perplexity, SearchGPT, and Grok. Includes production LangGraph audit node patterns.
- **[Building a Production MCP Server in n8n (SSE & JSON-RPC)](https://agenticspulse.com/posts/building-production-mcp-server-n8n-guide.html)** — End-to-end guide to exposing reliable tools via the Model Context Protocol.
- **[Real-Time LLM Token & Reasoning Cost Calculator](https://agenticspulse.com/tools/llm-pricing-calculator.html)** — Free developer utility for modeling multi-agent token budgets and cost scenarios.
- **[Agent Observability Patterns for Production Multi-Agent Workflows](https://agenticspulse.com/posts/agent-observability-patterns-production-guide.html)** — Practical patterns for tracing, cost attribution, and failure isolation across agent graphs.

These resources are maintained as living documents and frequently referenced by teams building production agent systems.

---

## 🤖 Multi-Agent Orchestration Frameworks

- **[LangGraph](https://github.com/langchain-ai/langgraph)** — Graph-based orchestration with durable state, checkpointing, and human-in-the-loop primitives. Current production leader for complex workflows.
- **[CrewAI](https://github.com/crewAIInc/crewAI)** — Role-based multi-agent framework optimized for hierarchical process design and rapid development.
- **[AutoGen](https://github.com/microsoft/autogen)** — Conversational multi-agent framework from Microsoft. Flexible group-chat and tool-use patterns.
- **[Semantic Kernel](https://github.com/microsoft/semantic-kernel)** — Enterprise SDK with strong support for C#, Python, and Java. Excellent for integrating LLMs into existing application stacks.
- **[LlamaIndex Workflows](https://github.com/run-llama/llama_index)** — Event-driven workflows particularly strong for data and RAG-centric agents.
- **[OpenAI Swarm](https://github.com/openai/swarm)** — Lightweight experimental framework focused on agent handoff and simplicity.
- **[MetaGPT](https://github.com/geekan/MetaGPT)** — Multi-agent framework that assigns software-company roles (PM, Architect, Engineer) to LLMs.
- **[PydanticAI](https://github.com/pydantic/pydantic-ai)** — Type-safe agent framework built on Pydantic. Strong structured output and dependency injection.
- **[Mastra](https://github.com/mastra-ai/mastra)** — TypeScript-first agent framework with growing momentum.

---

## 💻 Autonomous Coding & Developer Agents

- **[Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code)** — Anthropic’s agentic terminal coding agent. Strong at codebase navigation, git operations, and multi-step implementation.
- **[Aider](https://github.com/Aider-AI/aider)** — Terminal-based AI pair programmer that works directly with local git repositories.
- **[OpenHands](https://github.com/All-Hands-AI/OpenHands)** (formerly OpenDevin) — Open-source platform for autonomous software engineering agents.
- **[Cursor](https://cursor.com)** — AI-native code editor with deep agentic features and repository-wide context.
- **[Windsurf](https://codeium.com/windsurf)** — Cascade-powered agentic IDE focused on multi-file reasoning.
- **[Continue](https://github.com/continuedev/continue)** — Open-source autopilot for VS Code and JetBrains.

---

## 🌐 Browser & Desktop Automation Agents

- **[Browser-Use](https://github.com/browser-use/browser-use)** — Open-source library connecting LLMs directly to browser sessions. High momentum in 2026.
- **[Stagehand / Browserbase](https://www.browserbase.com)** — Production browser infrastructure with observability and stealth capabilities.
- **[Anthropic Computer Use](https://docs.anthropic.com/en/docs/build-with-claude/computer-use)** — Native computer-use capabilities allowing Claude to control mouse, keyboard, and screen.
- **[Playwright + LLM patterns](https://playwright.dev)** — Widely used combination for reliable, scriptable browser agents.
- **[Skyvern](https://github.com/Skyvern-AI/skyvern)** — Open-source browser agent focused on form filling and workflow automation using vision + LLMs.

---

## 🧠 Agent Memory, RAG & Vector Layers

- **[Mem0](https://github.com/mem0ai/mem0)** — Dedicated memory layer for personalized AI agents.
- **[Zep](https://github.com/getzep/zep)** — Long-term memory and knowledge graph store designed for agents.
- **[LangGraph Memory / Checkpointers](https://langchain-ai.github.io/langgraph/)** — Built-in durable state and memory primitives.
- **[Qdrant](https://qdrant.tech)** — High-performance vector database frequently used in production RAG + agent stacks.
- **[Chroma](https://www.trychroma.com)** — Lightweight embedding database popular for prototyping.
- **[Graphiti](https://github.com/getzep/graphiti)** / knowledge-graph approaches — Emerging patterns for temporal and relational agent memory.

---

## 🤝 Contributing

We welcome high-quality additions that help practitioners build more reliable agentic systems.

### What We Accept
- Actively maintained open-source frameworks and tools
- Production-relevant MCP servers with clear documentation
- Observability, evaluation, and safety tools with demonstrated utility
- High-signal architectural patterns or reference implementations

### What We Generally Reject
- Unmaintained or abandoned projects
- Pure marketing landing pages without usable code
- Duplicate entries of already-listed tools
- Low-effort “AI wrapper” repositories

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/add-framework-name`)
3. Add your entry in the appropriate section, following existing formatting
4. Keep descriptions concise, factual, and free of hype
5. Commit with a clear message (`git commit -m 'Add ProjectName – short description'`)
6. Push and open a Pull Request

Please include:
- Official repository or documentation link
- One-sentence factual description
- Any notable production characteristics (state management, observability, license)

Maintainers reserve the right to edit descriptions for clarity and consistency.

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

---

**Stay ahead of production agentic systems.**

Deep technical guides, benchmarks, and architecture patterns → [AgenticsPulse.com](https://agenticspulse.com)

Maintained with care by the AgenticsPulse team.
