---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: Webhooks
slug: webhooks
---
# Webhooks

The Origa API supports webhooks to provide real-time notifications on interview request updates and candidate assessment results. To configure webhooks, follow these steps:

1.  Set up a webhook endpoint on your server to receive POST requests from Origa.
2.  Register your webhook URL in the Origa developer dashboard.
3.  Handle incoming webhook events and process them according to your application's requirements.

<br />

Webhook Event Example:

```json
{
  "event_type": "screening.completed",
  "timestamp": "2023-06-01T15:00:00Z",
  "payload": {
    "request_id": "abc123",
    "interview_id": "int_123",
    "assessment_results": {
    }
  }
}
```