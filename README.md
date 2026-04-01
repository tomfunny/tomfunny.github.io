# Tom's Blog

我的个人博客，基于 [Astro](https://astro.build) 构建，部署在 [Vercel](https://vercel.com)。

## 特性

- 🎨 简约干净的设计风格
- 🌓 胶囊形状主题切换（浅色/深色）
- 📱 响应式设计，适配移动端
- 🏷️ 标签和分类系统
- 🔍 SEO 优化
- 🖼️ 图片优化支持（Vercel Image Optimization）
- 📄 自动生成站点地图

## 技术栈

- **Astro 5** - 现代化的静态站点生成器
- **TypeScript** - 类型安全
- **CSS 变量** - 主题系统
- **Vercel** - 托管和 CDN

## 本地开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 预览构建结果
npm run preview
```

## 部署到 Vercel

### 方式 1：Vercel CLI（推荐）

```bash
# 安装 Vercel CLI
npm i -g vercel

# 登录
vercel login

# 部署
vercel
```

### 方式 2：GitHub 自动部署

1. 在 Vercel 导入 GitHub 仓库
2. 每次 push 到 main 分支自动部署

### 方式 3：GitHub Actions

配置 `.github/workflows/deploy-vercel.yml`，需要设置以下 Secrets：
- `VERCEL_TOKEN` - Vercel API Token
- `VERCEL_ORG_ID` - 组织 ID
- `VERCEL_PROJECT_ID` - 项目 ID

## 项目结构

```
├── src/
│   ├── components/      # 可复用组件
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   └── Search.astro
│   ├── layouts/         # 布局组件
│   │   ├── Layout.astro
│   │   └── BlogPost.astro
│   ├── content/         # 博客内容
│   │   ├── blog/        # 博客文章
│   │   └── config.ts    # Content Collections 配置
│   ├── pages/           # 页面
│   │   ├── index.astro  # 首页
│   │   ├── blog/        # 博客列表和详情页
│   │   ├── tags/        # 标签页
│   │   ├── categories/  # 分类页
│   │   └── about.astro  # 关于页
│   └── styles/          # 全局样式
│       └── global.css
├── public/              # 静态资源
│   └── images/          # 图片文件
├── vercel.json          # Vercel 配置
└── astro.config.mjs     # Astro 配置
```

## 撰写新文章

在 `src/content/blog/` 目录下创建新的 Markdown 文件：

```markdown
---
title: '文章标题'
description: '文章描述'
pubDate: 2026-04-01
tags: ['标签 1', '标签 2']
categories: ['分类']
draft: false
---

文章内容...
```

## 图片使用

### 方式 1：静态图片（推荐）

将图片放在 `public/images/` 目录：

```astro
<img src="/images/photo.jpg" alt="描述" />
```

### 方式 2：优化的图片（需要 @astrojs/image）

```astro
---
import { Image } from 'astro:assets';
import photo from '../images/photo.jpg';
---

<Image src={photo} alt="描述" width={800} height={600} />
```

## Vercel 图片优化

Vercel 自动优化 `/public/images/` 下的图片：
- 自动转换为 WebP/AVIF
- 响应式尺寸
- CDN 缓存

## 待办事项

- [ ] 添加搜索功能
- [ ] 添加 RSS Feed
- [ ] 添加阅读进度条
- [ ] 集成评论系统（Giscus）

## License

MIT
