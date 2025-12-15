# JoggAI API 文档

JoggAI 视频 AI 平台 API 文档

---

## 基本命令

```bash
# 安装 Mintlify
npm i -g mintlify

# 本地预览
mintlify dev

# 访问: http://localhost:3000
```

---

## 项目结构

```
/docs
├── README.md
├── mint.json
│
├── home/                          # 首页文件
│   └── WelcometoJoggAI.mdx        (包含 Key Features 和视频展示)
│
├── api-reference/
│   ├── v1/                        # API v1（维护中）
│   │   ├── QuickStart/
│   │   ├── API Documentation/     (15个)
│   │   ├── Video/Avatar/Voice/    (45+ endpoints)
│   │   └── openapi.json
│   │
│   └── v2/                        # API v2（推荐）⭐
│       ├── QuickStart/            (4个)
│       │   ├── GettingStarted.mdx
│       │   ├── Pricing.mdx
│       │   ├── ErrorHandling.mdx
│       │   └── RateLimits.mdx
│       ├── API Documentation/     (12个教程)
│       ├── Video/                 (7个)
│       ├── Avatar/                (5个)
│       ├── Voice/                 (2个)
│       ├── Asset/                 (5个)
│       ├── Template/              (3个)
│       ├── Product/               (2个)
│       ├── User/                  (2个)
│       ├── Webhook/               (5个)
│       └── openapi-v2.yaml
│
├── images/                        # 文档图片 (23个)
└── logo/                          # 品牌资源 (4个)
```

---

## 文件命名规范

### 文档文件
```
✅ 推荐: CreateAvatarVideo.mdx, GetUserInfo.mdx
❌ 避免: create-avatar-video.mdx, 创建视频.mdx
```

### 特殊文件
```
README.md
mint.json
openapi-v2.yaml
```

### 图片文件
```
✅ 推荐: api-key-guide.png, img_1.png
❌ 避免: IMG_20231201.png, 截图1.png
```

---

## 文件组织原则

### 1. 按功能模块分类
```
api-reference/v2/
├── Video/          # 视频相关
├── Avatar/         # 头像相关
└── Voice/          # 语音相关
```

### 2. 教程与 API 分离
```
api-reference/v2/
├── API Documentation/  # 教程文档
└── Video/              # API Endpoints
```

### 3. 资源集中管理
```
/images/    # 所有图片
/logo/      # 所有Logo
```

---

## 文档格式

### Front Matter（必填）

```markdown
---
title: "文档标题"
description: "简短描述（不超过160字符）"
---
```

### 标题层级

```markdown
# H1 - 页面主标题
## H2 - 主要章节
### H3 - 子章节
#### H4 - 细分内容
```

---

## 图片管理

### 存放位置
```
/images/    # 文档图片
/logo/      # Logo/品牌
```

### 引用方式
```markdown
![描述](/images/your-image.png)
```

---

## 导航配置

### mint.json 结构

```json
{
  "navigation": [
    {
      "group": "组名",
      "pages": [
        "path/to/page"
      ]
    }
  ]
}
```

### 路径规范

```json
✅ "api-reference/v2/Video/CreateVideo"
❌ "api-reference/v2/Video/CreateVideo.mdx"
❌ "/api-reference/v2/Video/CreateVideo"
```

---

## Git 提交规范

```bash
# 格式: <type>(<scope>): <subject>

# type:
- docs: 文档更新
- feat: 新功能
- fix: 修复错误
- refactor: 重构

# 示例:
git commit -m "docs(v2): 添加视频翻译教程"
git commit -m "fix(v1): 修复链接错误"
git commit -m "feat(v2): 新增 API 文档"
```

---

## 文档发布检查

- [ ] Front Matter 完整
- [ ] 标题层级正确
- [ ] 链接使用相对路径
- [ ] 图片路径规范
- [ ] mint.json 已更新
- [ ] 本地预览正常

---

## 版本管理

| 版本 | 状态 | 维护策略 |
|------|------|----------|
| V1 | 维护中 | 兼容性支持 |
| V2 | 主版本 | 功能更新 |

---

**在线文档:** [https://docs.jogg.ai](https://docs.jogg.ai)
