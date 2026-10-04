# Activity Planner Schema Contract

The Activity Scout expects one existing destination database with these
conceptual fields:

- Identity: Activity, Official event URL, Discovery source, Recommended on
- Lifecycle: Candidate, Planned, Deferred, Declined, Attended
- Logistics: Event date and time, Venue, Full address, Neighborhood, Borough
  or city, Maps URL, Price, Planning effort
- Fit: Activity categories, Suitable for, Best social mode, Social energy, Why
  it fits, Confidence
- Social links: Instagram URL, Secondary social URL, Social platform
- Feedback: Decision reason, Actual context, Context fit, Attended rating, User
  notes
- Calendar boundary: Calendar status

The agent must fetch the actual schema before any write and leave unverified
fields blank.
