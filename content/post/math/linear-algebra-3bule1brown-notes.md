---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Linear Algebra 3bule1brown Notes"
subtitle: ""
summary: ""
authors: [admin]
tags: [Linear Algebra]
categories: [Math]
date: 2020-04-17T09:45:32+09:00
lastmod: 2020-04-17T09:45:32+09:00
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

笔记模版都参照“康奈尔笔记法”

这个模板是数学文章的Typora模板，由于数学文章的特殊性（符号比较多），这里使用toc+title的方式来组织笔记

toc对应康奈尔笔记的左边栏(问题/线索 )，title(##或者###)对应右边栏(笔记/要点)，总结在最后

一个#号代表问题/线索，其余灵活组织，代表笔记/要点内容



这是一系列[视频](https://www.3blue1brown.com/essence-of-linear-algebra-page)的笔记

[toc]

# 线索1: 第二步在这里写出对第一步笔记的问题或者线索，使用#

## 第一步先在这里记录笔记/要点，使用##或者###

- 使用符号
- 使用缩写
- 列出要点
- Vector: 三种观点：箭头（物理），数字串（CS）=》抽象符号（Math）
- Focus on从原点开始的箭头，用[a, b]表示向量，用(a,b)表示点
- Vector Add/mul



- [a, b]=》实际上是scale 单位向量 i, j
- 选择不同的i，j=》加上不同的scalar a，b，就是linear combination
- span：i，j的所有set的集合
- 观察单个向量：想象成箭头；观察向量集合：想象成点集
- 每个向量都能表示不同的点：linear independent；若i，j共线，则造成不同的[a,b]表示相同的点，则linear dependent



- input—linear transformation-》output
- Linear Transformation(Function)：保证原点不变，并且保证grid line parallel and evenly spaced
- Linear Transformation表示的是i，j的变化，就可以通过matrix的两组值来想象整个坐标空间的变化
- $\begin{pmatrix}a&c\\b&d\end{pmatrix}$中ab是i的x,y坐标变化，cd是j的x,y坐标变化
- $\begin{pmatrix}a&c\\b&d\end{pmatrix}$$\begin{bmatrix}X\\Y\end{bmatrix}$左乘向量
- 这样的好处是可以通过想象移动i，j来构成$\begin{pmatrix}a&c\\b&d\end{pmatrix}$的各个值



- composition：左乘矩阵
- 想象的时候还是拆分成i，j，在通过左乘操作移动i，j

# 线索2

# 线索3

# 总结：第三步在这里总结