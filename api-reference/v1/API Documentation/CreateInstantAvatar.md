---
title: "Create Instant Avatar"
description: "How to create instant avatar."
---

## Create Instant Avatar

You can customize your avatar using the Create Instant Avatar API. Input the video path via `origin_url` to create your digital avatar.

Recommended input video specifications: 1080P at 30FPS. If you provide a video with higher specifications, we will automatically convert it to that specification.

Consumption：Each API call to "Create Instant Avatar" consumes 100 credits.

### Base URL

\`https://api-services.jogg.ai\`

### Endpoint

[/api-reference/v1/endpoint/CreateInstantAvatar](/api-reference/v1/endpoint/CreateInstantAvatar)

### Request Body

```json
{
    "origin_url": "string",  // Required. URL of the source video
    "name": "string"         // Required. Name for the avatar
}
```

### Response

```json
{
    "code": 0,
    "msg": "success",
    "data": {
        "id": 123  // The ID of the created avatar
    }
}
```

### Error Codes

* 401: Unauthorized - Invalid API key

* 400: Bad Request - Missing required fields

* 500: Internal Server Error

## Delete Custom Avatar

You can delete a customized avatar using the Delete Instant Avatar API by selecting it with the avatar's `ID`.

### Endpoint

[/api-reference/v1/endpoint/DeleteInstantAvatar](/api-reference/v1/endpoint/DeleteInstantAvatar)

### Request Body

```json
{
    "id": 123  // Required. The ID of the avatar to delete
}
```

### Response

Success:

```json
{
    "code": 0,
    "msg": "success"
}
```

### Error Codes

* 401: Unauthorized - Invalid API key

* 400: Bad Request - Invalid avatar ID

* 404: Not Found - Avatar not found

* 500: Internal Server Error