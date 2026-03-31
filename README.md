# Tom's Blog

我的个人博客，基于 [Astro](https://astro.build) 构建。

## 特性

- 🎨 简约干净的设计风格
- 🌓 自动深色模式（跟随系统）
- 📱 响应式设计，适配移动端
- 🏷️ 标签和分类系统
- 🔍 SEO 优化
- 💬 Giscus 评论支持
- 📄 自动生成站点地图

## 技术栈

- **Astro 5** - 现代化的静态站点生成器
- **TypeScript** - 类型安全
- **CSS 变量** - 主题系统

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

## 项目结构

```
├── src/
│   ├── components/      # 可复用组件
│   │   ├── Header.astro
│   │   └── Footer.astro
│   ├── layouts/         # 布局组件
│   │   ├── Layout.astro
│   │   └── BlogPost.astro
│   ├── content/         # 博客内容
│   │   ├── blog/        # 博客文章
│   │   └── config.ts    # Content Collections 配置
│   ├── pages/           # 页面
│   │   ├── index.astro  # 首页
│   │   ├── blog/        # 博客列表和详情页
│   │   └── about.astro  # 关于页
│   └── styles/          # 全局样式
│       └── global.css
├── public/              # 静态资源
└── astro.config.mjs     # Astro 配置
```

## 撰写新文章

在 `src/content/blog/` 目录下创建新的 Markdown 文件：

```markdown
---
title: '文章标题'
description: '文章描述'
pubDate: 2026-03-31
tags: ['标签 1', '标签 2']
categories: ['分类']
draft: false
---

文章内容...
```

## 部署

博客部署在 GitHub Pages：

1. 推送到 GitHub
2. 在仓库设置中启用 GitHub Pages
3. 选择 `GitHub Actions` 作为来源（或 `gh-pages` 分支）

## 待办事项

- [ ] 添加搜索功能
- [ ] 添加 RSS Feed
- [ ] 添加阅读进度条
- [ ] 优化移动端导航

## License

MIT
