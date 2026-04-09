---
layout: default
title: Architecture
parent: API Documentation
nav_order: 1
---

[Documentation Home](../index.md) | [API Index](index.md)

# Architecture

Current API architecture for the implemented GymTracker stack.

## Stack

- Backend: TypeScript + Express
- Database: PostgreSQL + Prisma
- Validation: Zod
- Frontend consumer: SvelteKit web app
- Internal dependency: ExerciseDB for ExerciseDB-backed exercise metadata

## API Boundary

GymTracker backend is the supported API boundary for clients.

- Web frontend talks to GymTracker backend only
- Future iOS remote repositories should also talk to GymTracker backend only
- ExerciseDB is an internal backend dependency, not a supported client API

## Current Responsibility Split

- Frontend:
	collect input, bootstrap GymTracker session state, render dashboard/exercises/sessions/settings
- GymTracker backend:
	validate requests, own auth session model, store user-owned records, shape all client DTOs
- ExerciseDB:
	provide base ExerciseDB-backed exercise metadata used internally by GymTracker backend

## Current Runtime Topology

- nginx is the public entrypoint in the existing deployment topology
- GymTracker backend is the intended supported API target behind nginx
- direct public `/exercises/` routing to ExerciseDB still exists in infrastructure, but it is not the intended client contract

## Current Backend Module Areas

- `auth`
- `users`
- `exercises`
- `sessions`
- `reports`
- shared internal ExerciseDB integration client

## Current API Design Rules

- versioned under `/api/v1`
- GymTracker-issued access token only
- no refresh token in MVP
- unified exercise contract
- session detail uses full aggregate payloads
- session delete is soft-delete/tombstone normal path
- reporting surface is intentionally small and data-only

## Related Pages

- Implemented routes: [Endpoints](endpoints.md)
- Current DTOs: [Models](models.md)
- Sync-aligned rules and deferred sync work: [Sync](sync.md)
- Deferred work: [Future](future.md)

---

**Navigation**

- Previous: [API Index](index.md)
- Next: [Endpoints](endpoints.md)
- Root docs: [Documentation Home](../index.md)
