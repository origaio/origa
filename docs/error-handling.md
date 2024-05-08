---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Error Handling'
slug: error-handling
---
# Error Handling

The Origa API uses standard HTTP status codes to indicate the success or failure of API requests. In case of an error, the API will return a JSON response with an `error` object containing `code` and `message` fields.

Example Error Response:

```json
{
  "error": {
    "code": "invalid_request",
    "message": "Missing required parameter: resume_url"
  }
}
```