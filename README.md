# Activout Homebrew tap

Homebrew formulas for Activout's command-line tools, on macOS and Linux.

```sh
brew install activout/tap/elg
```

| Formula | What it does | Platforms |
|---|---|---|
| [`elg`](https://github.com/activout/elg) | Unofficial CLI for GleSYS email hosting, DNS and servers | macOS, Linux (Intel and ARM) |
| [`nordray-tunnel`](https://github.com/activout/nordray-tunnel) | Self-hosted HTTP tunnels in your own Bunny account | macOS, Linux (Intel and ARM) |
| [`blue5`](https://github.com/activout/Activout.Blue5) | Unofficial read-only CLI for the Bluestone PIM Public API | macOS (Apple Silicon), Linux (Intel) |
| [`content-scheduler`](https://github.com/activout/Activout.C9.Scheduler) | Reconciles cron-based publish rules into Contentful Scheduled Actions | macOS (Apple Silicon), Linux (Intel) |
| [`bank`](https://github.com/activout/Activout.Banking) | Archives and exports your own bank transactions via Enable Banking | macOS (Apple Silicon), Linux (Intel) |

A formula appears once its project has a release with binaries. Each one installs the prebuilt binary from the
project's GitHub release and checks it against the release's checksum file. If Homebrew refuses to load a formula from
an untrusted tap, run `brew trust activout/tap`.

## How the formulas are updated

`Formula/` is generated: do not edit it by hand. [`update.py`](update.py) lists the CLIs and writes each formula from
the project's latest GitHub release. The [Update formulas](.github/workflows/update.yml) workflow runs it every hour,
installs and tests every formula that changed, and commits the result. A new release therefore reaches the tap within an
hour, without a token or step in the CLI's own repository. Run the workflow by hand to pick up a release at once.

To add a CLI, add an entry to `CLIS` in `update.py`.
