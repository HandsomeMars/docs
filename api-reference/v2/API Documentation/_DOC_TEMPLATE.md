# API Documentation Template

此模板定义了所有 API 文档的统一格式结构。

## 📐 统一文档结构

### 1. **Introduction** (简介)

```markdown
## Introduction

[1-2句话说明接口用途]

### Key Features

<CardGroup cols={2}>
  <Card title="特性1" icon="icon-name">
    特性描述
  </Card>
  <Card title="特性2" icon="icon-name">
    特性描述
  </Card>
  <Card title="特性3" icon="icon-name">
    特性描述
  </Card>
  <Card title="特性4" icon="icon-name">
    特性描述
  </Card>
</CardGroup>

### Workflow Overview

[接口调用流程说明]

<Steps>
  <Step title="步骤1">
    步骤说明
  </Step>
  
  <Step title="步骤2">
    步骤说明
  </Step>
  
  <Step title="步骤3">
    步骤说明
  </Step>
</Steps>

```mermaid
sequenceDiagram
    [时序图展示完整流程]
```

<Info>
重要提示或说明
</Info>
```

---

### 2. **Quick Start** (快速开始)

```markdown
## Quick Start

### Related API Endpoints

| Endpoint | Purpose | Documentation |
|----------|---------|---------------|
| `GET /endpoint1` | 用途说明 | [API Reference](/link) |
| `POST /endpoint2` | 用途说明 | [API Reference](/link) |

### Key Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `param1` | string | ✅ | 参数说明 |
| `param2` | integer | ❌ | 参数说明 |

<Warning>
关键的参数使用警告
</Warning>
```

---

### 3. **Code Examples** (代码示例)

```markdown
## Code Examples

### Scenario 1: [场景名称]

[场景说明]

**[步骤说明]:**

```bash
curl --request POST \
  --url 'https://api.jogg.ai/open/v2/endpoint' \
  --header 'x-api-key: YOUR_API_KEY' \
  --header 'Content-Type: application/json' \
  --data '{
    "param1": "value1",
    "param2": "value2"
  }'
```

**Response:**

```json
{
  "code": 0,
  "msg": "Success",
  "data": {
    "id": "123456"
  }
}
```

<Check>
成功提示
</Check>

---

### Scenario 2: [场景名称]

[重复场景1的结构，展示不同使用场景]

---

### Scenario 3: [场景名称]

[更多场景示例...]

<Tip>
实用技巧
</Tip>
```

---

### 4. **Use Case Examples** (使用场景)

```markdown
## Use Case Examples

<AccordionGroup>
  <Accordion title="使用场景1">
    场景详细说明:
    - 要点1
    - 要点2
    - 要点3
  </Accordion>
  
  <Accordion title="使用场景2">
    场景详细说明...
  </Accordion>
</AccordionGroup>
```

---

### 5. **Related Documentation** (相关文档)

```markdown
## Related Documentation

<CardGroup cols={2}>
  <Card
    title="相关API 1"
    icon="icon-name"
    href="/link"
  >
    简要说明
  </Card>
  
  <Card
    title="相关API 2"
    icon="icon-name"
    href="/link"
  >
    简要说明
  </Card>
</CardGroup>
```

---

## ✅ 必须遵循的原则

### 第一性原理
- **充分性**: 包含用户理解和使用API所需的所有关键信息
- **必要性**: 移除重复、冗余或不相关的内容
- **简洁性**: 用最少的文字表达最清晰的意思

### 统一性
- **结构统一**: 所有文档遵循相同的4部分结构
- **格式统一**: 使用相同的Markdown组件和样式
- **术语统一**: API端点、参数名保持一致

### 实用性
- **场景驱动**: 每个示例都对应真实使用场景
- **完整示例**: 包含完整的请求和响应
- **错误处理**: 展示成功和失败的情况

---

## 📝 组件使用指南

### 信息提示组件

