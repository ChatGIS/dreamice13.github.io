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
vexo主题中有一些作者信息、图片，为了改成自己的信息并同步github，需要fork对应的主题。
## 1、fork主题
fork主题
## 2、下载主题
```bash
git clone git@github.com:dreamice13/hexo-theme-vexo.git themes/vexo
```
## 3、修改提交
在themes/vexo文件夹下进行git提交、上传

# 样式问题
## 1、部署样式错乱
删除public文件夹，使用命令`hexo g`重新生成。
> 使用`hexo clean`命令清除缓存文件 (db.json) 和已生成的静态文件 (public)。`hexo c`不是其简写形式，不能使用。

