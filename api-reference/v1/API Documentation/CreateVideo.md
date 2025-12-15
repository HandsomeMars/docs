---
title: 'Create Video from Templates'
description: 'How to create video from templates with API.'
---

### Request Parameters

```java
{
    "text": "string",   # Text script replacement; default is "default"
    "lang": "string",   # Language; options include:
                                "english" 
                                "filipino"
                                "french"
                                "german"
                                "hindi"
                                "indonesian"
                                "italian"
                                "japanese"
                                "korean"
                                "malay"
                                "portuguese"
                                "russian"
                                "spanish"
                                "thai"
                                "vietnamese"
                                "arabic"
                                "greek"
                                "turkish"
                                "slovenian"
                                "croatian"
                                "romanian"
                                "chinese" (Simplified Chinese)
                                "bengali"
                                "urdu"
                                "hungarian"
                                "traditional-chinese" (Traditional Chinese)
                                "polish"
    "template_id": 0,                # Template ID
    "template_type": "string",       # Template type; default is "user"
    "dp_id": 0,                      # Digital person ID; default is 0
    "timbre_td": 0,                  # Timbre ID; default is 0
    "without_tts": 0,                # Whether to use TTS to redo the voice; 0 for yes, 1 for no
    "variables": [                   # Array for variable replacement
        {                            # Type of variable: image, video, text
            "name": "string",        # Name of the variable to be replaced as set in the template
            "properties": {          # Properties of the variable
                "url": "string"      # URL for the replacement image/video
            },                       # Content for text replacement
            "type": "string"
        }
    ]
}

```

### Response

```java
{
    "code": 0,
    "msg": "success",
    "data": {
        "prj_id": "620b079caf3a4d2abd2c7ce095fb4e69"    # Project ID
    }
}
```

### Request Example

```json
curl --location --request POST 'https://api-services.jogg.ai/open/render' 
--header 'x-api-key: <your-api-key>' 
--header 'Content-Type: application/json' 
--data-raw '{
    "text": "default",
    "lang": "english",
    "template_id": 96,
    "template_type": "user",
    "dp_id": 0,
    "timbre_td": 0,
    "without_tts": 1,
    "variables": [
        {
            "name": "logo",
            "properties": {
                "url": "images/image.png"
            },
            "type": "image"
        },
        {
            "name": "discount",
            "properties": {
                "content": "66"
            },
            "type": "text"
        }
    ]
}'
```