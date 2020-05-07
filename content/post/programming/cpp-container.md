---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Cpp Container"
subtitle: ""
summary: ""
authors: [admin]
tags: [c++]
categories: [Programming]
date: 2020-04-19T11:58:45+09:00
lastmod: 2020-04-19T11:58:45+09:00
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

C++ Container 的笔记

[原文](https://embeddedartistry.com/blog/2017/08/02/an-overview-of-c-stl-containers/)

The C++ container library categorizes containers into four types:

- Sequence containers:
  - `array` represents a static contiguous array
  - `vector` represents a dynamic contiguous array
  - `forward_list` represents a singly-linked list
  - `list` represents a doubly-linked list
  - `deque` represents a double-ended queue, where elements can be added to the front or back of the queue.
- Sequence container adapters: They are not full container classes on their own, but wrappers around other container types (such as a vector, deque, or list)
  - `stack` provides an LIFO data structure
  - `queue` provides a FIFO data structure
  - `priority_queue` provides a priority queue, which allows for constant-time lookup of the largest element (by default)
- Associative containers: provide sorted data structures that provide a fast lookup (*O(log n)* time) using keys.
  - Keys are unique
    - `set` is a collection of unique keys, sorted by keys
    - `map` is a collection of key-value pairs, sorted by keys
      set and map are typically implemented using red-black trees
  - Multiple entries for the same key are permitted
    - `multiset` is a collection of keys, sorted by keys
    - `multimap` is a collection of key-value pairs, sorted by keys
- Unordered associative containers: Access times are O(n) in the worst-case, but much faster than linear time for most operations.
  - Keys are unique
    - `unordered_set` is a collection of keys, hashed by keys
    - `unordered_map` is a collection of key-value pairs, hashed by keys
  - Multiple entires for the same key are permitted
    - `unordered_multiset` is a collection of keys, hashed by keys
    - `unordered_multimap` is a collection of key-value pairs, hashed by keys

### Thread Safety

I want to share with you some relevant points regarding container thread safety, as many embedded systems will likely require sharing objects across threads. The following general thread-safety rules apply:

- All container functions are safe to be called concurrently on different objects of the same container type (i.e. it is safe to use two different `std::vector` instances on two different threads
- All `const` member functions can be called concurrently by different threads
- Containers can be safely read from multiple threads if no thread is making asynchronous writes
- Different elements in the same container can be modified concurrently, except for the elements of `std::vector`.
- If an object is written to by one thread and read by other threads, the object must be protected
- In general, iterator operations read from a container, but do not modify it, so they are thread-safe
  - Container operations that invalidate iterators are NOT thread-safe, as they modify the container