# Group Visibility Rules

This document defines how group post visibility works in Foodory.

## Rule types

## 1) `daily_unlock`

- Scope: current day in a specific group.
- Behavior:
  - A member must publish at least one image post in that group on the current day.
  - Until they post, they cannot see other members' posts from that day in that group.
  - After posting, today's posts become visible.
- Applies only to the group feed.

## 2) `sunday_reveal`

- Scope: current week in a specific group.
- Behavior:
  - Group posts created during the week are hidden.
  - Posts are revealed to group members on Sunday.

## Exception

- If a post is shared to **all friends**, that friends-audience visibility remains available regardless of group rules.

## Implementation notes

- Store normalized `dayKey` and `weekKey` on posts.
- Evaluate access using trusted backend logic (Cloud Functions + security rules).
- Client should show clear lock states and reasons:
  - "Post today to unlock today's group photos"
  - "Weekly photos reveal on Sunday"

