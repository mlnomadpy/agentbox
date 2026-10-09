# Development and validation

## Requirements and first run

Use Node 22, npm, Git, and a desktop session for Electron. Run `npm ci` from
the checkout, then `ZERO_FIXTURES=1 ZERO_NO_SUPERVISOR=1 npm run dev`.
The fixture window is the recommended starting point for UI work. Both flags
matter: fixtures select sample content and the supervisor flag disables automatic
agent scheduling. No provider login is needed for that workflow.

`npm ci` runs installation hooks and may download platform binaries. Native
node-pty compilation may require Xcode command-line tools on macOS, or Python,
make, and a C++ compiler on Linux. See install output for the failing component.

## Real sessions

Install and authenticate Claude Code or Codex separately for actual agents.
Use an ignored `zero.config.json` with a dedicated `storeRoot` for experiments.
Review `main/config.mjs` and `main/supervisor.mjs` before changing session
permissions. A development window on a real store requires explicit
`ZERO_DEV_ON_REAL_STORE=1`; hot reload can discard UI state.

## Build and run

`npm run build` produces `renderer/dist`; `npm start` builds and opens Electron.
`npm run serve -- --help` describes browser mode. Desktop and browser modes
have different platform capabilities; test the mode affected by your change.
The build probes an installed Claude CLI for command/model metadata. If that
CLI lacks a command the probe expects, update the CLI or use a clean environment
without it, which uses committed snapshots. Do not commit machine-generated
`*.local.json` metadata. `npm run read:claude` deliberately updates snapshots.

`npm run pack` invokes the unsigned packaging workflow. Packaging is distinct
from a renderer build and depends on platform tools. The fork still carries
upstream application identifiers and release settings: review `package.json`
and `main/updater.mjs` before distributing fork releases. Do not publish a fork
with upstream signing credentials or update infrastructure.

## Checks

Run `npm run check:contribution` for local Markdown file targets and issue form
structure. It does not validate remote URLs or heading fragments. Run
`npm run test:working` while iterating and `npm run test:changed` for the PR diff.
Use `npm run typecheck` for renderer types and `npm test` for broad or uncertain
changes. See the [testing guide](testing.md) for the exact selection and merge policy.
Bounded workers avoid overwhelming shared development machines. CI also tests
Linux and macOS. For visible changes, manually exercise the affected workflow
and include results in the pull request. Record failures and limitations rather
than calling an unrun check successful.
