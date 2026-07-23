# Fangmo's Blog

个人博客，使用 Hexo、Fluid 和 GitHub Pages 构建。

## 首次安装

```powershell
cd C:\Users\18149\Documents\fangmo-blog
npm.cmd install --cache .npm-cache
```

## 创建文章

文章文件名决定 URL，建议使用小写英文和短横线：

```powershell
npm.cmd run new -- "classic-3d-reconstruction"
```

随后编辑 `source/_posts/classic-3d-reconstruction.md`，例如：

```yaml
---
title: 经典三维重建方法梳理
date: 2026-07-21 20:00:00
categories:
  - 论文阅读
tags:
  - 3D Reconstruction
  - Computer Vision
---
```

`<!-- more -->` 之前的内容会显示为首页摘要。

## 添加图片

把图片放到 `source/images/classic-3d-reconstruction/pipeline.png`，在 Markdown 中引用：

```markdown
![三维重建流程](/images/classic-3d-reconstruction/pipeline.png)
```

文件名大小写必须完全一致。

## 本地预览

```powershell
npm.cmd run clean
npm.cmd run build
npm.cmd run server
```

打开 http://localhost:4000，结束预览时按 `Ctrl+C`。

## 使用草稿

```powershell
npm.cmd run new:draft -- "oasis-paper-reading"
npm.cmd run drafts
```

完成后转为正式文章：

```powershell
npx.cmd hexo publish "oasis-paper-reading"
```

## 第一次发布到 GitHub

1. 网站地址已配置为 `https://sbsjkm.github.io`。
2. GitHub Pages 仓库为 `SBSJKM.github.io`。
3. 在仓库 `Settings > Pages` 中将 Source 设为 `GitHub Actions`。
4. 配置 Git 身份并推送：

```powershell
git config user.name "SBSJKM"
git config user.email "sbsjkm13@sjtu.edu.cn"
git init
git add .
git commit -m "Initialize personal blog"
git branch -M main
git remote add origin https://github.com/SBSJKM/SBSJKM.github.io.git
git push -u origin main
```

## 以后上传文章

写完并本地预览后执行：

```powershell
git add .
git commit -m "Add classic 3D reconstruction article"
git push
```

GitHub Actions 会自动构建并发布。可在仓库的 `Actions` 页面查看状态。
