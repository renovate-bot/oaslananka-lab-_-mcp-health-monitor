# Security Policy

## Supported Versions

| Version | Supported |
| ------- | --------- |
| 1.x     | ✅        |

## Reporting a Vulnerability

Report via GitHub Security Advisories:
https://github.com/oaslananka-lab/mcp-health-monitor/security/advisories/new

Do not open public issues for security vulnerabilities.

Include a clear impact summary, affected version, reproduction steps, and any
proposed mitigation.

## Threat Model Notes

- Azure DevOps PAT tokens are stored as base64 in the local SQLite database in
  v1.x. This is encoding, not encryption. Use least-privilege PATs and rotate
  them if the database leaves the trusted machine.
- MCP server URLs, commands, tags, health history, and Azure DevOps pipeline
  history are stored locally in SQLite.
- Keep SQLite database files outside version-controlled directories.
- The primary transport is stdio. If HTTP transport is enabled for local
  diagnostics, bind it to loopback or place it behind an authenticated reverse
  proxy.

For implementation details and storage notes, see `docs/security.md`.
