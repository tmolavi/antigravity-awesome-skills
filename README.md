# Molavi Agent Skills: Curated Skills for Antigravity, Codex, Cursor & Claude

*Unofficial community project maintained by **Taghi Molavi (tmolavi)***

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![GitHub License](https://img.shields.io/github/license/tmolavi/antigravity-awesome-skills)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/tmolavi/antigravity-awesome-skills)](https://github.com/tmolavi/antigravity-awesome-skills/stargazers)

A curated, practical collection of agent skills and MCP setup patterns for real-world web, database, SEO, and DevOps work. 

---

## 🌟 Value Proposition

In the era of autonomous software development, agents must be equipped with specialized domain knowledge and direct tool access to prevent hallucinations, reduce costs, and ensure production safety. 

This repository provides:
1. **Curated Skills Bundle**: **277 unique, deduplicated agent skills** (`SKILL.md` configurations) ready for local or global installation.
2. **Unified MCP Server Registry**: Configs to connect agents directly to databases, profiling tools, and SEO crawlers.
3. **Token & Context Optimization Protocol**: Taghi Molavi's guidelines for minimizing input/output tokens and speeding up response generation.

---

## 📂 Repository Structure

```
├── README.md                 # Primary index & documentation
├── llms.txt                  # Structural summary for AI crawlers & LLM indexers
├── docs/
│   ├── token-optimization.md # Taghi Molavi Token Optimization Protocol
│   └── agent-installation.md # Local/global installation and MCP config guides
└── skills/                   # 277 curated Agent Skills grouped by category
```

---

## 🏷️ Curated Categories & Skills Included

### 1. Web & Frontend Frameworks
- **Next.js 15 & React 19**: App Router, Server Components, Server Actions, modern hooks (`useActionState`, `useOptimistic`).
- **Tailwind CSS**: Utility-first design tokens and performance-centric styling rules.
- **SvelteKit, Astro, Hugo**: Best practices for static and hybrid rendering architectures.
- **Inertia.js & SSR**: Seamless Single Page Application (SPA) state flow with server-side rendering.

### 2. Backend, Languages & Databases
- **Python**: Concurrency patterns, FastAPI, data pipelines, packaging, and performance profiling.
- **PHP 8.4 & Laravel 13**: Eloquent best practices, Pest testing patterns, and DDD modules.
- **Node.js & NestJS**: Feature-based modular architectures, DTO validation, and structured exception filters.
- **Go & Rust**: System programming, thread safety, async patterns, and memory safety rules.
- **MySQL & PostgreSQL**: Safe queries, index tuning, schema validations, and connection pooling.

### 3. DevOps, CI/CD & Cloud
- **Docker**: Clean multi-stage builds, container safety, and environment isolation.
- **Terraform**: Multi-cloud module libraries (AWS, GCP, Azure).
- **GitHub Actions**: Optimized workflows, caching, and automated deployment pipelines.

### 4. Artificial Intelligence & Vector Databases
- **Gemini, OpenAI & Claude APIs**: High-level SDK patterns, RAG setups, and embeddings.
- **Vector DBs**: Index tuning, similarity search patterns, and semantic queries.

### 5. SEO, AEO & GEO Optimization
- **Technical SEO**: Auditing, sitemaps, canonical tags, Core Web Vitals optimizations.
- **Answer Engine Optimization (AEO)**: Formatting structured JSON-LD data and microcopy for AI search models.
- **Generative Engine Optimization (GEO)**: Citation density analysis, factual coverage, and crawler accessibility.

---

## ⚡ Quick Start & Installation

To install these skills locally in your project workspace:

```bash
mkdir -p .agents/skills/
cp -r skills/<skill-name> .agents/skills/
```

For complete configuration instructions (including setting up local/remote MCP servers), read the [Agent Installation Guide](docs/agent-installation.md).

For advanced prompt optimization guidelines, refer to the [Taghi Molavi Token Optimization Protocol](docs/token-optimization.md).

---

## 🤝 Contributing

Contributions to improve and expand these skills are highly welcome! Please submit a Pull Request or open an Issue. All contributions are credited under the **Taghi Molavi Antigravity Ecosystem**.

---

## 📄 License

This repository is open-sourced under the MIT License. See the [LICENSE](LICENSE) file for details.
