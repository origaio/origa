---
# snazzyDocs - DO NOT REMOVE OR EDIT BELOW THIS LINE
title: 'API Runtime Examples'
slug: api-examples
---
# Making API Requests

To interact with the Origa API endpoints, you can use any HTTP client or programming language that supports making HTTP requests. Here are a few examples using popular tools:

<br />

## cURL

```bash
curl -X POST \
  'https://api.origa.io/v1/interview/create-interview-request' \
  -H 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "resume_url": "https://example.com/resume.pdf",
    "job_description_id": "71e49d1c-4fe5-4e02-ae2b-705c2f4dad7d",
    "candidate": {
      "name": "John Doe",
      "phone_number": "+1 (310) 818-8269"
    },
    "questionnaire_template_id": "tpl_123"
  }'
```

<br />

## Python (using the `requests` library)

```python
import requests

url = 'https://api.origa.io/v1/interview/create-interview-request'
headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
    'Content-Type': 'application/json'
}
payload = {
    'resume_url': 'https://example.com/resume.pdf',
    'job_description_id': '71e49d1c-4fe5-4e02-ae2b-705c2f4dad7d',
    'candidate': {
        'name': 'John Doe',
        'phone_number': '+1 (310) 818-8269'
    },
    'questionnaire_template_id': 'tpl_123'
}

response = requests.post(url, headers=headers, json=payload)
print(response.json())
```

<br />

## JavaScript (using the `Axios` library)

```javascript
const axios = require('axios');

const url = 'https://api.origa.io/v1/interview/create-interview-request';
const headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
    'Content-Type': 'application/json'
};
const payload = {
    'resume_url': 'https://example.com/resume.pdf',
    'job_description_id': '71e49d1c-4fe5-4e02-ae2b-705c2f4dad7d',
    'candidate': {
        'name': 'John Doe',
        'phone_number': '+1 (310) 818-8269'
    },
    'questionnaire_template_id': 'tpl_123'
};

axios.post(url, payload, { headers })
    .then(response => {
        console.log(response.data);
    })
    .catch(error => {
        console.error(error);
    });
```

<br />

Make sure to replace `YOUR_ACCESS_TOKEN` with your actual OAuth2 access token in the examples above.