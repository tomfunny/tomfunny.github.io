# Vercel 部署指南

## 🚀 快速部署（3 步完成）

### 步骤 1：在 Vercel 导入项目

1. 访问 https://vercel.com/new
2. 点击 **Import Git Repository**
3. 选择 `tomfunny/tomfunny.github.io` 仓库
4. 点击 **Import**

### 步骤 2：配置项目

框架会自动检测为 Astro，无需修改配置。

点击 **Deploy** 开始部署。

### 步骤 3：完成

部署完成后，你会获得：
- **生产环境 URL**: `https://tomfunny-github-io.vercel.app`
- **预览环境**: 每次 PR 自动生成预览

---

## 🔧 自定义域名（可选）

1. Vercel 项目设置 → **Domains**
2. 添加你的域名（如 `blog.tomfunny.com`）
3. 按提示配置 DNS

---

## 📸 图片优化配置

### 1. 更新 `astro.config.mjs`

```javascript
import { defineConfig } from 'astro/config';
import sitemap from '@astrojs/sitemap';

export default defineConfig({
  site: 'https://tomfunny.github.io',
  integrations: [sitemap()],
  image: {
    service: {
      entrypoint: 'astro/assets/services/sharp',
    },
  },
});
```

### 2. 安装图片优化依赖

```bash
npm install sharp
```

### 3. 在文章中使用图片

```markdown
---
title: '我的文章'
image: '/images/cover.jpg'
---

![封面图](/images/cover.jpg)
```

Vercel 会自动：
- 转换为 WebP 格式
- 生成多种尺寸
- CDN 缓存加速

---

## 📤 图片上传功能（高级）

如果需要用户上传图片，可以使用 Vercel Serverless Functions：

### 创建 API 路由

`src/pages/api/upload.ts`:

```typescript
import type { APIRoute } from 'astro';

export const POST: APIRoute = async ({ request }) => {
  // 处理图片上传
  const formData = await request.formData();
  const file = formData.get('image') as File;
  
  // 保存到云存储（如 Vercel Blob、AWS S3）
  // ...
  
  return new Response(JSON.stringify({ success: true }));
};
```

### 推荐的云存储

| 服务 | 免费额度 | 说明 |
|------|----------|------|
| **Vercel Blob** | 1GB | 最简单，与 Vercel 集成 |
| **Cloudinary** | 25GB | 专业图片服务 |
| **AWS S3** | 5GB | 通用对象存储 |

---

## 🎯 Vercel 免费额度

| 资源 | 免费额度 |
|------|----------|
| 带宽 | 100GB/月 |
| 构建时间 | 6000 分钟/月 |
| Serverless 函数 | 100GB-小时/月 |
| 图片优化 | 1000 次/月 |
| 域名 | 无限 |

对于个人博客完全够用！

---

## ✅ 部署检查清单

- [ ] 已创建 Vercel 账号
- [ ] 已导入 GitHub 仓库
- [ ] 已配置自定义域名（可选）
- [ ] 已测试图片加载
- [ ] 已验证 HTTPS

---

## 🔗 相关链接

- [Vercel 文档](https://vercel.com/docs)
- [Astro + Vercel](https://docs.astro.build/en/guides/deploy/vercel/)
- [Vercel 图片优化](https://vercel.com/docs/image-optimization)
