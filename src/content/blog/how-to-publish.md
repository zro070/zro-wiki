---
title: "如何在这个博客发布文章"
description: "记录从写文章、本地预览、推送到 GitHub、再到 Vercel 自动部署的完整流程。"
pubDate: "Nov 14 2026"
categories:
  - 技术
---

这篇文章记录本博客的发布流程，方便以后查阅。

## 一、写文章

在 `src/content/blog/` 目录下新建一个 `.md` 文件，例如 `my-first-post.md`，文件顶部是元信息（frontmatter），下面是正文：

```markdown
---
title: "我的第一篇文章"
description: "这是一段文章简介，会显示在列表卡片上"
pubDate: "Nov 14 2026"
categories:
  - 技术
---

正文写在这里，支持 Markdown 语法。
```

### frontmatter 字段说明

| 字段 | 必填 | 说明 |
| --- | --- | --- |
| title | 是 | 文章标题 |
| description | 是 | 简介，显示在列表卡片上 |
| pubDate | 是 | 发布日期，格式 Nov 14 2026 |
| categories | 否 | 分类：技术 / 日常 / 分享 |
| image | 否 | 封面图，放 public/image/，写 /image/xxx.webp |
| badge | 否 | 填 Pin 表示置顶 |
| draft | 否 | 填 true 表示草稿，不发布 |

分类决定文章出现在哪个 tab，不写分类则只出现在「时间轴」里。

## 二、本地预览

```sh
cd D:/ghub/Frosti
pnpm run dev
```

浏览器打开 `http://localhost:4321` 检查效果。

## 三、上传（提交 + 推送）

```sh
cd D:/ghub/Frosti
git add -A
git commit -m "新文章：我的第一篇文章"
git push
```

> 推送需要代理（Clash）开着。

## 四、自动上线

推送到 GitHub 后，Vercel 会自动重新部署，等 1~2 分钟网站就更新了。

## 完整流程

```text
写 .md 文件 → pnpm run dev 本地预览 → git add/commit/push → Vercel 自动部署上线
```
