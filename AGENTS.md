# Agentbox: instructions for coding agents

Read [CLAUDE.md](CLAUDE.md) in full before changing this repository.
Use [CONTRIBUTING.md](CONTRIBUTING.md) for setup and submission.

Behavior changes require regression tests written first and observed failing.
Before completion, run the full suite with bounded workers:
`npx vitest run --maxWorkers=4 --minWorkers=1`.
Documentation-only changes require `npm run check:contribution` rather than
verbatim prose tests. Report which checks ran and any unresolved failures.
