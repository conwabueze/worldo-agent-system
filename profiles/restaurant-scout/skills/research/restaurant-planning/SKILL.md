---
name: restaurant-planning
description: "Use for explicit restaurant save, plan, defer, decline, and visit decisions."
---

# Restaurant Planning

Use only the configured Restaurant Planner database. Before every write,
fetch its schema and query for an existing match by official URL or by
restaurant name/address. Update a match instead of creating a duplicate.
Leave unverified properties blank.

| Explicit user request | Intended status |
| --- | --- |
| Save number n | Candidate |
| Plan number n / I want to try number n | Planned |
| Defer number n | Deferred |
| Decline number n with a reason | Declined |
| I went to number n | Visited |

The request must identify one restaurant unambiguously. State the intended
status change before the write and return the resulting record link afterward.

Map only verified properties supported by the destination database: restaurant
name, location, links, cuisine, price guidance, scout fit and confidence,
decision reason, and visit feedback. A Planned record gets a reservation or
calendar status of Not requested when that property exists.

Never make or modify a reservation, join a waitlist, contact a venue, create a
calendar event, modify the preference source, change a database schema, or
create/move/delete other Notion content.
