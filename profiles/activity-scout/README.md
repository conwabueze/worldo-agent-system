# Activity Scout profile distribution

This is a reusable, public-safe source package for an Activity Scout profile.
Replace angle-bracket placeholders during private deployment; do not commit the
real values.

Included:

- distribution.yaml: Hermes package manifest and ownership boundary
- SOUL.md: role, data boundary, and authority rules
- activity-research skill: research procedure and output contract
- activity-planning skill: explicit decision-to-database mapping

The public package intentionally contains no live Notion URLs, OAuth tokens,
Discord configuration, preference data, or user feedback.

For local development, install this directory into a disposable profile:

```sh
hermes profile install "/absolute/path/to/worldo-agent-system/profiles/activity-scout" --name activity-scout-sandbox --alias
```
