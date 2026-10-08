# User Activity Tracking

A simple, open-source guide for understanding and implementing **user activity tracking** in web applications.

This project explains how you can track different types of user interactions and activities on your website or application—similar to the activity data collected by services such as **Microsoft Clarity**.

> **Note:** This project focuses on **activity tracking**, not session recording.
> Session recording creates a replayable visual recording of a user's session, while activity tracking focuses on collecting structured information about what users do.

---

## About

Understanding how users interact with an application can help developers and product teams improve usability, identify problems, and understand user behavior.

This repository provides a practical and easy-to-understand guide for implementing user activity tracking from the ground up.

You will learn how to track activities such as:

* Page visits
* Button clicks
* Link clicks
* Form interactions
* User actions
* Custom events
* Session-related activities
* Other application-specific events

The goal is to explain **what happens behind the scenes when user activity is tracked** and how you can build a similar system yourself.

---

## Project Goals

This project aims to:

* Explain the fundamentals of user activity tracking
* Show how client-side activity can be collected
* Explain how activity data can be sent to a backend
* Demonstrate how events can be structured
* Explain how activity data can be stored
* Show how collected data can be analyzed
* Discuss privacy and security considerations
* Provide practical implementation examples

The project is intended primarily as a **learning and documentation resource**.

---

## Activity Tracking vs Session Recording

These two concepts are related but not the same.

### Activity Tracking

Activity tracking records structured events describing what a user does.

For example:

```json
{
  "event": "button_click",
  "element": "signup_button",
  "page": "/signup",
  "timestamp": "2026-10-08T00:30:00Z"
}
```

The system knows that the user clicked a particular button, but it does not create a video-like replay of the page.

### Session Recording

Session recording attempts to recreate or record a user's interaction with a website.

For example, a session recording system may capture:

* Mouse movement
* Clicks
* Scrolling
* DOM changes
* Page navigation
* User interaction sequences

This can then be presented as a replayable session.

**This repository focuses on the first approach: structured user activity tracking.**

---

## Basic Architecture

A simple activity tracking system can be represented as:

```text
┌─────────────────────┐
│     User / Browser  │
└──────────┬──────────┘
           │
           │ User Interaction
           ▼
┌─────────────────────┐
│   Tracking Client   │
│                     │
│ Clicks              │
│ Page Views          │
│ Forms               │
│ Custom Events       │
└──────────┬──────────┘
           │
           │ Send Event
           ▼
┌─────────────────────┐
│      Backend API    │
└──────────┬──────────┘
           │
           │ Store
           ▼
┌─────────────────────┐
│      Database       │
└──────────┬──────────┘
           │
           │ Analyze / Action
           ▼
┌─────────────────────┐
│    Dashboard /      │
│    Analytics        │
└─────────────────────┘
```

---

## How It Works

The basic workflow is:

```text
User performs an action
        ↓
Tracking system detects the action
        ↓
Event is created
        ↓
Event is sent to the backend
        ↓
Backend validates the event
        ↓
Event is stored
        ↓
Data can be analyzed later
```

For example, when a user clicks a button:

```text
User clicks "Sign Up"
        ↓
Tracking code detects click
        ↓
Create "button_click" event
        ↓
Send event to API
        ↓
Store event
```

---

## Privacy & Security

User activity tracking must be implemented responsibly.

Tracking does **not** mean collecting everything available in the browser.

Avoid unnecessarily collecting sensitive information such as:

* Passwords
* Authentication tokens
* Payment information
* Private messages
* Personal secrets
* Sensitive form inputs

Sensitive fields should be excluded or masked whenever possible.

For example:

```javascript
track("form_submit", {
    form: "signup"
});
```

Instead of sending the actual contents of every input field.

### Important Considerations

Depending on your application's location and users, you may also need to consider:

* Privacy laws and regulations
* User consent
* Cookie policies
* Data retention
* Data deletion
* Data access
* Anonymization
* Data security

This repository is a technical guide and does not constitute legal advice.

---

## Security Considerations

The tracking API should be treated as an untrusted public endpoint.

The backend should consider:

* Input validation
* Rate limiting
* Request authentication where appropriate
* Payload size limits
* Abuse prevention
* Data sanitization
* Access control
* Secure transport using HTTPS

Never trust tracking data simply because it came from your own frontend.

A malicious client can manually send requests to your tracking endpoint.

---

## What You Will Learn

Throughout this repository, you will learn how to build the different parts of an activity tracking system.

### 1. Client-Side Tracking

How to detect user interactions from the browser.

### 2. Event Collection

How to convert interactions into structured events.

### 3. Event Transmission

How events can be sent to a backend API.

### 4. Backend Processing

How the server receives and validates tracking data.

### 5. Data Storage

How activity events can be stored efficiently.

### 6. Session Identification

How multiple events can be associated with a particular browsing session.

### 7. Analytics

How stored activity data can be analyzed to understand user behavior.

### 8. Privacy

How to design tracking without unnecessarily collecting sensitive information.

---

## Example Use Cases

User activity tracking can be used for:

* **E-commerce:** Product views, add to cart, checkout, purchases
* **SaaS:** Signups, feature usage, projects, subscriptions
* **Content:** Views, likes, shares, downloads
* **Education:** Course views, lessons, quiz completion
* **Marketplace:** Searches, product views, purchases
* **Social Apps:** Posts, likes, comments, follows

For example:

```text
Product View → Add to Cart → Checkout → Purchase
```

The events can be customized based on the application's requirements.

---

## Contributing

Contributions are welcome!

You can contribute by:

* Improving documentation
* Fixing mistakes
* Adding examples
* Improving explanations
* Adding implementation guides
* Reporting issues
* Suggesting new topics

Before contributing, please read:

* [Contributing Guide](CONTRIBUTING.md)
* [Code of Conduct](CODE_OF_CONDUCT.md)

---

## Support the Project

If you find this project useful:

* ⭐ Star the repository
* 🐛 Report issues
* 💡 Suggest improvements
* 🔧 Submit pull requests
* 📖 Help improve the documentation

Open-source projects become better through community contributions.

---

**Built for learning, experimentation, and understanding how user activity tracking works.**
