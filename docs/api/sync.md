---
layout: default
title: Sync
parent: API Documentation
nav_order: 4
---

[Documentation Home](../index.md) | [API Index](index.md)

# Sync

GymTracker does not have dedicated sync endpoints yet, but the current API already includes several sync-aligned rules.

## What Is Already Sync-Aligned

- GymTracker owns stable backend identities for user-created records
- ExerciseDB-backed exercise overlays are keyed by stable `npId`
- session delete is soft-delete/tombstone normal path
- session detail uses a full aggregate payload, which keeps nested ownership and lifecycle explicit
- mutable root entities use `createdAt`, `updatedAt`, and `deletedAt` patterns in the backend domain

## What Is Not Implemented Yet

- no dedicated sync endpoints
- no device-level sync state
- no conflict-resolution API
- no offline-first web synchronization layer
- no iOS remote repository sync implementation yet

## Current Practical Meaning

The current backend contract is the foundation that later iOS repository and sync work should target.

That means:

- exercises should keep using stable `npId` for ExerciseDB-backed overlay lookup
- user-created exercises should keep using backend UUID identity
- session payloads should keep using:
	- user exercise reference -> UUID
	- ExerciseDB-backed reference -> `npId`

## Related Pages

- Current contract surface: [Endpoints](endpoints.md)
- Current DTO shapes: [Models](models.md)
- Deferred sync work and other future items: [Future](future.md)

---

**Navigation**

- Previous: [Models](models.md)
- Next: [Future](future.md)
- Root docs: [Documentation Home](../index.md)
