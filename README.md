---
title: "Markdown Page"
permalink: /markdown/
---

# OpenAI Playground Manual


## Table of Contents

<!---toc start-->

* [OpenAI Playground Manual](#openai-playground-manual)
  * [Table of Contents](#table-of-contents)
  * [Introduction](#introduction)
  * [Features](#features)
  * [Guide](#guide)
    * [Tips](#tips)
    * [Examples](#examples)
    * [FAQ](#frequently-asked-questions)  

<!---toc end-->



## Introduction 

The OpenAI API provides a simple interface to state-of-the-art AI models 
for natural language processing, image generation, semantic search, and speech recognition. Follow this guide to learn how to generate human-like responses to natural language prompts, create vector embeddings for semantic search, and generate images from textual descriptions.

## Features

### Communicate with the OpenAI servers through an API

This allows you to write programs that communicate with things like chatgpt and prompt responses from it. This makes it much easier to implement AI generation into some program and software. 

> ⚠️ *AI can be wrong and can be a hindrance in some situations*: Be very careful here!

### Configure responses through the openai Website

![Playground Screenshot](/writing/graphics/open-ai-playground-interface-gpt3.webp)

Through this you can control the amount of content it generates how random or deterministic it is and how likely it is to repeat itself when giving multiple prompts. You can change the model that it's using like gpt 3.5 or gpt 4.0 depending on what you wan't to use it for

> 💡*Tip: You might wan't to use a more lightweight version of chatgpt if you aren't planning on asking complicated problems i.e. gpt-4o-mini*

## Guide

Before you do anything your going to need to install the openai dependencies for your chosen language

### Command:

- **Python:** `pip install openai`
- **Javascript** `npm install openai`

After you do this your going to need to sign into your account and generate an **API-KEY**. Follow the steps below to do this

### Steps:

- Click on Account **Settings**
- Go to **API-KEYS**

Following this it should take you to a screen that looks like this.

![API-key Screen shot](/writing/graphics/Screenshot%202024-12-11%20120822.jpg)

- Click create new secret key
- copy this key and then set as an environment variable this is dependent on your system
  - **Mac/Linux:** `export OPENAI_API_KEY="your_api_key_here"`
  - **Windows:** `setx OPENAI_API_KEY "your_api_key_here"`
  - You then can simply implement OpenAI into your code to communicate with the server.



### Tips

- ⚠️ *If your making an open source project do not put your API-key in the repo you could be charged for uses that aren't you*



### Examples

#### **Python Example:**
```python
from openai import OpenAI
client = OpenAI()

completion = client.chat.completions.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {
            "role": "user",
            "content": "Write a haiku about recursion in programming."
        }
    ]
)

print(completion.choices[0].message)
```

#### **Javascript Example:**

```javascript
import OpenAI from "openai";
const openai = new OpenAI();

const completion = await openai.chat.completions.create({
    model: "gpt-4o-mini",
    messages: [
        { role: "system", content: "You are a helpful assistant." },
        {
            role: "user",
            content: "Write a haiku about recursion in programming.",
        },
    ],
});

console.log(completion.choices[0].message);
```

### Frequently Asked Questions

**How can I contact support?**

> If you already have an account, Login and click the help button. 
> If you don't have an account or can't login, got to [help.openai.com](https://help.openai.com/en/)

**How much does it cost to use ChatGPT?**

> ChatGPT is free to use, though some features do cost money and they have subscription plans available. [pricing page](https://openai.com/chatgpt/pricing/).

[go back](../)

