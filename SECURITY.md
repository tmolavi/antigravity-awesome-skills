# Security Policy

## Reporting a Vulnerability

Security is a primary concern for the **Molavi Agent Skills** project. Because these skills are designed to run within agentic AI environments with full local execution permissions, keeping the repository clean of malicious configurations or secrets is critical.

If you discover any security vulnerability, sensitive credential leakage, or malicious script in any of the skills:
1. Do **NOT** open a public issue.
2. Report the vulnerability privately by contacting **Taghi Molavi** via [molavi.pro](https://molavi.pro).

We will investigate the issue and address it promptly.

## Safe Usage Guidelines

When installing and running agent skills:
- Always review the `SKILL.md` and related scripts before execution.
- Never store API keys, database credentials, or secret tokens inside the skills folder.
- Run database connections with read-only permissions inside MCP configuration files.
