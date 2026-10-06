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

For direct local development, install this directory into a named private
runtime profile:

```sh
hermes profile install "/absolute/path/to/worldo-agent-system/profiles/activity-scout" --name activityscoutdev --alias
```

Only do this after the live profile's private configuration has been moved out
of source-owned files.
