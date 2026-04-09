---
layout: default
title: Endpoints
parent: API Documentation
nav_order: 2
---

[Documentation Home](../index.md) | [API Index](index.md)

# Endpoints

Implemented GymTracker API routes as of the current MVP backend/frontend slice.

## Health

### `GET /api/health`

- simple backend health check
- no auth required

## Auth

### `POST /api/v1/auth/providers/interact/login`

- frontend-supported Interact login path
- accepts Interact `username` and `password`
- backend talks to Interact internally
- returns GymTracker session response

### `POST /api/v1/auth/providers/interact/exchange`

- bundle-based provider exchange path
- validates Interact bundle through backend-side provider adapter
- returns GymTracker session response

### `POST /api/v1/auth/logout`

- invalidates current GymTracker session
- requires GymTracker auth

### `GET /api/v1/auth/session`

- returns current session summary
- requires GymTracker auth

### `GET /api/v1/me`

- returns current account basics
- requires GymTracker auth

## Exercises

### `GET /api/v1/exercises`

- returns unified exercise list
- merges user-created exercises and ExerciseDB-backed exercises
- supports practical list filtering such as `search`, `archived`, and `source`
- requires GymTracker auth

### `POST /api/v1/exercises`

- creates a GymTracker-owned user exercise
- requires GymTracker auth

### `GET /api/v1/exercises/:exerciseId`

- returns one unified exercise DTO
- plain id contract:
	- user-created exercise -> UUID
	- ExerciseDB-backed exercise -> `npId`
- requires GymTracker auth

### `PATCH /api/v1/exercises/:exerciseId`

- updates a GymTracker-owned user exercise
- or updates allowed overlay fields for an ExerciseDB-backed exercise
- current ExerciseDB-backed overlay fields:
	- aliases
	- hidden/archive state
- requires GymTracker auth

### `DELETE /api/v1/exercises/:exerciseId`

- soft-deletes GymTracker-owned user exercises
- does not delete ExerciseDB-backed exercises
- requires GymTracker auth

## Sessions

### `GET /api/v1/sessions`

- returns lightweight session list under `items`
- supports `from`, `to`, and `limit`
- excludes tombstoned sessions by default
- requires GymTracker auth

### `POST /api/v1/sessions`

- creates a sparse or nested session aggregate
- returns canonical stored aggregate
- requires GymTracker auth

### `GET /api/v1/sessions/:sessionId`

- returns full session aggregate
- includes `entries`, `sets`, and `reps`
- requires GymTracker auth

### `PATCH /api/v1/sessions/:sessionId`

- full aggregate save only
- no row-level patch endpoints
- requires GymTracker auth

### `DELETE /api/v1/sessions/:sessionId`

- root soft delete / tombstone normal path
- requires GymTracker auth

## Reports

### `GET /api/v1/dashboard/summary`

- returns summary-card data only
- supports `from` and `to`
- requires GymTracker auth

### `GET /api/v1/reports/session-volume`

- returns time-bucketed session volume data
- supports `from`, `to`, and `bucket=day`
- requires GymTracker auth

## Related Pages

- System context: [Architecture](architecture.md)
- Data definitions: [Models](models.md)
- Deferred and future work: [Future](future.md)

---

**Navigation**

- Previous: [Architecture](architecture.md)
- Next: [Models](models.md)
- Root docs: [Documentation Home](../index.md)
