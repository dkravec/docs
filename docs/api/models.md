---
layout: default
title: Models
parent: API Documentation
nav_order: 3
---

[Documentation Home](../index.md) | [API Index](index.md)

# Models

Core entities used by the API and client synchronization flows.

## Session

- id: UUID
- date: Date
- exercises: [Exercise]

## Exercise

- id: UUID
- name: String

## Usage Notes

- Session is the top-level workout record.
- Exercise appears in catalogs, programs, and session logs.
- Stable IDs are required for reliable sync and merge logic.

## Related Pages

- Route behavior: [Endpoints](endpoints.md)
- Architecture context: [Architecture](architecture.md)
- Sync assumptions: [Sync](sync.md)

---

**Navigation**

- Previous: [Endpoints](endpoints.md)
- Next: [Sync](sync.md)
- Root docs: [Documentation Home](../index.md)