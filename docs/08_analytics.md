# Analytics

Once user activity has been collected and stored, the data can be analyzed to understand how users interact with an application.

Analytics turns individual events into useful information and patterns.

## From Events to Insights

For example, stored events might look like:

```text id="g5q8zq"
product_viewed
product_viewed
add_to_cart
product_viewed
checkout_started
purchase_completed
```

Analytics can transform these events into useful metrics:

```text id="zq1m7h"
10,000 Product Views
        ↓
6,000 Add to Cart
        ↓
4,000 Checkouts
        ↓
2,500 Purchases
```

## Common Metrics

Depending on the application, you can analyze:

* Event frequency
* Active users
* Session duration
* Feature usage
* Conversion rate
* Drop-off rate
* User journeys
* Retention

## Funnels

A funnel represents a sequence of actions that users are expected to complete.

For example, an e-commerce funnel:

```text id="q4x3kl"
Product View
     ↓
Add to Cart
     ↓
Checkout
     ↓
Purchase
```

If many users view a product but only a few purchase it, the data can help identify where users are dropping off.

## Feature Usage

Activity tracking can also show which features are being used.

```text id="t0f8qk"
Analytics      5,200 uses
Projects       4,100 uses
Reports        2,800 uses
Settings       1,100 uses
```

This can help teams understand which features are most important to their users.

## Session Analysis

Because events can be associated with sessions, it is also possible to analyze individual user journeys.

```text id="n4p8sx"
Session abc123

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

This provides context that individual events alone cannot provide.

## Custom Analytics

Different applications need different metrics.

An e-commerce application may focus on:

```text id="2z9x0k"
Add to Cart → Purchase
```

A SaaS application may focus on:

```text id="p4j7s1"
Signup → Feature Usage → Subscription
```

The analytics layer should therefore be flexible enough to work with custom events and application-specific requirements.

## The Goal

The purpose of analytics is not simply to collect large amounts of data.

The goal is to turn activity data into useful insights that help understand user behavior and improve the application.

```text id="qv4vcz"
Events
  ↓
Data
  ↓
Metrics
  ↓
Insights
  ↓
Better Decisions
```
