---
layout: default
title: Future
parent: API Documentation
nav_order: 5
---

[Documentation Home](../index.md) | [API Index](index.md)

# Future

This page tracks API-adjacent work that is mentioned in the backend planning set but is not implemented yet.

## Auth

- Apple provider exchange is still deferred
- GymTracker refresh token flow is not implemented
- Interact remains the only supported MVP provider

## Exercises

- broader overlay support beyond aliases and hidden state is deferred
- no per-user materialized copy of the ExerciseDB catalog is planned
- direct public nginx `/exercises/` routing still exists in infrastructure and still needs later cutover so supported clients go through GymTracker backend only

## Sessions

- no routines integration in MVP
- no row-level session mutation endpoints are planned for MVP
- no sync-specific session endpoints exist yet

## Reports

- only dashboard summary and session-volume report exist today
- no streak engine
- no personal records reporting
- no leaderboards
- no comparative trend analytics

## Sync and iOS Remote Repositories

- no dedicated sync endpoints yet
- no Xcode repository/sync hookup has been implemented against the backend contract yet
- later iOS remote repository adoption is still expected to start with Exercises first

## Web and Realtime

- no offline-first web sync layer
- no WebSockets
- no background realtime updates

## Deployment and Infrastructure

- final containerized backend deployment flow is still planning-only
- nginx routing changes are not implemented yet
- ExerciseDB has not yet been fully moved behind GymTracker backend for all supported public traffic
- production migration/deploy automation remains future work

## Out of Scope For Current MVP

- routines
- nutrition
- HealthKit backend work
- timer backend scope

---

**Navigation**

- Previous: [Sync](sync.md)
- Next: [API Index](index.md)
- Root docs: [Documentation Home](../index.md)
