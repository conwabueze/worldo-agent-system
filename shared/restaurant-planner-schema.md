# Restaurant Planner Schema Contract

Restaurant Scout uses one canonical Restaurant Planner database. The database
is an intentional record of a recommendation and the user's decision; it is
not a reservation system.

## Fields

| Field | Notion type | Purpose |
| --- | --- | --- |
| Restaurant | Title | Restaurant, bar, cafe, bakery, or food experience name. |
| Status | Select | `Candidate`, `Planned`, `Deferred`, `Declined`, `Visited`. |
| Full address | Text | Verified street address. |
| Neighborhood | Select | Useful for local discovery and logistics. |
| Borough/city | Select | Borough or city. |
| Maps URL | URL | Direct maps link. |
| Cuisine/categories | Multi-select | Cuisine, format, or food experience labels. |
| Price guidance | Select | Use a simple scale such as `$`, `$$`, `$$$`, `$$$$`, or `Unknown`. |
| Suitable for | Multi-select | `Solo`, `Friends`, `Partner`, and other user-defined contexts. |
| Best social mode | Select | Primary recommended social context. |
| Social energy | Select | Low, Medium, or High social energy. |
| Planning effort | Select | Walk-in friendly, Reservation helpful, or Reservation required. |
| Official website | URL | Restaurant-controlled primary link. |
| Instagram URL | URL | Preferred social link when available. |
| Secondary social URL | URL | Secondary verified social/discovery link. |
| Social platform | Select | Platform for the secondary social link. |
| Discovery source | URL | Source that led to the recommendation. |
| Why it fits | Text | Concise connection to the user's preferences and context. |
| Confidence | Select | High, Medium, or Low confidence in the recommendation. |
| Recommended on | Date | When Restaurant Scout suggested it. |
| Decision reason | Text | Why it was saved, planned, deferred, or declined. |
| Planned for | Date | Optional user-intended visit date; not a calendar event. |
| Reservation status | Select | `Not requested`, `Need to check`, `Requested manually`, `Confirmed manually`, `Not needed`. |
| Visit date | Date | Actual visit date, if known. |
| Actual context | Multi-select | Who/what setting the visit actually involved. |
| Context fit | Select | Great fit, Good fit, Mixed, or Poor fit. |
| Visited rating | Number | User rating after the visit. |
| User notes | Text | Freeform feedback for future recommendations. |

## Suggested views

- **Candidates:** table filtered to `Candidate`.
- **Planned:** table or calendar filtered to `Planned`.
- **Deferred:** table filtered to `Deferred`.
- **Declined:** table filtered to `Declined`.
- **Visited:** table filtered to `Visited`.

## Authority boundary

Restaurant Scout must fetch the actual schema before every write. It sets only
verified fields and fields directly supplied by the user. It does not create a
reservation, join a waitlist, contact a venue, create a calendar event, or
change this schema.
