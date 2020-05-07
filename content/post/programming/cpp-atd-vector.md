---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "C++的Vector实现"
subtitle: ""
summary: ""
authors: [admin]
tags: [c++]
categories: [Programming]
date: 2019-11-03T22:48:08+09:00
lastmod: 2019-11-03T22:48:08+09:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

本文介绍如何实现基本的vector container

### 基本方法

- Big five
- resize, reserve
- operator[]
- size, empty, clear
- back, push_back, pop_back
- iterator

### 基本数据存储

- data: 原生array[]
- size
- capacity