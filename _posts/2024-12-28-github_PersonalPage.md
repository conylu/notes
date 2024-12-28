---
title: How to Generate TOC
author: Tao He
date: 2021-08-10
category: Jekyll
layout: post
---

```yaml
toc:
    enabled: true
```

Why this repo
-------------



# 20241228_01_github个人主页搭建_带选项卡

## 如何创建一个极简版的 github 个人主页

- 新建 repo, repo 名称为 [您的GitHub用户名].github.io
- 在 repo 中新建 readme.md 文件
- 在 readme.md 文件中输入以下内容

  ```markdown
  # Hello World
  ```

- 访问 https://[您的GitHub用户名].github.io 即可看到效果

## 如何根据其他人的模板创建自己的 github 个人主页

- 在 [Jekyll Themes](https://www.bing.com/search?q=jekyll+theme&form=ANNTH1&refig=E2119464A82D4812AA25ADA3F678D8BC&pc=DCTS&pqlth=0&assgl=12&sgcn=jekyll+theme&qs=HS&smvpcn=0&swbcn=10&sc=10-0&sp=1&ghc=0&cvid=E2119464A82D4812AA25ADA3F678D8BC&clckatsg=1&hsmssg=0) 找模板; 我使用的是 [academicpages](https://github.com/academicpages/academicpages.github.io), 其预览效果为 [academicpages.github.io](https://academicpages.github.io/)
- fork 模板 repo, github 会询问 repo 的名称, 修改为 [您的GitHub用户名].github.io
- 将 fork 的 repo clone 到本地(使用 github desktop)
- 修改 _config.yml 文件, 将 url 修改为 https://[您的GitHub用户名].github.io, 将 baseurl 修改为 ""
  
  > - url: 表示网站的根地址
  > - baseurl: 表示网站的子目录地址

  这样做的目的是, 使得网站的子网页链接的根地址为自己的 github 个人主页, 否则会链接到[你 fork 的模板 repo 的主人]的 github 个人主页
- push 到远程仓库
- check: 按照 step 1-4 设置, 过几分钟后会看到 5 的位置出现你的个人网站网址; 有时在手机浏览器访问该网址能比电脑浏览器更快看到效果
  ![alt text](image-26.png)


## 如何在 github 个人主页的基础上, 设置一个子目录, 用于展示自己的项目

- 目的: username.github.io 根据 [academicpages 模板](https://academicpages.github.io/) 放个人主页, username.github.io/notes 根据 [GitBook Style](https://sighingnow.github.io/jekyll-gitbook) 放 notes
- 步骤为:
  - 新建一个 repo, repo 名称为 notes
  - notes repo 中 fork [GitBook Style](https://sighingnow.github.io/jekyll-gitbook) 模板
  - 用 Github Desktop 将 notes repo clone 到本地, 修改 _config.yml 文件, 将 url 修改为 https://[您的GitHub用户名].github.io/notes, 将 baseurl 修改为 "/notes", push 到远程仓库
  - 将 notes repo 设置为 github pages, 选择 source 为 master branch, 点击 save
    ![alt text](image-27.png)
- 思想:
  - 看最终网址, 似乎 notes 是 username.github.io 的子目录/一个选项卡, 它具有下面的特征: 1. 在 username.github.io 的主页上点击 notes 选项卡, 就会跳转到 username.github.io/notes; 2. 在本地的 username.github.io repo 中有一个 notes 文件夹, 里面存放了 notes repo 的内容
  - 但实际上, notes 是 username.github.io 的一个独立的 repo, 通过 baseurl 的设置, 使得 notes repo 的网址为 username.github.io/notes
  - 也就是说, 1. github 中的每一个 project 都可以设置为 github pages, 它的网址自动成为 username.github.io/project_name; 2. username.github.io/xxx 形式的连接中, xxx 可以是一个独立的 repo, 也可以是一个 username.github.io repo 中的子目录

## ref: 本文参考了以下链接

- [【保姆级教程】手把手教你用github制作学术个人主页（学者必备）](https://blog.csdn.net/qd1813100174/article/details/128604858)
- GPT


[1]: https://github.com/allejo/jekyll-toc
