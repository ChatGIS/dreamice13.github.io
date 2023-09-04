<!--
 * @Author: Dreamice dreamice13@foxmail.com
 * @Date: 2022-12-19 20:26:24
 * @LastEditors: Dreamice dreamice13@foxmail.com
 * @LastEditTime: 2023-09-04 23:44:21
 * @FilePath: \dreamice13.github.io\source\_posts\hexo标签及分类.md
 * @Description: 
-->
---
title: Hexo设置标签及分类
date: 2022-12-19 20:26:24
tags: [hexo]
categories: Hexo
---

以下方式仅限于vexo主题下使用；

# 设置标签
标签设置有两种方式；

1、数组方式
```
tags: [标签1, 标签2]
```
相对方法2，这种方式写起来比较简单、直观；

2、短横线方式
```
tags: 
- 标签1 
- 标签2
```

> 注意：该方式-后要有空格；

# 设置分类
分类设置方式如下：
```
categories: 分类名
```
> 注意：每篇文章必须包括categories，且分类名必须不为空；也就是说每篇文章必须分类，否则点击Series会报错。当然，这个仅实验于vexo主题。