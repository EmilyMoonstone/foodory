# MVP Scope

This MVP includes all currently requested features.

## Platform and backend

- Flutter app (iOS/Android first)
- Firebase:
  - Authentication
  - Firestore
  - Storage
  - Cloud Functions
  - Cloud Messaging

## Social model

- Friend system (request, accept, remove)
- Groups (create, invite, join, leave)
- Group roles (owner/admin/member)

## Posting

- Image post with audience selection:
  - all friends
  - one or multiple groups
  - both at the same time
- Post fields:
  - How much work was it?
  - How it tastes
  - Link to recipe
  - General text
- Optional post context:
  - Location tag / restaurant mode
  - "Cooked together" tags for other users

## Group visibility rules

- **Rule A (daily unlock):** In selected groups, a member can only see others' posts for the current day after posting their own image that day.
- **Rule B (weekly reveal):** In selected groups, weekly posts are revealed only on Sunday.
- **Exception:** Posts shared to **all friends** are always visible.

## Feed, history, and engagement

- Instagram-like feed UI
- Friends feed and group feed
- Reactions on posts
- Personal history/archive
- Group history/archive (rule-aware)
- Saved posts
- Collaborative cookbooks from saved posts (personal and group)
- Weekly group recap story (can be based on reactions/engagement)

