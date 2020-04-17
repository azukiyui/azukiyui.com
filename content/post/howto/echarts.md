---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Echarts"
subtitle: ""
summary: ""
authors: [admin]
tags: [blog]
categories: [HowTo]
date: 2020-04-18T07:14:57+09:00
lastmod: 2020-04-18T07:14:57+09:00
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



添加了echarts的支持，使用shortcode的方法，添加如下的json string，注意json的item需要加引号 \"\"， 可以有换行，不能有tab

```json
{

"title": {"text": "ECharts example" },

"tooltip": {}, 

"legend": { "data":["销量"] },

"xAxis": {  "data": ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"] },

"yAxis": {}, 

 "series": [{"name": "销量",  "type": "bar",  "data": [5, 20, 36, 10, 10, 20]  }]

} 
```



{{% echarts %}}

{

"title": {"text": "ECharts example" },

"tooltip": {}, 

"legend": { "data":["销量"] },

"xAxis": {  "data": ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"] },

"yAxis": {}, 

 "series": [{"name": "销量",  "type": "bar",  "data": [5, 20, 36, 10, 10, 20]  }]

} 

{{% /echarts %}}