---
title: 'AI Scripts'
description: 'How to generate AI scripts from product?'
---

## Introduction

Using the JoggAI API, you can generate AI scripts effortlessly. Simply provide the product information or the `product_id` generated in the [Upload URL to create product](/api-reference/v1/URL-to-Video/UploadURL), and you can create several different styles of product introduction scripts.

## Quick Start

### Generate Scripts from product

Provide the product information or the `product_id` generated at the "Upload URL to Create Product" endpoint, and you can create several different styles of product introduction scripts.
If you do not provide the `product_id`, then the product's `name` and `description` are required.

Please refer to the [AI Scripts](/api-reference/v1/AI-Scripts/AI-Scripts) for more details.

```bash
curl --location --request POST 'https://api.jogg.ai/v1/ai_scripts' \
--header 'x-api-key: <your-api-key>' \
--header 'User-Agent: Apifox/1.0.0 (https://apifox.com)' \
--header 'Content-Type: application/json' \
--data-raw '{
    "product_id": "",
    "name": "Owala FreeSip Insulated Stainless Steel Water Bottle with Straw for Sports, Travel, and School BPA-Free Sports Water Bottle, 24 oz, Shy Marshmallow",
    "description": "24-ounce insulated stainless-steel water bottle with a FreeSip spout and push-button lid with lock\nPatented FreeSip spout designed for either sipping upright through the built-in straw or tilting back to swig from the spout opening\nProtective push-to-open lid keeps spout clean; convenient carry loop doubles as a lock\nDouble-wall insulation keeps drinks cold for up to 24 hours; wide opening for cleaning and adding ice; cup holder-friendly base\nBPA, lead, and phthalate-free; hand wash cup, dishwasher-safe lid; not for use with hot liquids",
    "target_audience": "test",
    "video_length": "15",
    "language": "english"
}'
```

Response example:

```json

{
    "rid": "e1e2ccf9a266619517eb70ab35393ed6",
    "code": 0,
    "msg": "success",
    "data": {
        "generated_scripts": [
            {
                "script_paragraphs": "Ever tried drinking water while running? It's like a comedy show!You either spill it all over or look like a fish out of water.Then I found the Owala FreeSip bottle—game changer, folks!Sip upright or swig like a champ, no spills in sight!Stay hydrated with style—24 oz of pure refreshment, Shy Marshmallow!",
                "script_style": "Storytime"
            },
            {
                "script_paragraphs": "Stay refreshed with the Owala FreeSip's 24-ounce capacity!Enjoy sipping upright or swigging from the spout—your choice!Double-wall insulation keeps drinks cold for 24 hours, amazing right?BPA-free and easy to clean—perfect for sports, travel, or school!Grab yours today and elevate your hydration game!",
                "script_style": "Top 3 reasons"
            },
            {
                "script_paragraphs": "Meet the Owala FreeSip Water Bottle: your hydration superhero!Sip upright through the straw or tilt for a swig—your choice!Double-wall insulation keeps drinks cold for 24 hours. Chill vibes only!BPA-free and easy to clean; it’s a bottle, not a science experiment!Perfect for sports, travel, or school—stay hydrated in style!",
                "script_style": "Data"
            },
            {
                "script_paragraphs": "Ever tried drinking water while running? It's like a comedy show!You tilt, you sip, and suddenly, it's a water fountain explosion.Then there’s the awkward moment when you need a straw, but don’t have one.Imagine a world where sipping and swigging are both possible, effortlessly.Meet the Owala FreeSip Water Bottle, your hydration hero for every adventure!",
                "script_style": "Light marketing"
            }
        ]
    }
}
```

### Use the script for video generation.

You can replace the script using the `override_script` parameter in the [Generate Video from Product Information](/api-reference/v1/URL-to-Video/CreateVideo) endpoint.

## Consumption

Each time you call the AI Scripts API, it will consume 0.2 API Credit.