---
title: 'Get the generated video'
description: 'How to get the generated video.'
---
```mermaid
graph TD;
    A[Upload File - /open/upload/sign] -->|Provides Media URL| B[Create Project - /open/render]
    B -->|Uses uploaded file| C[Get Project Info - /open/prj_info]
    C -->|Query synthesis status| D[Check Project Status]