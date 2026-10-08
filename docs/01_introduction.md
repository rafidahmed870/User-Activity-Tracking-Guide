# Introduction

## What is User Activity Tracking?

User activity tracking is the process of collecting information about the actions users perform while interacting with a website or application.

Instead of recording the entire user session, activity tracking focuses on **specific actions as structured events**.

For example:
```text
Page View
   ↓
Button Click
   ↓
Product View
   ↓
Add to Cart
   ↓
Checkout
   ↓
Purchase
```

Each action can be recorded as an event and analyzed later.

---

## Why Track User Activity?

User activity data can help developers and product teams understand how their application is being used.

It can be used to:

- Understand user behavior
- Measure feature usage
- Find drop-off points
- Analyze user flows
- Improve user experience
- Measure conversions
- Identify frequently used features

For example, an e-commerce application might track:

```text
Product View → Add to Cart → Checkout → Purchase
```

This allows the application to understand how users move through the purchasing process. Otherside if anyone will visit checkout page but not complete the checkout or `add_to_cart` any product then you have the data.

---

## Activity Tracking vs Session Recording

Activity tracking and session recording are related, but they are not the same.

**Activity tracking** collects structured events:

```json
{
  "event": "add_to_cart",
  "product_id": "123"
}
```

**Session recording** attempts to recreate or replay a user's interaction with the application.

This project focuses on **activity tracking and event-based data collection**, not session recording.

---

## What is an Event?

An event represents something that happened inside an application.

For example:

```text
page_view
button_click
product_view
add_to_cart
checkout_started
purchase_completed
```

Events can also be customized according to the application's requirements.

A SaaS application might track:

```text
project_created
feature_used
team_member_invited
```

While an e-commerce application might track:

```text
product_viewed
cart_item_added
checkout_started
order_completed
```

---

## What We Will Learn

Throughout this documentation, we will explore how to:

1. Detect user activities
2. Convert activities into events
3. Send events to a backend
4. Store activity data
5. Associate events with sessions
6. Analyze collected data
7. Handle privacy and security

The goal is to understand the fundamental concepts behind building a simple and customizable **user activity tracking system**.