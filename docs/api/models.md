---
layout: default
title: Models
parent: API Documentation
nav_order: 3
---

[Documentation Home](../index.md) | [API Index](index.md)

# Models

Core API shapes that are implemented today.

## Auth Session Response

```json
{
  "user": {
    "id": "uuid",
    "displayName": "Showcase Account",
    "username": "showcase"
  },
  "session": {
    "accessToken": "gymtracker-access-token",
    "expiresAt": "2026-04-09T15:05:22.435Z"
  },
  "linkedProvider": {
    "provider": "interact",
    "providerUserId": "provider-user-id",
    "displayName": "Showcase Account",
    "username": "showcase"
  }
}
```

## Exercise DTO

```json
{
  "id": "Barbell_Bench_Press_-_Medium_Grip",
  "source": "catalog",
  "name": "Bench Press",
  "type": "strength",
  "aliases": [],
  "primaryMuscles": ["chest"],
  "secondaryMuscles": ["triceps"],
  "equipment": "barbell",
  "category": "strength",
  "instructions": [],
  "images": [],
  "isUserCreated": false,
  "isArchived": false,
  "isEditable": true,
  "isDeletable": false,
  "updatedAt": null
}
```

Identity rules:

- user-created exercise:
	- `id` is GymTracker UUID
	- `source = "user"`
- ExerciseDB-backed exercise:
	- `id` is stable `npId`
	- `source = "catalog"`

Important iOS mapping rule:

- catalog DTO `id` -> `Exercise.npId`
- user DTO `id` -> `Exercise.id`
- catalog DTO `id` is never the local SwiftData row UUID

## Session List Item

```json
{
  "id": "uuid",
  "routineId": null,
  "startedAt": "2026-04-08T09:00:00.000Z",
  "completedAt": null,
  "notes": "Push day",
  "updatedAt": "2026-04-08T10:05:00.000Z"
}
```

## Session Detail Aggregate

```json
{
  "id": "uuid",
  "routineId": null,
  "startedAt": "2026-04-08T09:00:00.000Z",
  "completedAt": "2026-04-08T10:05:00.000Z",
  "notes": "",
  "entries": [
    {
      "id": "uuid",
      "order": 0,
      "exerciseId": "Barbell_Bench_Press_-_Medium_Grip",
      "isCompleted": true,
      "sets": [
        {
          "id": "uuid",
          "order": 0,
          "notes": null,
          "durationSeconds": null,
          "distance": null,
          "distanceUnit": null,
          "paceSeconds": null,
          "restSeconds": 90,
          "isCompleted": true,
          "isDropSet": false,
          "reps": [
            {
              "id": "uuid",
              "weight": 185,
              "weightUnit": "lb",
              "count": 5,
              "notes": null,
              "baseWeight": null,
              "perSideWeight": null,
              "isPerSide": false
            }
          ]
        }
      ]
    }
  ],
  "updatedAt": "2026-04-08T10:05:00.000Z"
}
```

## Dashboard Summary

```json
{
  "from": "2026-03-12",
  "to": "2026-04-08",
  "totalSessions": 8,
  "totalVolume": 12450,
  "averageVolumePerSession": 1556.25,
  "lastWorkoutDate": "2026-04-08T18:05:00.000Z"
}
```

## Session Volume Report

```json
{
  "bucket": "day",
  "from": "2026-03-12",
  "to": "2026-04-08",
  "items": [
    {
      "start": "2026-04-01T00:00:00.000Z",
      "end": "2026-04-02T00:00:00.000Z",
      "totalVolume": 4200,
      "sessionCount": 1
    }
  ]
}
```

## Related Pages

- Route behavior: [Endpoints](endpoints.md)
- Architecture context: [Architecture](architecture.md)
- Sync-aligned conventions: [Sync](sync.md)

---

**Navigation**

- Previous: [Endpoints](endpoints.md)
- Next: [Sync](sync.md)
- Root docs: [Documentation Home](../index.md)
