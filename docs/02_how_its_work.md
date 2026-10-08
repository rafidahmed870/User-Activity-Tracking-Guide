# How It Works

User activity tracking works by detecting user actions, converting them into events, sending those events to a server, and storing them for later analysis.

## Basic Flow

```text
User Action
    ↓
Event Created
    ↓
Event Sent to Server
    ↓
Server Processes Event
    ↓
Event Stored
    ↓
Data Analyzed
```

### 1. User Action

The process starts when a user performs an action.

For example:

```text
User clicks "Add to Cart"
```

### 2. Event Created

The application converts that action into a structured event.

```json
{
  "event": "add_to_cart",
  "product_id": "123"
}
```

### 3. Event Sent to Server

The event is sent from the client to the backend through an API.

```text
Browser
   ↓
POST /api/events
```

### 4. Server Processes the Event

The server receives the event and can:

* Validate the data
* Add additional information
* Identify the session
* Apply security rules
* Prepare the event for storage

### 5. Event Stored

The processed event is stored in a database or another suitable storage system.

```text
Database

event: add_to_cart
product_id: 123
session_id: abc123
timestamp: ...
```

### 6. Data Analyzed

Stored events can later be used for analytics.

For example:

```text
1,000 Product Views
        ↓
600 Add to Cart
        ↓
400 Checkout
        ↓
250 Purchases
```

This helps identify how users move through a particular workflow.

## Complete Example

For an e-commerce application:

```text
User clicks "Add to Cart"
          ↓
"add_to_cart" event created
          ↓
Event sent to API
          ↓
Server validates event
          ↓
Event stored
          ↓
Analytics system processes data
```

The same flow can be used for almost any application. Only the events and the data associated with them need to change.

## The Core Idea

The tracking system can be summarized as:

```text
Action → Event → API → Storage → Analysis
```

The rest of this documentation will explain each part of this process in more detail.
