---
title: "Using Audio Source as Voice"
description: "create avatar video by uploading audio."
---

## Introduction

This document provides a detailed guide on how to use your own audio file as a voice source to generate a digital avatar video via the [Jogg.ai](http://Jogg.ai) API. This feature allows the digital avatar model to perform lip-syncing to any voice you provide (e.g., your own recording).

---

### **Core Concept: Audio-Driven Lip-Sync**

Unlike using a preset voice (`voice_id`), the core of this feature is **"audio-first"**. You provide an audio file containing speech, and our system will analyze this audio to drive the digital avatar's mouth movements to precisely match the pronunciation in the audio.

- **Asynchronous Processing:** This process is also asynchronous. After submitting the task, you will immediately receive a `project_id`, and the video will be processed in the background.
- **Audio is Key:** The voice of the character in the video will come entirely from the audio file you provide.
- **Automatic Lip-Sync:** The system automatically analyzes the audio waveform and phonemes to generate highly synchronized lip animations.

### Upload Audio

You can upload audio to obtain your asset_id.

Please refer to the [Upload Media](/api-reference/v1/UploadFile/UploadFile) for more details.

```powershell
curl --request POST \
  --url https://api.jogg.ai/v1/upload/asset \
  --header 'Content-Type: application/json' \
  --header 'x-api-key: <api-key>' \
--data-raw '{
    "filename":"1.jpg"
}'
```

#### Obtain the Signed URL

Before uploading a file, you need to obtain a signed URL via an API request. 
Here’s an example response:

```json
{
  "rid": "ab3329c49f320dba9a57d742195d930b",
  "code": 0,
  "msg": "<string>",
  "data": {
    "sign_url": "<string>",
    "asset_id": "<string>"
  }
}
```

sign_url: Use this URL to upload the file.

#### Use cURL to Upload the File

Use the following cURL command to upload the file to the server. Make sure to replace \<file-binary-data\> with the actual binary data of the file.

```powershell
curl --location --request PUT '<sign_url>' \
--header 'Content-Type: application/octet-stream' \
--data-binary '<file-binary-data>'
```

```json
{
    "rid": "1e66bb40e189f7fb2936330863c1468e",
    "code": 0,
    "msg": "success"
}
```

### Create Talking Avatar Video

Please refer to the [Create Talking Avatar Videos](/api-reference/v1/Create-Avatar-Videos/CreateAvatarVideo) for more details.

```bash
curl --location --request POST 'https://api.jogg.ai/v1/create_video_from_talking_avatar' \
--header 'x-api-key: <your-api-key>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "audio_url": <your-audio-url>,
    "aspect_ratio": 0,
    "screen_style": 1,
    "avatar_id": 127,
    "avatar_type": 0,
    "caption": true   
}'
```

Response example:

```json
{
    "rid": "d43b3a5999e31b7e7a62ee5ef84d411d",
    "code": 0,
    "msg": "success",
    "data": {
        "project_id": "<project-id>"   
    }
}
```

### Get the generated video

Use the project_id obtained from the "Generate Video from Product Information" step to retrieve details about the video generation, including status and duration. Access the generated video using the video_url.

Please refer to the[ GetGeneratedVideo](/api-reference/v1/GetGeneratedVideo/GetGeneratedVideo) for the full options of enums.

```bash
curl --location --request GET 'https://api.jogg.ai/v1/project?project_id=fa6228c0f52c4f3986e88f7ffa5d2864' \
--header 'x-api-key: <your-api-key>' \
```

Response example:

```json
{
    "code": 0,
    "msg": "success",
    "data": {
        "id": "fa6228c0f52c4f3986e88f7ffa5d2864",
        "title": "welcome to jogg.ai",
        "status": 4,
        "status_desc": "success",
        "video_duration": 6,
        "video_url": "https://res.jogg.ai/video.webm",
        "cover_url": "https://res.jogg.ai/cover.png",
        "created_at": 1732806631
    }
}
```