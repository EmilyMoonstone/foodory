# Architecture Overview

## Client

- **Framework:** Flutter
- **Style:** Instagram-like, media-first UI
- **Layers:**
  - Presentation (screens, widgets, state)
  - Domain (use cases, visibility logic orchestration)
  - Data (Firebase repositories)

## Firebase backend

- **Authentication:** user identity and sessions
- **Firestore:** app data (users, friendships, groups, posts, reactions, saves, cookbooks)
- **Storage:** post images
- **Cloud Functions:** trusted server-side logic:
  - enforce audience expansion
  - enforce visibility rule calculations
  - build weekly recap story payloads
- **Cloud Messaging:** notifications

## Security model

- Firestore and Storage rules enforce read/write access by friendship/group membership and audience.
- Rule-sensitive views are calculated server-side or via trusted fields written by Cloud Functions.
- Clients never decide access on their own.

## Non-functional requirements

- Fast feed loading (paging + cached thumbnails)
- Reliable uploads with retry
- Offline-friendly reads where possible
- Audit-friendly event timestamps (`createdAt`, `updatedAt`)

