# Agentbox: instructions for coding agents

Read [CLAUDE.md](CLAUDE.md) in full before changing this repository.
Use [CONTRIBUTING.md](CONTRIBUTING.md) for setup and submission.

Behavior changes require regression tests written first and observed failing.
During iteration, use `npm run test:working` or explicit files. Before completion,
run `npm run test:changed` against the PR base (`--base <ref>` for a stack).
Run `npm test` for shared test infrastructure, dependencies, deleted source, or
changes whose impact cannot be selected confidently. Full Linux/macOS CI remains
required for merge. Do not repeat a passing full local run without new evidence.
Documentation-only changes require `npm run check:contribution` and related
source-reading tests; avoid verbatim prose tests. See [testing](docs/testing.md).
Report the selected scope, checks run, and unresolved failures.
