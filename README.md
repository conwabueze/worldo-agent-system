# Personal Agent System with Hermes

A build-in-public blueprint for a modular personal-agent system running on
[Hermes Agent](https://github.com/NousResearch/hermes-agent).

The first implemented specialist is an Activity Scout. It researches
activities, uses a Notion preference source, and records explicit decisions in
one Activity Planner database. Future specialists can cover restaurants and
other parts of life without sharing private credentials or memory by default.

## Architecture

    Discord or another chat surface
                |
        Specialist profile
                |
    Notion preferences and destination database
                |
    Optional future calendar workflow with separate approval

See [architecture](docs/architecture.md), the
[Activity Scout package](agents/activity-scout/README.md), and the
[local installation notes](deploy/local-install.md).

## What this repository intentionally excludes

This is a public-safe source repository, not a copy of a live personal agent.
It excludes credentials, OAuth tokens, Discord identifiers, Notion URLs and
records, session history, personal preference data, logs, and backups.

## Status

The Activity Scout is the first working profile. It supports Notion retrieval
and explicit activity-record decisions; it does not create calendar events,
purchase tickets, make reservations, or contact anyone.
