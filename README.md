# eve-plugins-ai

AI agent and developer-tooling **packages** for [eve](https://github.com/fruwehq/eve)
(Ubuntu). This repo owns these packages end to end — identity registry
(`_catalog-base/packages.yaml`), manifests, and provision steps.

## Packages

| id | what |
| --- | --- |
| `dev-toolchain` | base developer toolchain (also defines the `dev-ai` bundle) |
| `claude` | Claude Code CLI |
| `codex-cli` | Codex CLI |
| `goose` | Goose agent |
| `hermes` | Hermes |
| `opencode` | opencode |
| `vscode` | Visual Studio Code |

`claude`, `codex-cli`, and `goose` declare `depends_on: dev-toolchain`. The
`dev-ai` **bundle** (in `dev-toolchain`) composes the whole set.

## Use it

These are pulled by eve like any external plugin source — nothing is bundled in
eve core:

```sh
eve plugin source add --recommended eve-plugins-ai
eve pull
```

(or add it via the eve TUI's plugin screen). It's in eve's recommended-source
catalog. Pair it with `eve-providers` (providers + OS identity) and, optionally,
`eve-packages-linux` for desktops/remote-access.

## Conformance

CI runs eve's `plugin-test` harness against every package on push/PR
(`.github/workflows/conformance.yml`).

MIT licensed.
