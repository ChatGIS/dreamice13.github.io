---
title: Hexo设置主题
date: 2022-12-10 19:54:09
tags: [hexo]
categories: Hexo
---

# 基础使用
## 1. 选择主题
截止本文编写时，hexo官网提供了372个主题，用户可以根据自己喜好选择主题；
个人当前选择主题是yanm1ng/hexo-theme-vexo；

## 2. 下载主题
通过命令下载主题，
```bash
git clone git@github.com:dreamice13/hexo-theme-vexo.git themes/vexo
```
## 3. 设置主题
在_config.yml文件中，找到theme选项，将选项设置为：`theme: vexo`
设置之后，即可使用该主题的样式；

# 进阶使用
## 1、部署样式错乱
删除public文件夹，使用命令`hexo g`重新生成。

