---
title: 如何用 Hugo 构建 GitHub Pages
date: 2022-05-28
tags: ["分享"]
description: "开启你的创作之旅"
showDate: true/false    # to enable/disable showing dates
math: true              # to enable showing equations (katex)
chordsheet: true        # to add chordsheet styelsheet
---

Hugo + GitHub Pages = "我的世界"

不知道你有没有玩过《[我的世界](https://www.minecraft.net/zh-hans)》这款游戏 —— 基于有限的规则，创造无限的世界。

## 安装依赖
推荐使用 brew 进行安装
```shell
brew install hugo
```
当然，[官网](https://gohugo.io/getting-started/installing/)也有其他安装方式。

## 创建你的 GitHub Pages
首先，你需要一个 GihHub 账号，这没什么好说的，接着，按照以下步骤，创建你的 GitHub Pages：
1. 新建仓库：仓库名格式须符合正则表达式 `/**.github.io/`，切记勾选 `Add a README file`。
2. 设置主题：点击 Settings 进入设置页面，点击 Pages，进入 GitHub Pages，选择 master 分支，点击按钮 `Change theme`，选择一个临时主题（这很重要），如果你有自己的域名，也可以在自定义域名处填写自己的域名，点击`Save`。

看到 `Your site is published at https://***` 了吗？稍等片刻后，你可以就可以看到自己的 GitHub Pages 了。
## 用 Hugo "重构"你的 GitHub Pages
作为一个有追求的人，官方简单的主题显然不能满足我们的需求，作为一个不重复造轮子的懒人（智者），推荐使用 Hugo，遵循以下步骤：
1. 使用
```shell
hugo new site myBlog # myBlog 是你的目录名。
```
命令新建一个 Hugo 网站。
2. 进入目录，创建 `theme`目录。
```shell
cd myBlog && mkdir -p themes
```
3. 进入 themes 目录，克隆 Hugo Themes。
```shell
cd thems && git clone git@github.com:humrochagf/colordrop.git themes/colordrop # git@github.com:humrochagf/colordrop.git themes/colordrop 是所选主题的地址
```
4.编辑配置文件 `config.yml`,配置方式参考主题页面。
5. 本地预览，实时编辑。
```shell
hugo server -D 
```
6. 打包。
```shell
hugo # 默认将静态站点保存到 "public" 目录
```
7. 将 `public` 目录下的内容拷贝到你的 `**.github.io` 仓库下，提交观赏效果。


新增一篇文章的常用命令一般是 
```shell
hugo new posts/<filename>.md
```
但也有不同，比如，我就是通过
```shell
hugo new post/<filename>.md.
```
来新增的。
    
### 参考文章
- [如何利用 GitHub Pages 和 Hugo 轻松搭建个人博客？](https://zhuanlan.zhihu.com/p/57361697)
- [Hugo博客部署到GitHub无法显示CSS、JS踩坑](https://blog.csdn.net/qq_45050480/article/details/105325541)