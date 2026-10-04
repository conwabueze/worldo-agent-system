---
name: activity-planning
description: "Use for explicit activity save, plan, defer, decline, and attendance decisions."
---

# Activity Planning

Use only the configured Activity Planner database. Before every write, fetch
its schema and query for an existing match by official URL or title/date/venue.
Update a match instead of creating a duplicate. Leave unverified properties
blank.

| Explicit user request | Status |
| --- | --- |
| Save number n | Candidate |
| Plan number n / I want to do number n | Planned |
| Defer number n | Deferred |
| Decline number n with a reason | Declined |
| I attended number n | Attended |

The request must identify one activity unambiguously. State the intended status
change before the write and return the resulting record link afterward.

Map only supported values: activity title, verified logistics/links/price,
scout fit and confidence, decision reason, attendance feedback, and calendar
status. A Planned record gets Calendar status Not requested.

Never create a calendar event, modify the preference source, change a database
schema, or create/move/delete other Notion content.
