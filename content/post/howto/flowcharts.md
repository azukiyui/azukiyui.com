---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Flowcharts"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2020-04-18T07:45:43+09:00
lastmod: 2020-04-18T07:45:43+09:00
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



使用以下的shortcode来添加flowchart，预览则使用Typora的flow功能

{{\%flowchart\%}} 

{{\% /flowchart\%}}

{{% flowchart%}}

```flow
st=>start: Start:>http://www.google.com[blank]
e=>end:>http://www.google.com
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?:>http://www.google.com
io=>inputoutput: catch something...
para=>parallel: parallel tasks

st->op1->cond
cond(yes)->io->e
cond(no)->para
para(path1, bottom)->sub1(right)->op1
para(path2, top)->op1
```

{{% /flowchart%}}