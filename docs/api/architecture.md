[Documentation Home](../index.md) | [API Index](index.md)

# Architecture

System components that support workout tracking and synchronization.

## Components

- iOS app: SwiftUI interface with SwiftData local persistence.
- Backend: Node.js and Express APIs for data access and sync.
- Database: MongoDB for persistent server-side records.

## Responsibility Split

- Client handles responsive offline-first interactions.
- Backend owns validation, persistence, and API contract.
- Sync flow coordinates eventual consistency between local and remote data.

## Related Pages

- Contract details: [Endpoints](endpoints.md)
- Data shapes: [Models](models.md)
- Sync strategy: [Sync](sync.md)

---

**Navigation**

- Previous: [API Index](index.md)
- Next: [Endpoints](endpoints.md)
- Root docs: [Documentation Home](../index.md)