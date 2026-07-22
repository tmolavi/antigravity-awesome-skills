# Installation and Usage Guide for AI Agents & MCP Servers

## Compiled by Taghi Molavi (tmolavi)

This guide provides setup and configuration protocols for using the skills and Model Context Protocol (MCP) servers contained in this repository.

---

## 🛠️ Supporting Platforms & IDEs

The skills and servers in this repository are designed to work seamlessly with the following AI platforms and editors:
- **Google Antigravity** (IDE, CLI, and Standalone version 2.0)
- **Cursor** & **Windsurf** (VS Code-based AI code editors)
- **Claude Desktop** & **ChatGPT Codex**
- **Cline**, **Roo Code**, and **Aider**

---

## 📂 1. Setting Up Agent Skills

### Option A: Local Workspace Installation (Recommended)
Place the required skills directly in your project root under the `.agents/skills/` directory.

```bash
mkdir -p .agents/skills/
cp -r /path/to/antigravity-awesome-skills/skills/<skill-folder> .agents/skills/
```

### Option B: Global System-Wide Installation
For global access, install the skills into the user-level configuration path for your agent:

- **Google Antigravity**:
  ```bash
  cp -r /path/to/antigravity-awesome-skills/skills/* ~/.gemini/config/skills/
  ```
- **ChatGPT Codex / Cursor**:
  ```bash
  cp -r /path/to/antigravity-awesome-skills/skills/* ~/.codex/skills/
  ```

---

## 🔌 2. Configuring MCP Servers

Model Context Protocol (MCP) servers extend your AI agent's capabilities by providing database querying, SEO auditing, and development environment logs directly.

### A. Configuration for Google Antigravity
Save the following configurations in your global config file located at `~/.gemini/config/mcp_config.json`:

```json
{
  "mcpServers": {
    "mysql-mcp": {
      "command": "npx",
      "args": ["-y", "@benborla29/mcp-server-mysql"],
      "env": {
        "MYSQL_HOST": "127.0.0.1",
        "MYSQL_PORT": "3306",
        "MYSQL_USER": "root",
        "MYSQL_PASS": "secret",
        "MYSQL_DB": "my_db"
      }
    },
    "clockwork-mcp": {
      "command": "npx",
      "args": ["-y", "clockwork-mcp"]
    },
    "maxaeo-ai-visibility": {
      "command": "npx",
      "args": ["-y", "maxaeo-ai-visibility-mcp"]
    },
    "octoboost-seo": {
      "command": "npx",
      "args": ["-y", "octoboost-mcp-server"],
      "env": {
        "OCTOBOOST_API_KEY": "YOUR_API_KEY"
      }
    }
  }
}
```

### B. Configuration for Cursor / Claude Desktop / ChatGPT Codex
Save the configurations in `~/.claude/claude_desktop_config.json` or your Cursor custom MCP server settings:

```json
{
  "mcpServers": {
    "mysql-mcp": {
      "command": "npx",
      "args": ["-y", "@benborla29/mcp-server-mysql"],
      "env": {
        "MYSQL_HOST": "127.0.0.1",
        "MYSQL_PORT": "3306",
        "MYSQL_USER": "root",
        "MYSQL_PASS": "secret",
        "MYSQL_DB": "my_db"
      }
    },
    "clockwork-mcp": {
      "command": "npx",
      "args": ["-y", "clockwork-mcp"]
    },
    "maxaeo-ai-visibility": {
      "command": "npx",
      "args": ["-y", "maxaeo-ai-visibility-mcp"]
    },
    "octoboost-seo": {
      "command": "npx",
      "args": ["-y", "octoboost-mcp-server"],
      "env": {
        "OCTOBOOST_API_KEY": "YOUR_API_KEY"
      }
    }
  }
}
```

---

## 🎯 Verification

To verify that your skills and MCP servers are running successfully:
- **Antigravity CLI**: Run `agy` and type `/mcp` to list active connections.
- **Cursor**: Go to `Settings > Features > MCP` to check the status of configured servers.
- **Claude Desktop**: Restart the app and look for the electrical plug icon in the input box.
