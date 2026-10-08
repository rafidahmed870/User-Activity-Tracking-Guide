# Session Management

A session is a group of user activities that happen during a particular period of interaction with an application.

Session management allows multiple events to be connected together so we can understand the user's journey.

## Why Sessions?

Consider these events:

```text
page_view
product_viewed
add_to_cart
checkout_started
purchase_completed
```

Without a session identifier, it can be difficult to know whether these events belong to the same user journey.

A session can connect them:

```text
Session: abc123

page_view
    ↓
product_viewed
    ↓
add_to_cart
    ↓
checkout_started
    ↓
purchase_completed
```

## Session ID

A unique identifier can be assigned to each session.

For example:

```json id="m3hxzq"
{
  "event": "add_to_cart",
  "session_id": "abc123",
  "timestamp": "2026-10-08T10:00:00Z"
}
```

Every event belonging to that session can use the same `session_id`.

## Creating a Session

A new session can be created when a user starts interacting with the application.

```text id="3m3u6f"
User opens application
        ↓
Check for existing session
        ↓
No session found
        ↓
Create session ID
        ↓
Track activities
```

The session identifier can then be reused for subsequent events.

## Session Expiration

Sessions should not continue indefinitely.

A session can expire after a period of inactivity.

For example:

```text id="6yr5o4"
User Activity
     ↓
No activity
     ↓
Session timeout
     ↓
New activity
     ↓
New Session
```

The exact timeout depends on the application's requirements.

## Anonymous vs Authenticated Users

A tracking system can work with both anonymous and authenticated users.

### Anonymous

```text id="d2j6lq"
session_id: abc123
user_id: null
```

### Authenticated

```text id="p2iz5j"
session_id: abc123
user_id: user_456
```

A `session_id` represents a browsing session, while a `user_id` can represent the authenticated account.

These identifiers should not be confused with each other.

## Session-Based Analysis

Once events are connected to sessions, user journeys become easier to analyze.

For example:

```text id="y2p0i1"
Session abc123

10:00  page_view
10:01  product_viewed
10:03  add_to_cart
10:05  checkout_started
10:07  purchase_completed
```

This allows analytics systems to answer questions such as:

* What actions happened during a session?
* Where did users leave a workflow?
* How long did a session last?
* Which events commonly happen together?

## Basic Flow

```text id="p0u3wh"
User
 ↓
Session Created
 ↓
Activity Detected
 ↓
Event + Session ID
 ↓
Stored
 ↓
Session Analysis
```

Sessions provide the connection between individual events and the overall user journey.
