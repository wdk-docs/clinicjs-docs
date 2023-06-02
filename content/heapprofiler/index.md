---
title: Clinic.js HeapProfiler
subtitle: Uncovers memory allocations by functions with Flamegraphs.
---

火焰图是随时间分配的内存的聚合可视化。
每个块表示一个函数分配的内存量。
块越宽，分配的内存就越多。

## 演示

<video src="../assets/videos/heapprofiler-screen-recording.mp4" playsinline loop autoplay muted></video>

**[互动的例子](../assets/html/heapprofiler-example.html)**

## 配置

```bash
npm install -g clinic
clinic heapprofiler --help
```
