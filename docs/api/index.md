---
layout: default
title: API Documentation
nav_order: 2
has_children: true
---

[Documentation Home](../index.md) | [User Manual](../user-manual/index.md)

# GymTracker API

Current API reference for the implemented GymTracker backend and the frontend contract built against it.

This section reflects what exists now:

- GymTracker backend on TypeScript, Express, PostgreSQL, Prisma, and Zod
- GymTracker-owned auth sessions with no refresh token in MVP
- unified exercise API backed by GymTracker DB plus internal ExerciseDB lookup
- full-aggregate session API
- dashboard summary and session-volume reporting endpoints

## API Sections

- [Architecture](architecture.md)
	Current system boundaries, stack, and service responsibilities.
- [Endpoints](endpoints.md)
	Implemented route groups and request/response behavior.
- [Models](models.md)
	Current DTOs and domain shapes exposed through the API.
- [Sync](sync.md)
	What is already sync-aligned today, and what is not implemented yet.
- [Future](future.md)
	Deferred API-adjacent work that is mentioned in the backend planning set but is not implemented yet.

## Current MVP Surface

- Auth:
	`POST /api/v1/auth/providers/interact/login`,
	`POST /api/v1/auth/providers/interact/exchange`,
	`POST /api/v1/auth/logout`,
	`GET /api/v1/auth/session`,
	`GET /api/v1/me`
- Exercises:
	`GET /api/v1/exercises`,
	`POST /api/v1/exercises`,
	`GET /api/v1/exercises/:exerciseId`,
	`PATCH /api/v1/exercises/:exerciseId`,
	`DELETE /api/v1/exercises/:exerciseId`
- Sessions:
	`GET /api/v1/sessions`,
	`POST /api/v1/sessions`,
	`GET /api/v1/sessions/:sessionId`,
	`PATCH /api/v1/sessions/:sessionId`,
	`DELETE /api/v1/sessions/:sessionId`
- Reports:
	`GET /api/v1/dashboard/summary`,
	`GET /api/v1/reports/session-volume`

---

**Navigation**

- Next: [Architecture](architecture.md)
- Root docs: [Documentation Home](../index.md)