```markdown
<Info>普通信息提示</Info>
<Tip>实用技巧提示</Tip>
<Warning>警告信息</Warning>
<Check>成功/完成提示</Check>
```

### 卡片组

```markdown
<CardGroup cols={2}>  <!-- 或 cols={3}, cols={4} -->
  <Card title="标题" icon="图标名">
    内容
  </Card>
</CardGroup>
```

### 步骤

```markdown
<Steps>
  <Step title="步骤标题">
    步骤内容
  </Step>
</Steps>
```

### 折叠面板

```markdown
<AccordionGroup>
  <Accordion title="标题">
    内容
  </Accordion>
</AccordionGroup>
```

---

## 🎯 文档分组策略

当多个文档有相似性但场景不同时，应该：

### 创建文档组
- **主文档**: 概述性文档，包含通用流程
- **场景文档**: 针对特定场景的详细文档

### 示例：Avatar Videos 文档组

```
CreateAvatarVideos.mdx          # 主文档 - 通用流程
├── AvatarVideosWithPhotoAvatar.mdx   # 场景1 - 使用照片Avatar
├── AvatarVideosTransparentBackground.mdx  # 场景2 - 透明背景
└── AvatarVideosWithAudioSource.mdx   # 场景3 - 自定义音频
```

### 示例：Upload Media 文档组

```
UploadMedia.mdx                 # 主文档 - 上传概述
├── UploadMediaImages.mdx       # 场景1 - 上传图片
├── UploadMediaVideos.mdx       # 场景2 - 上传视频
└── UploadMediaAudio.mdx        # 场景3 - 上传音频
```

---

## 📊 质量检查清单

创建/更新文档后，检查：

- [ ] 包含所有4个主要部分
- [ ] Introduction 部分有清晰的工作流程图
- [ ] Quick Start 列出了所有相关API端点
- [ ] Code Examples 至少包含3个不同场景
- [ ] 每个代码示例都有完整的请求和响应
- [ ] 使用了适当的信息提示组件
- [ ] 链接到相关的API参考文档
- [ ] 没有重复或冗余内容
- [ ] 代码示例使用 v2 API 端点
- [ ] 所有URL、参数名正确

---

## 🔗 内部链接规范

### API Reference 链接
```markdown
[API Reference](/api-reference/v2/Category/EndpointName)
```

### Tutorial 链接
```markdown
[Guide](/api-reference/v2/API Documentation/GuideName)
```

### 示例
```markdown
[Get Avatars API](/api-reference/v2/Avatar/GetPublicAvatars)
[Create Avatar Videos](/api-reference/v2/API Documentation/CreateAvatarVideos)
[Webhook Integration](/api-reference/v2/API Documentation/WebhookIntegration)
```

---

## 🎨 常用图标

| 分类 | 图标名 |
|------|--------|
| **通用** | check, info-circle, exclamation-triangle, bolt, star |
| **用户/Avatar** | user, users, user-circle, face-smile |
| **媒体** | video, image, microphone, music, file-video |
| **操作** | upload, download, play, pause, stop |
| **网络** | link, webhook, globe, cloud |
| **功能** | wand-magic-sparkles, sparkles, sliders, palette, language |
| **商业** | shopping-bag, box, chart-line, gauge |

完整图标列表：https://fontawesome.com/icons

---

## 💡 最佳实践

1. **先理解后编写**: 先理解API的核心功能和工作流程
2. **用户视角**: 从用户需求出发，而不是技术实现
3. **逐步深入**: 从简单示例到复杂场景
4. **实战导向**: 每个示例都应该可以直接运行
5. **持续优化**: 根据用户反馈不断改进

---

## 📚 参考已完成的文档

以下文档已按照统一格式更新，可作为参考：

1. `CreateAvatarVideos.mdx` - 完整示例
2. `URLtoVideo.mdx` - 多步骤流程
3. `AIScripts.mdx` - 异步任务处理
4. `GetResult.mdx` - 状态检查和轮询

参考这些文档的结构和风格来更新其他文档。




