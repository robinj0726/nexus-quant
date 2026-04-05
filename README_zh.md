# 🚀 NexusQuant

**Local-first, Ultra-fast Financial Sentiment Graph Engine.**

> 毫秒级洞察市场情绪，让非结构化金融资讯瞬间化为你的本地知识图谱。

🇨🇳 简体中文 | [🇺🇸 English](README.md) 

NexusQuant 是一个为宽客 (Quants) 和极客打造的下一代量化舆情分析底座。我们抛弃了臃肿的微服务和沉重的图数据库，采用 **Bun + uv + Rust + Markdown** 的极致性能栈，将海量新闻、财报和社交异动，转化为可以直接在本地 Obsidian 浏览的实体关联情绪图谱。

## 💡 核心哲学：轻、快、稳、灵

  * **轻 (Local-First):** 零数据库依赖。所有的分析结果和实体关联均以带有 YAML Frontmatter 的 Markdown 格式存储，天然完美契合 Obsidian 和 PARA 知识管理法。你的金融数据，真正属于你。
  * **快 (Extreme Performance):** 拒绝环境噩梦。底层利用 `uv` 毫秒级拉起 Python 抓取管道，利用 Rust 编译的 WASM + DuckDB 在内存中极速聚合计算因⼦。
  * **稳 (Type & Memory Safe):** TypeScript 强类型约束 Agent 调度循环，Rust 保证底层数据清洗的内存绝对安全。
  * **灵 (Infinite Extension):** 原生支持双向 MCP (Model Context Protocol) 协议与热加载 Skills 插件。万物皆可接入，万物皆可输出。

-----

## 🏗️ 架构全景 (Architecture)

```text
nexus-quant/
├── ⚙️ core/               # 大脑中枢：Bun + TypeScript 
│   ├── agent.ts          # 基于 ReAct 范式的调度循环 (专为 DeepSeek-MoE 优化)
│   └── mcp_client.ts     # 双向 MCP 协议支持
├── 🐍 etl/                # 感知器：uv + Python
│   ├── pyproject.toml    # 闪电级依赖管理，告别环境配置噩梦
│   └── fetch_news.py     # 基于无头浏览器的非结构化资讯抓取
├── 🦀 engine/             # 运算引擎：Rust + WASM + DuckDB
│   ├── Cargo.toml
│   └── src/lib.rs        # 毫秒级内存图谱推演，编译为 WASM 供 Bun 调用
├── 🔌 plugins/            # 扩展沙箱：热插拔 Skills
│   └── rsi_calculator.ts # 社区/个人贡献的自定义指标与数据源 (如 tushare 接口)
├── 🗂️ vault/              # 效应器：Markdown 舆情图谱输出
│   ├── Events/           # 突发宏观/行业事件节点
│   └── Tickers/          # 股票标的节点 (带情绪极性打分及双向链接)
├── 📄 config.yaml        # 全局枢纽：一键配置模型、数据源与图谱行为
└── 🚀 package.json       # 入口点
```

-----

## 🔥 杀手级特性 (Killer Features)

### 1\. 毫秒级事件传染推演

输入一条突发新闻，NexusQuant 会瞬间拉起 ETL 管道，调度大语言模型进行 NER (实体识别) 和极性打分，推演产业链上下游的连锁反应，并输出多空风向标。

### 2\. 万物皆节点 (Markdown as Graph)

分析结果直接输出为含有 YAML 元数据的 `.md` 文件和 `[[WikiLinks]]`。打开你的 Markdown 编辑器，一个动态的金融知识图谱已经为你构建完毕。追踪市场情绪就像追踪代码 Diff 一样简单。

### 3\. 热插拔插件生态 (MCP & Plugins)

只需在 `plugins/` 目录下丢入一段 TypeScript 或 Python 脚本，无需注册，系统启动时自动反射为大模型的可用工具。无缝接入全网公开或私有 API。

-----

## ⚡ 快速开始 (Quick Start)

只需三行命令，见证魔法时刻：

```bash
# 1. 安装 Bun 依赖 (核心中枢)
bun install

# 2. 同步极速 Python 环境 (ETL 管道)
uv sync

# 3. 启动突发事件情绪推演！
bunx nexus-quant start --event "智利突然宣布锂矿出口配额减半" --depth 2
```

> **系统要求：** 需要预先安装 [Bun](https://www.google.com/search?q=https://bun.sh/), [uv](https://www.google.com/search?q=https://github.com/astral-sh/uv), 及 [Rust](https://www.google.com/search?q=https://www.rust-lang.org/) 工具链。推荐使用 macOS (Apple Silicon 体验极佳) 或 Linux。

-----

## 🛠️ 贡献指南

NexusQuant 正在积极招募种子开发者！无论你是对 Rust 性能压榨感兴趣，还是热衷于微调金融小模型，亦或是想贡献特定的 MCP 爬虫插件，我们都非常欢迎。

查看 [CONTRIBUTING.md](https://www.google.com/search?q=./CONTRIBUTING.md) 了解如何提交 PR，以及项目 `config.yaml` 的详细配置规范。

## 📜 许可证

本项目采用 MIT 许可证 - 详情请见 [LICENSE](https://www.google.com/search?q=LICENSE) 文件。