# Contributing

## Branches

Use focused branches with one of these prefixes:

- `fix/`
- `feat/`
- `ci/`
- `docs/`
- `chore/`

## Commits

Use Conventional Commits, for example `fix: handle failed health checks` or
`ci: harden release validation`.

## Local Validation

Run the full local gate before opening or updating a pull request:

```bash
task ci
```

If Task is unavailable, run the underlying npm commands:

```bash
npm ci
npm run format:check
npm run lint
npm run lint:test
npm run typecheck
npm test
npm run test:integration
npm run build
npm pack --dry-run
```

## Pull Request Checklist

- Keep the change scoped to one behavior or maintenance goal.
- Update tests for behavior changes.
- Update README, SECURITY.md, or docs when user-facing behavior changes.
- Do not include secrets, local databases, generated packages, or private notes.
- Confirm release and publish paths remain guarded by the production environment.

## Release Process

Releases are prepared by release-please from the canonical repository:
`oaslananka-lab/mcp-health-monitor`. Publishing is guarded by the `production`
environment and package provenance attestation.
