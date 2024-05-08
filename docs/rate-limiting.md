---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'Rate Limiting'
slug: rate-limiting
---
# Rate Limiting

To ensure fair usage and maintain optimal performance, the Origa API enforces rate limits on a per-client basis. The current rate limits are:

-   100 requests per minute
-   5000 requests per hour

When a client exceeds the rate limit, the API will return a `429 Too Many Requests` response with a `Retry-After` header indicating the number of seconds to wait before making the next request.