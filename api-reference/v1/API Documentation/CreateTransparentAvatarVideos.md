---
title: "Create Transparent Avatar Videos in WebM/MP4 Format"
description: "How to create transparent avatar videos in WebM/MP4 format."
---

This document will guide you on how to create a digital avatar video with a transparent background using the [Jogg.ai](http://Jogg.ai) API. This type of video is ideal for post-production compositing or for overlaying the digital avatar on other visual content such as web pages or apps.

### **Core Concepts: Alpha Channel & File Formats**

When you request a transparent background video, we add an **Alpha Channel** to the video file. This channel stores transparency information, making all areas of the video completely transparent except for the digital avatar itself.

- **Use Cases:**
  - Seamlessly overlaying the digital avatar onto another video clip in video editing software (e.g., Adobe Premiere, Final Cut Pro).
  - Placing the digital avatar video on a top layer in web development to interact with the content below.
- **File Format:** The standard MP4 format does not typically support an Alpha channel for transparency. Therefore, transparent background videos will be provided in `.webm` or `.mov` format. Please ensure your player or editing tool supports these formats.
- **Asynchronous Processing:** Like all video creation tasks, this process is asynchronous.

### Create Talking Avatar Video

Use the Create Talking Avatar Video API to control the output format by selecting the desired video specification with the `screen_style` parameter. This parameter controls the background style, allowing you to choose between videos with a background, green screen videos, or videos with a transparent background.

> Please note: If you need to output a **WebM** video with a transparent channel, please set the `caption` to false; otherwise, the WebM video cannot be generated.

Please refer to the [Create Talking Avatar Videos](/api-reference/v1/Create-Avatar-Videos/CreateAvatarVideo) for more details and refer to the next section for obtaining the avatar_id and voice_id.

## Here is a code example

Request Example：

```bash
curl --location --request POST 'https://api.jogg.ai/v1/create_video_from_talking_avatar' \
--header 'x-api-key: <your-api-key>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "script": "Hi, welcome to JoggAI and create longer videos with Talking Avatars in minutes!",
    "aspect_ratio": 0,
    "screen_style": 1,# Background style 1: With background, 2: Green screen, 3: Transparent background(Webm)
    "avatar_id": 127,
    "avatar_type": 0,
    "voice_id": "en-US-ChristopherNeural",
    "caption": true,
	"video_name":"my_video"   
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

### Consumption

The generated video consumption is based on its duration: 1 credit is consumed for every 2 minutes of video.