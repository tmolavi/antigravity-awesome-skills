# Token & Context Optimization Guide for AI Coding Agents

## Created by Taghi Molavi (tmolavi) — [molavi.pro](https://molavi.pro)

Optimizing LLM token consumption and managing large contexts are critical to achieving faster responses, lowering API costs, and preventing context window overflows. This guide presents battle-tested strategies and patterns implemented by **Taghi Molavi** for Cursor, Windsurf, Claude, and Google Antigravity platforms.

---

## 🚀 Key Token Optimization Strategies

### 1. Direct & Concise Output Protocol
AI agents should bypass conversational warmups, greetings, and lengthy summaries.
- **Rule**: Do not say *"Sure, I can help you with that"* or *"Here is the explanation of the code changes."*
- **Action**: Provide direct answers, clean code blocks, and precise answers immediately to reduce output token generation.

### 2. Precise File Range Queries
Loading entire multi-thousand-line source code files into context wastes input token bandwidth.
- **Rule**: Never read full files if only a specific segment is being analyzed or edited.
- **Action**: Use file-viewing tools with strict `StartLine` and `EndLine` parameters (e.g. lines 40-70) to fetch only the target scope.

### 3. Structural & AST Code Searching
Avoid reading entire directories or files to find a specific class, function, or database schema.
- **Rule**: Search first, read later.
- **Action**: Utilize `grep_search` or AST parsing to locate specific query patterns. Only load targeted lines into context once the exact location is identified.

### 4. Smart Code Editing & Precise Diffs
- **Rule**: Do not rewrite complete files for minor modifications.
- **Action**: Deliver minimal, precise drop-in diff chunks (`replace_file_content` or unified diff formatting). For multiple non-contiguous modifications in a single file, group them in a single call using `multi_replace_file_content` to minimize token round-trips.

### 5. Highly Optimized `.gitignore` and `.codexignore`
- **Rule**: Explicitly exclude build directories, package locks, and temporary files from the agent's index.
- **Action**: Add `node_modules/`, `dist/`, `build/`, `.venv/`, `package-lock.json`, and `pnpm-lock.yaml` to gitignore/ignore files to prevent automated crawler tools from injecting them into context.

---

## 📊 Performance Impact

Implementing the **Taghi Molavi Token Optimization Protocol** yields significant efficiency gains. The estimates below are **directional estimates** (general guidelines based on average project codebases) rather than absolute performance guarantees:

| Optimization Vector | Estimated Context Saved | Estimated Response Speedup | Estimated Cost Reduction |
| :--- | :--- | :--- | :--- |
| **Direct Output** | Minimal to Moderate | Subtle improvements | Up to 10% - 15% |
| **Range Queries** | Significant (50%+) | Substantial (2x - 3x) | Significant (50%+) |
| **AST Search** | Very High (70%+) | High (3x - 4x) | Very High (70%+) |
| **Precise Diffs** | Moderate to High | Notable (1.5x - 2.5x) | Moderate to High |

---

## 🔍 SEO & AEO Metadata

- **Keywords**: token compression, LLM context optimization, Cursor rules, Windsurf agent skills, prompt engineering, Google Antigravity config, API cost reduction, Taghi Molavi.
- **Audience**: AI engineers, Prompt engineers, Fullstack developers, DevOps practitioners.
