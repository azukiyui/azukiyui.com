---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "看文章/读书/做计划/开发/学习的流程"
subtitle: ""
summary: ""
authors: [admin]
tags: [Flow]
categories: [GTD]
date: 2020-06-13T14:12:41+09:00
lastmod: 2020-06-13T14:12:41+09:00
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

- 明确几个工具软件的角色
  - Zotera：适合收集处理PDF，文章，书籍等各种数据，也是主要的信息存放软件
  - Onenote：逐渐被Zotero代替；日语笔记的部分暂时保留
  - Nirvana：主要的日常、开发的任务追踪，基本不存放资料类的数据
  - Obsidian：主要的笔记软件，大多数的笔记都会在这里，而少量的会放到Zotera；同时和Zotera共享Attachments，基本所有的PDF和网页的文章都会同步到Obsidian的目录，这样笔记就可以直接引用这些文件（Obsidian还不支持非PDF文件，但是可以直接生成同名md文件来暂时处理）
  - MindMap：在Dropbox以md文件形式存放，基本是中间数据，需要定时Archive
- 若是新的事务：
  - 注意区分资料、任务和笔记，把他们放到对应的工具软件
  - 如文章阅读：
    1. 在Zotero的Inbox发现一篇需要文章
    2. 把同名任务添加到Nirvana的阅读计划
    3. 在Obsidian建立同名笔记
       - 网页文章使用浏览器的annotation工具，看完后导出到Obsidian
       - PDF文章使用普通的PDF软件和PDF Expert，看完之后既可以在Zotero生成Note，也可以导出到Obsidian
    4. 完成之后将Zotero的文章归好类
  - 如开发任务：
    1. 在Nirvana建立Project
    2. 若需要学习或者文章阅读，参照上面的文章阅读例子
    3. 若需要Mindmap，则在Dropbox建立同名mindmap
    4. 若需要整理知识体系，则直接在Obsidian整理
- 若是正在做的事务，从Nirvana一般会有追踪，Obsidian可能会有一个Introduction页面