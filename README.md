# Codex Python boilerplate

Boilerplate to get started with OpenAI Codex


```python
import os
import openai

# load API Key ( https://beta.openai.com/account/api-keys )
openai.api_key = "YOUR_API_KEY"

def generate_function(description):
    response = openai.Completion.create(
        model="code-davinci-002",
        prompt=f"Python function to do the following: {description}\n\n```python\n",
        temperature=0,
        max_tokens=200,
        top_p=1,
        frequency_penalty=0.3,
        presence_penalty=0.3,
        stop=["```"]
    )
    return response.choices[0].text

print("What should the function do?")
description = input()
print(generate_function(description))
```
