# Event Tracking

## What is an Event?

An event represents an action or activity that happens inside an application.

For example:

```text
page_view
button_click
product_viewed
add_to_cart
checkout_started
purchase_completed
```

Each event describes **what happened**.

---

## Event Structure

An event usually contains information about the action along with some additional context.

A simple event can look like:

```json
{
  "event": "button_click",
  "timestamp": "2026-10-08T10:00:00Z"
}
```

Additional data can be included when necessary:

```json
{
  "event": "add_to_cart",
  "timestamp": "2026-10-08T10:00:00Z",
  "data": {
    "product_id": "123",
    "quantity": 2
  }
}
```

The exact structure can be designed according to the application's requirements.

---

## Common Events

Different applications can track different types of events.

### General

```text
page_view
button_click
link_click
search
```

### E-commerce

```text
product_viewed
add_to_cart
checkout_started
purchase_completed
```

### SaaS

```text
signup
project_created
feature_used
subscription_started
```

---

## Custom Events

Not every application has the same user actions. That's why a tracking system should support custom events.

For example, an e-commerce application can define:

```text
product_added_to_wishlist
```

A SaaS application can define:

```text
report_generated
```

And an education platform can define:

```text
lesson_completed
```

The event system should be flexible enough to support application-specific events.

---

## Event Data

Events can contain additional data when it provides useful context.

For example:

```json
{
  "event": "product_viewed",
  "data": {
    "product_id": "123",
    "category": "electronics"
  }
}
```

Only data that is necessary for the purpose of the event should be collected.

Avoid including sensitive or unnecessary information in event data.

---

## The Basic Concept

Event tracking can be summarized as:

```text
User Action
     ↓
Create Event
     ↓
Attach Relevant Data
     ↓
Send Event
```

Once events are collected, they can be stored and analyzed to understand how users interact with the application.
