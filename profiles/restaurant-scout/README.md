# Restaurant Scout profile distribution

This public-safe starter package defines the role and safety boundaries for a
Worldo restaurant specialist. It is intentionally not connected to a real
Notion database, Discord bot, reservation service, or personal preference
source yet.

Included:

- `distribution.yaml`: Hermes package manifest and ownership boundary
- `SOUL.md`: role, data boundary, and authority rules
- `restaurant-research`: research and ranking procedure
- `restaurant-planning`: explicit decision-to-database procedure

Before it becomes a live agent, Restaurant Scout needs its own preferences,
output contract, evaluation cases, Restaurant Planner database, minimum
Notion tool allowlist, and Discord/channel decision.

For direct local development, install it as a named private runtime profile:

```sh
hermes profile install "/absolute/path/to/worldo-agent-system/profiles/restaurant-scout" --name restaurantscoutdev --alias
```
