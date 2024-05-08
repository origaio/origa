---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: API Reference
slug: api-reference
---

# API Reference

This page contains information about API endpoints and how to trigger them.

## Authentication

The Origa API employs OAuth2 for secure authentication and authorization. To access protected endpoints, include the `Authorization` header with a valid Bearer token:

```bash
Authorization: Bearer YOUR_ACCESS_TOKEN
```
<br />
To obtain an access token, follow the OAuth2 authorization flow:

1. Request an authorization code by redirecting the user to:
    ```bash
    https://auth.origa.io/oauth2/authorize?response_type=code&amp;client_id=YOUR_CLIENT_ID&amp;redirect_uri=YOUR_REDIRECT_URI&amp;scope=read+write
    ```
<br />

2. Exchange the authorization code for an access token:
    ```bash 
    POST https://auth.origa.io/oauth2/token
    Content-Type: application/x-www-form-urlencoded

    grant_type=authorization_code&code=AUTH_CODE&client_id=YOUR_CLIENT_ID&client_secret=YOUR_CLIENT_SECRET&redirect_uri=YOUR_REDIRECT_URI
    ```
<br />

## Create Interview Request

```bash
POST /v1/interview/create-interview-request
```

Request Body:

```json
{
  "resume_url": "https://example.com/resume.pdf",
  "job_description_id": "71e49d1c-4fe5-4e02-ae2b-705c2f4dad7d",
  "candidate": {
    "name": "John Doe",
    "phone_number": "+1 (310) 818-8269"
  },
  "questionnaire_template_id": "tpl_123"
}
```

Response `201 Created`:

```json
{
  "request_id": "abc123",
  "status": "PENDING"
}
```

<br />

## Get Interview Request Status

```bash
GET /v1/interview/requests/{request_id}
```

Response `200 OK`:

```json
{
  "request_id": "abc123",
  "status": "COMPLETED",
  "screening_calls": [
    {
      "id": "call_1",
      "timestamp": "2023-06-01T14:30:00Z",
      "duration_minutes": 13,
      "status": "COMPLETED"
    },
    {
      "id": "call_2",
      "timestamp": "2023-06-02T10:15:00Z",
      "duration_minutes": 19,
      "status": "COMPLETED"
    }
  ],
  "assessment_results": {
  }
}
```


<br />