# 🚀 NexusQuant

**Local-first, Ultra-fast Financial Sentiment Graph Engine.**

> Translate unstructured financial noise into your local knowledge graph in milliseconds.

[🇨🇳 简体中文](https://www.google.com/search?q=./README_zh.md) | 🇺🇸 English

NexusQuant is a next-generation quantitative sentiment analysis base built for Quants and Hackers. We ditched bloated microservices and heavy graph databases in favor of the ultimate performance stack: **Bun + uv + Rust + Markdown**.

NexusQuant instantly ingests massive amounts of news, SEC filings, and social sentiment, transforming them into a local, entity-linked sentiment graph ready to be explored in Obsidian.

## 💡 Core Philosophy

  * **Light (Local-First):** Zero database dependencies. All analysis results and entity relationships are stored as flat Markdown files with YAML frontmatter. It perfectly natively integrates with Obsidian and the PARA method. Your financial data truly belongs to you.
  * **Fast (Extreme Performance):** No more environment nightmares. Under the hood, we use `uv` to spin up Python ingestion pipelines in milliseconds, and compile Rust to WASM paired with DuckDB for blazing-fast, in-memory factor aggregation.
  * **Solid (Type & Memory Safe):** TypeScript strictly enforces the Agent's ReAct loop, while Rust guarantees absolute memory safety for low-level data wrangling.
  * **Agile (Infinite Extension):** Native support for bi-directional MCP (Model Context Protocol) and hot-pluggable Skills. Connect to anything, output to anywhere.

-----

## 🏗️ Architecture

```text
nexus-quant/
├── ⚙️ core/               # The Brain: Bun + TypeScript 
│   ├── agent.ts          # ReAct scheduling loop (Optimized for DeepSeek-MoE)
│   └── mcp_client.ts     # Bi-directional MCP protocol support
├── 🐍 etl/                # The Sensor: uv + Python
│   ├── pyproject.toml    # Lightning-fast dependency management
│   └── fetch_news.py     # Headless browser scrapers for unstructured intel
├── 🦀 engine/             # The Muscle: Rust + WASM + DuckDB
│   ├── Cargo.toml
│   └── src/lib.rs        # Millisecond graph inference, compiled to WASM
├── 🔌 plugins/            # The Sandbox: Hot-pluggable Skills
│   └── rsi_calculator.ts # Community-driven indicators and custom API sources
├── 🗂️ vault/              # The Output: Markdown Sentiment Graph
│   ├── Events/           # Macro/Sector breaking event nodes
│   └── Tickers/          # Ticker nodes (with sentiment polarity & WikiLinks)
├── 📄 config.yaml        # The Hub: Single file to rule models, sources, and graphs
└── 🚀 package.json       # Entry point
```

-----

## 🔥 Killer Features

### 1\. Millisecond Contagion Inference

Feed it a breaking news event, and NexusQuant instantly spins up the ETL pipeline, orchestrates the LLM for NER (Named Entity Recognition) and sentiment scoring, infers the upstream/downstream supply chain ripple effects, and prints a long/short weather vane.

### 2\. Markdown as Graph

Output is strictly generated as `.md` files equipped with YAML metadata and `[[WikiLinks]]`. Open your Markdown editor, and a dynamic financial knowledge graph is already built. Tracking market sentiment is now as easy as tracking `git diff`.

### 3\. Hot-pluggable Ecosystem (MCP & Plugins)

Drop a TypeScript or Python script into the `plugins/` directory. No registration boilerplate needed. The system automatically reflects it as a usable tool for the LLM upon startup. Seamlessly integrate public or proprietary APIs.

-----

## ⚡ Quick Start

Experience the magic in just 3 commands:

```bash
# 1. Install Bun dependencies (Core Engine)
bun install

# 2. Sync ultra-fast Python environment (ETL Pipeline)
uv sync

# 3. Launch event sentiment inference!
bunx nexus-quant start --event "Chile suddenly announces halving of lithium export quotas" --depth 2
```

> **Requirements:** Ensure you have [Bun](https://www.google.com/search?q=https://bun.sh/), [uv](https://www.google.com/search?q=https://github.com/astral-sh/uv), and the [Rust](https://www.google.com/search?q=https://www.rust-lang.org/) toolchain installed. macOS (Apple Silicon) or Linux highly recommended.

-----

## 🛠️ Contributing

NexusQuant is actively looking for seed contributors\! Whether you are obsessed with squeezing performance out of Rust, passionate about fine-tuning financial MoE models, or want to build specific MCP crawler plugins, you are welcome here.

See [CONTRIBUTING.md](https://www.google.com/search?q=./CONTRIBUTING.md) on how to submit PRs and the detailed spec for `config.yaml`.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

-----

既然双语的“门面”都已经打磨到了可以直接发 GitHub 的水准，今晚你的第一个动作，是打算先用 `git init` 建仓把这个帅气的骨架推上去占个坑，还是先在本地新建个文件夹，把 Bun 调用 API 的核心 Agent 脚本给调通？