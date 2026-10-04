# System Architecture

## Principle

Profiles are durable specialist agents. Each has its own instructions, skills,
model configuration, session/memory boundary, messaging credentials, and MCP
connections. A future Concierge profile may become the single chat-facing
router, but specialists remain independently scoped.

## Current and planned profiles

| Profile | Responsibility | Status |
| --- | --- | --- |
| Activity Scout | Research activities and record explicit decisions | Working |
| Restaurant Scout | Research restaurants and record explicit decisions | Planned |
| Concierge | Route natural-language requests to specialists | Planned |

## Data and authority boundaries

| System | Purpose | Authority |
| --- | --- | --- |
| Preference source | Evolving taste/context input | Read during research; edit only on a separate explicit request |
| Activity Planner | Candidate through attended lifecycle | Create/update only for an explicit, item-specific decision |
| Calendar | Time commitment | Not connected; requires separate final approval |
| Discord | Conversation and notification surface | Never treated as permission to take unrelated external actions |

## Public-source versus private-runtime split

This repository contains reusable source and placeholders. The live Hermes
runtime holds the actual profile configuration, OAuth tokens, chat credentials,
Notion identifiers, preferences, records, and sessions. Do not merge those
runtime files into this repository.

## Repository layout

`profiles/` holds the installable source packages. Each profile has a
`distribution.yaml` manifest, its SOUL, and its own skills. `shared/` holds
cross-profile policies and schemas. `integrations/`, `evals/`, and `deploy/`
will hold reusable connection, testing, and deployment guidance as Worldo
grows.

The Worldo repository is the source of truth. `~/.hermes/profiles/` is the
private runtime: it is where Hermes runs installed profiles and keeps secrets,
OAuth state, memory, and sessions. Keeping those roles separate means one
repository can support many profiles without publishing personal information.
