---
title: CPU性能 —— 单核篇（施工中）
tags:
  - Performance
---







### How a modern cpu works roughly



### TMAM

PMC，vtune



The CPU Front-End consists of a number of data structures that serve the main goal toefficiently fetch and decode instructions from memory. Its main purpose is to feed prepared instructions to the CPU Back-End, which is responsible for the actual execution of instructions.



### 换一个视角

[Four Cornerstones of CPU Performance. | Easyperf](https://easyperf.net/blog/2022/10/17/Four-Cornerstones-of-CPU-Performance)

#### Predictability of Code

* Ideal: Every branch outcome is predicted correctly in 100% of the cases.
* Worst: random control flow patterns.

#### Predictability of Data

* Ideal: Every memory access is served from a closest cache. 
* Worst: random memory access patterns with large strides.

#### Execution Throughput

* Ideal: No stalls in the execution pipeline, 100% of the CPU bandwidth is utilized. 
* Worst: Instructions compete for a particular execution resource.

#### Execution Latency（Data Dependency Chains）

* Ideal: massively parallel application few/short dependencies.
* Worst: a long sequence of dependent instructions,e.g. pointer chaising. 



### 例子

#### Memory Bound



#### Core Bound



#### bad_speculation



#### Front-End Bound

FE没法即使把指令送去BE，所以Back-End在空等Front-End送来指令。

caches utilization and inability to fetch instructions from memory



### 总结

欢迎提issue交流：[Issues · jsjtxietian/jsjtxietian.github.io](https://github.com/jsjtxietian/jsjtxietian.github.io/issues)



