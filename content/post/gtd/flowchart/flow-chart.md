---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Flow Chart"
subtitle: ""
summary: ""
authors: [admin]
tags: [Flowchart]
categories: [GTD]
date: 2020-04-14T08:30:10+09:00
lastmod: 2020-04-14T08:30:10+09:00
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

```mermaid
graph TD
	start((选择当前事务的流程))
	selectPlace(判断当前地点)
	home(家)	
	click home "../home"
	
	onTheWay(出门/路上)
	workplace(公司)
	
	start-->selectPlace
	selectPlace-->home	
	selectPlace-->onTheWay
	selectPlace-->workplace
	

	
```

