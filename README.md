# Pluck's Blog

基于 **Astro** 的个人静态博客，使用 Firefly/Fuwari 主题体系进行定制，通过 GitHub Actions 自动构建并发布到 GitHub Pages。

- 在线访问：<https://pluck9527.github.io/firefly-blog/>
- 源码仓库：<https://github.com/Pluck9527/firefly-blog>
- 默认语言：简体中文
- Node.js：22 或更高版本
- 包管理器：pnpm 9 或更高版本

## 当前状态

当前版本已经完成基础清理和初始化：

- 使用 `Pluck's Blog` 作为站点名称
- 配置独立头像、图标、简介和关于页面
- 移除主题演示账号、推广链接及示例文章
- 关闭音乐、视频背景、追番、相册、动态等暂未使用的模块
- 保留归档、分类、标签、搜索和 RSS 等博客核心功能
- 适配 GitHub Pages 的 `/firefly-blog/` 子路径

## 本地运行

```bash
git clone https://github.com/Pluck9527/firefly-blog.git
cd firefly-blog
pnpm install
pnpm dev
```

开发服务器默认运行在 <http://localhost:4321>。

## 常用命令

| 命令 | 作用 |
| --- | --- |
| `pnpm dev` | 启动本地开发服务器 |
| `pnpm build` | 构建生产版本到 `dist/` |
| `pnpm preview` | 预览生产构建 |
| `pnpm check` | 执行 Astro 类型与内容检查 |
| `pnpm format` | 使用 Biome 格式化源码 |
| `pnpm new-post <filename>` | 创建一篇新文章 |

## 写文章

文章保存在 `src/content/posts/`，推荐使用命令创建：

```bash
pnpm new-post my-first-post
```

基础 Frontmatter 示例：

```yaml
---
title: 文章标题
published: 2026-08-07
description: 文章简介
tags: [随笔]
category: 记录
draft: false
---
```

## 主要配置

站点配置集中在 `src/config/`：

| 文件 | 用途 |
| --- | --- |
| `siteConfig.ts` | 站名、描述、语言、页面开关 |
| `profileConfig.ts` | 头像、简介、个人链接 |
| `navBarConfig.ts` | 顶部导航栏 |
| `sidebarConfig.ts` | 侧边栏组件 |
| `backgroundWallpaper.ts` | 背景与横幅 |
| `commentConfig.ts` | 评论系统 |
| `licenseConfig.ts` | 文章许可协议 |

Astro 的站点地址与 GitHub Pages 子路径配置位于 `astro.config.mjs`。

## 部署

推送到 `master` 分支后，仓库中的 GitHub Actions 工作流会自动：

1. 安装依赖；
2. 执行检查与生产构建；
3. 上传 Pages 构建产物；
4. 发布到 <https://pluck9527.github.io/firefly-blog/>。

部署状态可在仓库的 [Actions](https://github.com/Pluck9527/firefly-blog/actions) 页面查看。

## 技术栈

- [Astro](https://astro.build/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Pagefind](https://pagefind.app/)
- [GitHub Pages](https://pages.github.com/)

## 来源与许可

本项目在 [CuteLeaf/Firefly](https://github.com/CuteLeaf/Firefly) 的基础上进行定制；Firefly 源自 [saicaca/fuwari](https://github.com/saicaca/fuwari)。感谢原项目作者和贡献者。

代码遵循仓库中的 [MIT License](./LICENSE)。使用、修改或分发时，请保留许可证及原始版权声明。
