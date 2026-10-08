# Privacy & Security

User activity tracking involves collecting information about how people interact with an application. It should therefore be designed with privacy and security in mind.

## Collect Only What You Need

Track information that is useful for your analytics.

For example:

```json
{
  "event": "add_to_cart",
  "product_id": "123"
}
```

Avoid collecting unnecessary personal or sensitive information.

## Sensitive Data

Tracking systems should avoid collecting data such as:

* Passwords
* Authentication tokens
* Payment card information
* Private messages
* Sensitive form values

For example, track:

```text
form_submitted
```

instead of storing the actual contents of sensitive form fields.

## Data Security

Activity data should be protected like any other application data.

Consider using:

* HTTPS
* Input validation
* Access control
* Rate limiting
* Secure authentication
* Data encryption where appropriate

The tracking API should always treat client-provided data as untrusted.

## User Privacy

Depending on the application and where its users are located, privacy requirements may apply.

Consider:

* User consent
* Privacy policies
* Data retention
* Data deletion
* Data access
* Anonymization

The exact requirements depend on the application and applicable laws.

## Data Retention

Tracking data should not necessarily be stored forever.

Define an appropriate retention period and remove data that is no longer needed.

```text
Collect
   ↓
Store
   ↓
Use for Analytics
   ↓
Retention Period Ends
   ↓
Delete / Anonymize
```

## Anonymous Tracking

When possible, applications can track activity without directly identifying users.

For example:

```json
{
  "event": "page_view",
  "session_id": "abc123"
}
```

A session identifier can provide useful context without requiring personally identifiable information.

## The Goal

Good activity tracking should balance **useful analytics with responsible data collection**.

```text
Useful Data
     +
Privacy
     +
Security
     ↓
Responsible Tracking
```

Always collect the minimum information necessary to achieve the intended purpose of the tracking system.
