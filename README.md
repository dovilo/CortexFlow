# CortexFlow — AI Agent Reasoning Pipeline Studio

![MiMo Powered](https://img.shields.io/badge/Powered%20by-MiMo%20v2.5--pro-7c3aed?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Live-brightgreen?style=for-the-badge)

> Visual AI agent reasoning pipeline studio powered by Xiaomi MiMo v2.5-pro. Design, debug, and deploy multi-step reasoning chains with a drag-and-drop canvas.

**🌐 Live Demo:** [dovilo.github.io/CortexFlow](https://dovilo.github.io/CortexFlow/)

---

## What is CortexFlow?

CortexFlow is a **visual studio for designing multi-step AI reasoning pipelines**. Unlike traditional agent frameworks that require code, CortexFlow lets you build complex reasoning chains by connecting nodes on a visual canvas — each node is a MiMo-powered reasoning step with real-time execution visualization.

### Key Differentiators

| Feature | CortexFlow | LangChain | AutoGen | CrewAI |
|---|---|---|---|---|
| Visual Pipeline Editor | ✅ | ❌ | ❌ | ❌ |
| Real-Time Debug Console | ✅ | ❌ | ❌ | ❌ |
| Token Flow Visualization | ✅ | ❌ | ❌ | ❌ |
| Node-Based Architecture | ✅ | ❌ | ❌ | ❌ |
| Built-in MiMo Reasoning | ✅ | ❌ | ❌ | ❌ |
| Conditional Branching | ✅ | ✅ | ✅ | ❌ |
| Execution Analytics | ✅ | ❌ | ❌ | ❌ |
| Zero-Code Setup | ✅ | ❌ | ❌ | ❌ |

---

## Architecture

```
┌─────────────────────────────────────────────────────┐
│                  CortexFlow Engine                   │
├─────────────┬─────────────┬─────────────────────────┤
│  Canvas UI  │  Runtime    │  MiMo v2.5-pro          │
│  (React)    │  Executor   │  Reasoning Engine        │
├─────────────┼─────────────┼─────────────────────────┤
│  ┌───┐      │  Scheduler  │  ┌───────────────────┐  │
│  │ 📥│──────┼──►          │  │ Chain-of-Thought  │  │
│  └─┬─┘      │             │  │ Reasoning per Node │  │
│    │        │  Token      │  └───────────────────┘  │
│  ┌─▼─┐      │  Router     │                         │
│  │ 🧠│──────┼──►          │  ┌───────────────────┐  │
│  └─┬─┘      │             │  │ JSON Mode Output   │  │
│    │        │  State      │  └───────────────────┘  │
│  ┌─▼─┐      │  Manager    │                         │
│  │ 🔀│──────┼──►          │  ┌───────────────────┐  │
│  └┬─┬┘      │  Memory     │  │ 128K Context       │  │
│ ┌─▼┐ ┌▼─┐  │  Store      │  └───────────────────┘  │
│ │📤│ │🔧│  │             │                         │
│ └──┘ └──┘  │             │                         │
└─────────────┴─────────────┴─────────────────────────┘
```

---

## 8 Node Types

| Node | Icon | Purpose |
|------|------|---------|
| **Input** | 📥 | Raw data ingestion — text, JSON, API responses |
| **Reason** | 🧠 | MiMo chain-of-thought reasoning step |
| **Tool** | 🔧 | External API calls, web scraping, DB queries |
| **Gate** | 🔀 | Conditional routing based on reasoning output |
| **Memory** | 💾 | Persistent context storage across runs |
| **Transform** | 🔄 | Data reshaping, parsing, formatting |
| **Output** | 📤 | Result delivery — webhook, file, display |
| **Sub-Agent** | 🤖 | Nested pipeline execution |

---

## Features

- **🧠 Visual Pipeline Editor** — Drag-and-drop nodes, connect with bezier curves
- **⚡ Real-Time Debug Console** — Watch tokens flow through each node live
- **🔀 Conditional Branching** — Route execution based on MiMo reasoning
- **💾 Memory Injection** — Persistent memory across pipeline runs
- **🔗 Tool Integration** — Connect APIs, scrapers, databases, blockchain RPCs
- **📊 Execution Analytics** — Token usage, latency, cost tracking per node
- **🎨 Dark Theme** — Built for developers who live in dark mode
- **📱 Responsive** — Works on desktop and tablet

---

## Quick Start

```bash
# Clone
git clone https://github.com/dovilo/CortexFlow.git
cd CortexFlow

# Open in browser (static site)
open index.html

# Or serve locally
python3 -m http.server 8080
# → http://localhost:8080
```

No build step. No dependencies. Just open and go.

---

## How It Works

1. **Design** — Drag nodes onto the canvas, connect them to form reasoning chains
2. **Configure** — Set MiMo parameters per Reason node (temperature, max tokens, system prompt)
3. **Run** — Execute the pipeline and watch tokens flow in real-time
4. **Debug** — Inspect intermediate reasoning at any node, spot bottlenecks
5. **Deploy** — Export pipeline as API endpoint or scheduled task

---

## MiMo Integration

CortexFlow is built around **Xiaomi MiMo v2.5-pro** as the primary reasoning engine:

- **Chain-of-thought reasoning** per Reason node
- **JSON mode** for structured outputs from Gate nodes
- **128K context window** for long-chain memory
- **Cost-efficient** — MiMo's pricing enables high-volume pipeline execution

---

## API Reference

```javascript
// POST /api/pipeline/execute
{
  "pipeline_id": "uuid",
  "inputs": {
    "text": "Analyze this smart contract..."
  },
  "config": {
    "model": "mimo-v2.5-pro",
    "temperature": 0.7,
    "max_tokens": 4096
  }
}

// Response
{
  "status": "completed",
  "outputs": { ... },
  "nodes_executed": 7,
  "tokens_used": 2341,
  "latency_ms": 1820
}
```

---

## License

MIT License — see [LICENSE](LICENSE)

---

**Built with 🧠 by [dovilo](https://github.com/dovilo) · Powered by Xiaomi MiMo v2.5-pro**
