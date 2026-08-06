# emprove — the Emprove Claude plugin marketplace

The single, dedicated marketplace for Emprove's Claude Code plugins. Add it once, then browse and install:

```
claude plugin marketplace add Zenosyne-Technologies/emprove-marketplace
claude plugin install marvin@emprove
claude plugin install token-telemetry@emprove
```

Restart Claude Code after installing token-telemetry (its capture hooks load at session start).

## Plugins

| Plugin | What it is |
|---|---|
| **marvin** | Marvin — The Agentic Operating System: orchestrator persona + sub-agent methodology, installable into any project. |
| **token-telemetry** | Zero-overhead token/cost telemetry with storage management — marvin's cost-awareness companion. Optional; marvin degrades gracefully without it. |

## Migrating from the old in-repo marketplace

The marketplace previously lived inside the agent-operating-kit repo (registered as `zenosyne` or `emprove` depending on when you added it). Switch:

```
claude plugin marketplace remove zenosyne
claude plugin marketplace add Zenosyne-Technologies/emprove-marketplace
```

(Use `claude plugin marketplace list` to see what name yours is registered under; installed plugins keep working — reinstall `marvin@emprove` / `token-telemetry@emprove` if the plugin-to-marketplace link breaks.)

## Adding a plugin to this marketplace

One PR: append an entry to `.claude-plugin/marketplace.json` (external repos use the object source form `{ "source": "github", "repo": "Owner/repo" }`); the plugin repo itself must carry a valid `.claude-plugin/plugin.json`. Keep descriptions to one sentence.
