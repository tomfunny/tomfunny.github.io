# tomfunny.github.io 完善计划

创建时间：2026-03-31 22:35
更新时间：2026-03-31 23:05

## 目标

打造一个功能完整、设计精美的个人博客系统。

## 已完成功能 ✅

### 核心功能
- ✅ Astro 5 基础框架
- ✅ 响应式布局
- ✅ 博客文章系统（Content Collections）
- ✅ 标签系统 + 筛选
- ✅ 分类系统 + 筛选

### UI 组件
- ✅ 全局导航栏（所有页面）
- ✅ 页脚组件
- ✅ Layout 布局系统
- ✅ 文章卡片设计

### 新增功能（本次更新）
- ✅ **全局搜索** - 支持标题、内容、标签搜索（Cmd/Ctrl + K）
- ✅ **阅读进度条** - 文章页面顶部显示阅读进度
- ✅ **主题切换按钮** - 所有页面右上角可见，支持浅色/深色手动切换
- ✅ **主题持久化** - localStorage 保存用户偏好

### 页面列表
- ✅ 首页 `/`
- ✅ 博客列表 `/blog`
- ✅ 文章详情 `/blog/[slug]`
- ✅ 标签云 `/tags`
- ✅ 标签归档 `/tags/[tag]`
- ✅ 分类列表 `/categories`
- ✅ 分类归档 `/categories/[category]`
- ✅ 关于页 `/about`

## 待办事项

- [ ] RSS Feed
- [ ] Giscus 评论配置（需填写 repo ID）
- [ ] 更多示例文章
- [ ] GitHub Pages 部署配置

## 快捷操作

| 功能 | 快捷键 |
|------|--------|
| 打开搜索 | `Cmd/Ctrl + K` |
| 关闭搜索 | `Esc` |
| 切换主题 | 点击右上角太阳/月亮图标 |

## 运行命令

```bash
cd /Users/taoge/my_project/daily/tomfunny.github.io
npm install
npm run dev
```

## 设计决策

- 风格：简约干净（类似 Medium）✅
- 主色调：蓝色系 ✅
- 主题切换：支持手动切换 + 自动跟随系统 ✅
- 评论功能：Giscus（需配置）✅
