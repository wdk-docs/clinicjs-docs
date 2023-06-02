---
title: Clinic.js Flame
subtitle: Uncovers the bottlenecks and hot paths in your code with flamegraphs
---

引用其发明者Brendan Gregg的话，[火焰图](http://www.brendangregg.com/flamegraphs.html)是一种分析软件的可视化，允许快速准确地识别最常见的代码路径。
Flame是专门为Node.js设计的，被内置于Clinic.js中。
它收集CPU采样使用的指标，然后跟踪堆栈顶部的频率并创建火焰图。

火焰图是随时间采样的堆栈的聚合可视化。
它主要可视化两个指标。
一个函数在CPU上的时间，以及一个函数在栈顶的时间。
最后被调用的函数被称为位于堆栈顶部的函数。
如果观察到一个函数在堆栈顶部的次数比其他函数多，则该函数可能阻塞了事件循环。
如果观察到一个函数以较高的比率位于堆栈的顶部，则将其称为"hot"。

## 演示

<video src="../assets/videos/flame-screen-recording.mp4" playsinline loop autoplay muted></video>

**[交互例子](../assets/html/flame-example.html)**

## 设置

```bash
npm install clinic -g
clinic flame --help
```
