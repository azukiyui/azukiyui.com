---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "System Design"
subtitle: ""
summary: ""
authors: [admin]
tags: [leetcode, system design]
categories: [Programming]
date: 2020-04-28T15:36:21+09:00
lastmod: 2020-04-28T15:36:21+09:00
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

这是[这个系列](https://www.youtube.com/watch?v=prFEyaUEAMM&list=PLLuMmzMTgVK7XfFadhkPuF_ztvhxbriDr&index=16&t=0s)的视频的笔记

# EP1 Process and Thread

### Thread: 

- programmed instructions
- independently
- own regiters: program counter, stack pointer

### Process: 

- intance of a program

###  Parallel computing

- multi-threading: shared memory
- multi-processing: independent memory

### Code example

```c++
std::thread t1(run);//thread
//main thead contains t1 thread
pid_t pid=fork();//process
//parent pid => child id
//child pid => 0
//child start from fork()
```

### Communication

- Threading: 
  - shared variables
  - semaphore, mutex, lock
- processing:
  - shared menory
  - pipe: process->stdout->stdin->other process
  - socket
  - PRC

# EP2 Why multi threading

- More responsive
  - avoid blocking main thread
  - run heavy job
    - IO
    - CPU bound

- Speeding up: multi-core cpu

# EP3 Monte Carlo Method

### 简介

- 基于数值的统计计算方法
- random sampleing
- pro：
  - general
  - can solve hard problems

- cons：
  - slow convergence
  - inaccuracy

### Example

1. 计算PI
   - random sample point in space
   - count how many point in the circle
   - PI=num of in-circle points/num of all points
2. 计算微积分
   - random sample point in space
   - num of points/num of all points

## EP4 Floating point

### 32位浮点数的表示

$(-1)^s\times f\times 2^e$

s是sign位，1bit

f是floating位，一般23bit

e是exp位，一般8bit

内存排列是：s位e位f位

有效位数是小数点后7位

### 使用浮点数的问题

- 很大的数+很小的数：
  - 很小的数没有实际加上去
  - 先加到0上，在加很大的数
- 比较浮点数
  - 编译器会有优化
  - 使用abs(a-b)<ep

- 需要比较好的精度，使用double

### ML的使用趋势

- 精度要求两极分化
- quantization：float->uint8

## EP5/EP6 Lifetime of a variable/Reference

Stack

- automatically destoried
- primitive types/struct/class

Heap

- management
  - raw pointer: explicit new/delete
  - smart pointer: 
    - unique_ptr: destory out of scope
    - shared_ptr: destory reference count becomes 0

## EP7 System Design: Autocomplete

- clarify:
  - SAL:(qps/latency)
  - data source
  - amount of data/memory/disk/cpu...hardware
- Design:
  - architecture/algrithm/data structure/DB
  - scale: shard(seperate data into each machine) vs. replica(load balancing)
  - front/backend, interface: http->getway->rpc
  - trade offs/justify desision
- Autocomplete
  - autocomplete for youtube
    - how many entries? 10b
    - data source: log
    - latency: 100ms in 99%
    - machine spec: hardware
  - logs->tires->data->multiple servers(with replicas)
  - type->frontend->http->gateways->servers

## EP8/9

- std::initializer_list类型

```c++
auto a = {1,2,3};
vector<int> b = a;
//==> b = vector<int>(a);
//a is std::initializer_lype
```

## EP11 Multi-Threading

Leetcode有几题相关的题

## EP10 A*

A*算法

- Dijkstra的extention
- Dijkstra: f(n)=g(n)
- A*: f(n)=g(n)+h(n)
- g(n): cost from start
- h(n): estimated cost from current to target
- Time: O(|E|log|V|)
- Space: O(|V|)

## EP12

C++的2D array是colum major，连续排列的

## EP 13 Proto Buffer

https://github.com/huahualeetcode/SharpProto

## EP 15 Modern c++

- `std::initializer_list<T>`

- `auto`

- structtured binding

  ```c++
  pair<int, float> p(1,3.14);
  const auto& [x,y] = p;
  
  set<int> s;
  const auto [it, success] = s.insert(x);
  ```

- range based loop

  ```c++
  map<string, int> m;
  for(auto&& [key, val] : m)
  {
  	cout<<key<<val;
  }
  ```

- lambda expression

  ```c++
  auto comp = [](const auto& a, const auto& b){return a<b;};
  set<int, decltype(comp)> a(comp);
  
  class Foo
  {
      void Init()
      {
          bar->onUpdate([this](const auto& data)
                {
                    //在Bar中调用Foo的Private function
                    this->UpdateFoo(data);
                });
      }
      
      Bar* bar;
      void UpdateFoo(const int data){}
  }
  ```

- string_view