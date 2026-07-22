# Security Policy

## Scope

The **Molavi Agent Skills** project provides AI agent skill configurations and MCP server setup patterns. Because these skills are executed within agentic AI environments with full local file system and network access, security of the configurations is critical.

## What Counts as a Security Issue?

The following are treated as security vulnerabilities in this repository:

- **Leaked secrets**: Any real API key, password, token, or credential committed inside a skill file, config example, or documentation.
- **Malicious skill instructions**: A `SKILL.md` that instructs an agent to perform unauthorized actions (e.g., exfiltrate files, send data to external endpoints, delete data without explicit user confirmation).
- **Unsafe MCP configs**: Database or filesystem MCP configurations that use elevated permissions (admin/root/write) as the default, without explicit user opt-in.
- **Destructive database examples**: Code samples that use `DROP`, `TRUNCATE`, `DELETE` without explicit warning and user confirmation flows.
- **Hidden exfiltration behavior**: Instructions that cause agents to silently send user data, environment variables, or file contents to third-party servers.

## Reporting a Vulnerability

If you discover any of the above in this repository:

1. Do **NOT** open a public GitHub Issue.
2. Contact [Taghi Molavi](https://molavi.pro) privately.
3. Provide a brief description of the file and the nature of the issue.

We will investigate and address the issue promptly, typically within 7 days of a credible report.

## Safe Usage Guidelines

When installing and running agent skills from this repository:

- **Always review** the `SKILL.md` and any referenced scripts before execution.
- **Never store** real API keys, database credentials, or secret tokens inside the skills folder.
- **Database MCP connections must default to read-only** (SELECT-only) permissions. If your workflow requires write access, configure it explicitly and knowingly — this repository will never make write access the default.
- **Test on staging first** before connecting any MCP server to a production database or environment.
