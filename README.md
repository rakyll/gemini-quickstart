# Gemini API quickstart

This page contains instruction on how to quickly get started with Gemini API.

Obtain an API key at [AI Studio][1].

Set your API key as an environmental variable: 

```sh
export GEMINI_API_KEY=<YOUR KEY>
```

Make your first request to the API:

```sh
$ curl "https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=$GEMINI_API_KEY" \
    -H 'Content-Type: application/json' \
    -X POST \
    -d '{
      "contents": [{
        "parts":[{"text": "Hi, how are you?"}]
      }]
    }'
```

Alternatively, use the client libraries such as the Python client library:

```sh
$ pip install -U google-generativeai
```

```python
import google.generativeai as genai
import os

genai.configure(api_key=os.environ["GEMINI_API_KEY"])

model = genai.GenerativeModel('gemini-1.5-flash')
response = model.generate_content("Hello, how are you?")
print(response.text)
```


[1]: https://aistudio.google.com/