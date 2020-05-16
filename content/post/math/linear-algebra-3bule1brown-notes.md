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

{{% toc %}}

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
- $\begin{pmatrix}a&c \\\ b&d\end{pmatrix}$中ab是i的x,y坐标变化，cd是j的x,y坐标变化
- $\begin{pmatrix}a&c \\\ b&d\end{pmatrix}$$\begin{bmatrix}X \\\ Y\end{bmatrix}$左乘向量
- 这样的好处是可以通过想象移动i，j来构成$\begin{pmatrix}a&c \\\ b&d\end{pmatrix}$的各个值



- composition：左乘矩阵
- 想象的时候还是拆分成i，j，在通过左乘操作移动i，j



- 2D扩展到3D，也是一样的规则



- determinant：
  - 当前linear transformation造成的面积（体积）变化
  - det=0表示面积变成了直线（降维）
  - 正负号表示朝向
- $det\begin{pmatrix}a&c  \\\  b&d\end{pmatrix} = a\times d-b\times c$
- 2D<->3D的变化也可以用matrix来变化，即使用3x2或者2x3来变化向量，这也和投影是一个道理



- 解线性方程组：$A\vec{x}= \vec{v}$

- 求解即求一个$\vec x$使其通过线性变化$A$之后得到$\vec v$

- $det(A)$也有关系

  - $=0$：没有逆，几何上的解释由于=0降维，是不能把低维的向量扩展到高维，因为可以有多个解
  - $\ne0$：即求$A^{-1}$，且$A^{-1}$存在，$A^{-1}A=I$得出$\vec x=A^{-1}\vec v$
  - rank：表示A的output的维度，即2D->1D=>rank=1，3D->2D=>rank=2

- 若A降维，则有多个向量/面被归到原点，这些向量称为Null Space/Kernel

  

- 点乘：$\vec v \cdot \vec w$表示$\vec v$在$\vec w$上的投影的长度乘以$\vec w$的长度（投影的对象可以是v到w，也可以是w到v，结果是一样的）

- 点乘的意义在几何上来说是投影，即把v投影到w；可以理解为把v使用w的线性变换降维，即2D->1D，如果w的长度是1，这个降维的结果是v在w上的长度，再乘以w方向，就成了v在w的投影

  
  
- 叉乘：$\vec v \times \vec w$的det表示两个向量组成的平行四边形的面积

- 数学上表示为$det\begin{pmatrix}\vec v_x&\vec w_x\\\vec v_y&\vec w_y\end{pmatrix}$, 即理解为单位向量变换到$\vec v， \vec w$的面积变化，由于单位向量的面积是1，所以叉乘的面积是det的值

- $\vec v \times \vec w = \vec k$，则$\vec k$的长度是$\vec v ， \vec w$形成的四边形的面积，方向垂直与四边形

  
  
- $\begin{bmatrix}v_x \\\ v_y \\\ v_z\end{bmatrix}\times\begin{bmatrix}w_x \\\ w_y \\\ w_z\end{bmatrix} = det(\begin{bmatrix}\hat i & v_x&w_x \\\ \hat j&v_y&w_y \\\ \hat k&v_z&w_z\end{bmatrix})$

- 把$\hat i, \hat j, \hat k$当作varibale，则矩阵$\begin{bmatrix}\hat i & v_x&w_x \\\ \hat j&v_y&w_y \\\ \hat k&v_z&w_z\end{bmatrix}$构成了一个3D的平行四面体，通过移动variable来改变四面体的形状

- 存在一个3D->1D的线性变换$\vec P$，使得。$\begin{bmatrix}P_x \\\ P_y \\\ P_z\end{bmatrix}\cdot\begin{bmatrix}i \\\ j \\\ k\end{bmatrix} = det(\begin{bmatrix}\hat i & v_x&w_x \\\ \hat j&v_y&w_y \\\ \hat k&v_z&w_z\end{bmatrix})$

- $A^{-1}MA$表示了从其他坐标系统变换到标准坐标系统的矩阵$A$，在标准坐标系统应用可能的变换$M$，再从标准坐标系统变换到原坐标系统$A^{-1}$的过程。

  
  
- Eigen vector就是在线性变换之后，span不变，只是scale变化的vector，即变换前后的方向是不变的

- 3D rotation的eigen vector就是旋转轴

- eigen vector更能表示线性变化的特点

  - 即$A\vec v = \lambda \vec v$中的$\vec v$，表示了线性变换A的的特点，使得可以用简单的向量$\vec v$来表示复杂的线性变换$A$
  - 从$A\vec v = \lambda \vec v$推导出$A\vec v = (\lambda I) \vec v$，再移项提出v得到$(A-\lambda I)\vec v =  \vec 0$，从而得出$det(A-\lambda I)=0$，可以理解为$(A-\lambda I)$这个线性变换，把空间压缩，减少了一个维度
  - 计算出$\lambda$之后，把$\lambda$的值带入$A-\lambda I$得到新矩阵B，解$B\vec v=0$得到eigen vector $v$
  - eigen value是一个对角矩阵，所以计算的时候相对于普通的矩阵乘法要简单许多
  - 所以可以选择eigen vector作为坐标轴基向量，通过变换坐标轴，来简化线性变换矩阵，从而得到一个非常简单的对角矩阵



- 把多维的向量看作函数更好理解，因为函数的每一个值就可以对应向量的每一个分量，其他的操作也是一样的运算方法
- 更进一步从函数来说，也可以应用一个“线性变换”，把一个函数变换到另一个函数
- 函数的“线性”变换：
  - additivity：L(v+w)=L(v)+L(w)
  - scaling: L(kv)=kL(v)
- 求导就是“线性”的
- 函数的每一个指数未知数就是向量的一个值
- 求导的矩阵
  - $\begin{bmatrix}0&1&0&0&0&... \\\ 0&0&2&0&0&... \\\ 0&0&0&3&0&... \\\ ...\end{bmatrix}$
  - 其中1，2，3是$x$的幂数

# 线索2

# 线索3

# 总结：第三步在这里总结