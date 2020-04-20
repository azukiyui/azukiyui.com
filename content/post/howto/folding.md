---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Folding"
subtitle: ""
summary: ""
authors: [admin]
tags: [blog]
categories: [HowTo]
date: 2020-04-19T09:53:15+09:00
lastmod: 2020-04-19T09:53:15+09:00
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

折叠一段内容，可以用如下的html来实现

```html
<details>
  <summary>Click to expand!</summary>
  
  ## Heading
  1. A numbered
  2. list
     - With some
     - Sub bullets
</details>
```



<details>
  <summary>Click to expand!</summary>

  ## Heading
  1. A numbered

  2. list
     - With some
     - Sub bullets

3. 这是代码的例子：使用\<p>和<\\p>

  <p>

  ```c#
  public class Order
  {
      public int OrderId { get; set; }
      public int CustomerId { get; set; }
  
      public List<int> Products { get; set; }
  }
  ```

  </p>

</details>



这是折叠的例子

