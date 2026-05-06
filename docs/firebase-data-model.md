# Firebase Data Model (Draft)

> Collection names and fields can evolve, but this is the MVP baseline.

## `users`

- `displayName`
- `photoUrl`
- `bio`
- `createdAt`
- `settings` (map)

## `friendships`

- `users` (array of 2 user IDs)
- `status` (`pending` | `accepted` | `blocked`)
- `requestedBy`
- `createdAt`
- `updatedAt`

## `groups`

- `name`
- `photoUrl`
- `description`
- `ownerId`
- `memberIds` (array)
- `admins` (array)
- `visibilityRule` (`none` | `daily_unlock` | `sunday_reveal`)
- `createdAt`
- `updatedAt`

## `posts`

- `authorId`
- `imageUrl`
- `text`
- `workLevel` (e.g. 1-5)
- `tasteRating` (e.g. 1-5)
- `recipeLink`
- `audience` (map):
  - `toAllFriends` (bool)
  - `groupIds` (array)
- `taggedUserIds` (array) // cooked together
- `location` (map: placeId, name, lat, lng)
- `isRestaurantMode` (bool)
- `createdAt`
- `updatedAt`
- `weekKey` (e.g. `2026-W19`) for weekly grouping
- `dayKey` (e.g. `2026-05-06`) for daily rule checks

## `reactions`

- `postId`
- `userId`
- `emoji` (or `like`)
- `createdAt`

## `savedPosts`

- `userId`
- `postId`
- `createdAt`

## `cookbooks`

- `name`
- `ownerType` (`user` | `group`)
- `ownerId`
- `postIds` (array or subcollection)
- `createdAt`
- `updatedAt`

## `weeklyRecaps`

- `groupId`
- `weekKey`
- `topPosts` (array of post references/IDs)
- `metrics` (map: reactions count, participants, etc.)
- `generatedAt`

## Suggested subcollections (optional)

- `groups/{groupId}/members`
- `posts/{postId}/comments`
- `posts/{postId}/reactions` (if not using top-level `reactions`)

