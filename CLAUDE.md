# Forkstat Tool

## Purpose
Monitors process fork(), exec(), and exit() activity during benchmark execution using the upstream forkstat utility.

## Languages
- Bash: collection scripts (`forkstat-start`, `forkstat-stop`)
- Perl: post-processor (`forkstat-post-process`)

## Key Files
| File | Purpose |
|------|---------|
| `forkstat-start` | Launches forkstat with configurable `--events` parameter (default: `all`) |
| `forkstat-stop` | Kills forkstat, compresses output with xz |
| `forkstat-post-process` | Converts raw forkstat output to crucible metrics (uses `toolbox::metrics`, `toolbox::json`, `toolbox::cpu` from `$TOOLBOX_HOME/perl`) |
| `rickshaw.json` | Rickshaw integration: endpoint allow/block lists, file deployment, post-process script |
| `workshop.json` | Engine image build: compiles forkstat from source |

## Conventions
- Primary branch is `main`
- Runs as a profiler tool on master/worker roles, blocked on client/server
- Standard Bash/Perl modelines and 4-space indentation
