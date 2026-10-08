# Data Storage

Once activity events are received and processed by the server, they need to be stored somewhere so they can be analyzed later.

The storage method depends on the application's requirements, event volume, and analytics needs.

## Basic Flow

```text
Event
  ↓
Backend
  ↓
Validation
  ↓
Storage
```

## What Should Be Stored?

A tracking event might contain:

```json
{
  "event": "add_to_cart",
  "session_id": "abc123",
  "timestamp": "2026-10-08T10:00:00Z",
  "data": {
    "product_id": "123",
    "quantity": 2
  }
}
```

Common fields include:

* Event name
* Timestamp
* Session identifier
* Page or route
* Event-specific data

Only information that is useful for analytics should be stored.

## Choosing a Storage System

Activity data can be stored using different types of systems, such as:

* Relational databases
* Document databases
* Analytics databases
* Event or log storage systems

For a small project, a regular database may be enough. Larger systems may require storage designed specifically for high-volume event data.

## Event Records

Each activity can be stored as an individual event:

```text
session_001
 ├── page_view
 ├── product_viewed
 ├── add_to_cart
 └── checkout_started

session_002
 ├── page_view
 ├── product_viewed
 └── purchase_completed
```

This makes it possible to reconstruct user flows and analyze activity over time.

## Data Retention

Tracking data can grow quickly as the number of users and events increases.

A system should therefore consider:

* How long events should be stored
* When old data should be deleted
* How much storage is required
* Whether older data should be archived

Keeping data longer than necessary can increase both storage costs and privacy risks.

## Privacy

Avoid storing sensitive information unless it is genuinely required.

For example, avoid putting passwords, payment information, authentication tokens, or private form contents inside tracking events.

```text
Good:

event: "checkout_started"
order_id: "123"


Avoid:

event: "form_submitted"
password: "..."
card_number: "..."
```

## The Goal

The purpose of storing activity data is to make it available for later analysis.

```text
Collect
   ↓
Process
   ↓
Store
   ↓
Analyze
   ↓
Understand User Behavior
```

The next step is connecting related events together using **sessions**.
