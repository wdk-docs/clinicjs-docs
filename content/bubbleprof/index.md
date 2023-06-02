---
title: Clinic.js Bubbleprof
subtitle: Bubbleprof is a new, completely unique, approach to profiling your Node.js code
---

Bubbleprof是一种全新的方式来可视化你的Node.js进程的操作。
它观察应用程序的异步操作，对它们进行分组，测量它们的延迟，并绘制应用程序异步流中的延迟图

阅读[介绍性博客文章](https://clinicjs.org/blog/introducing-bubbleprof/)和[发布公告](https://www.nearform.com/blog/introducing-clinic-bubbleprof-a-unique-way-to-visualise-node-js-code/)。

## 它是如何工作的

每个气泡的大小表示一组操作中的时间。
将这些流放在您自己的代码、模块或节点核心中的位置进行分组。
小的相邻组也分组以减少杂乱。
连接气泡的箭头的长度显示了流从一个组移动到另一个组时的延迟。
内部的彩色线表示造成此延迟的异步操作类型的混合。
点击查看。
气泡和数字标签之间和周围的线长度反映了以毫秒(ms)为单位的聚合延迟。

## 演示

<video src="../assets/videos/bubbleprof-screen-recording.mp4" playsinline loop autoplay muted></video>

**[互动的例子](../assets/html/bubbleprof-example.html)**

## 设置

```bash
npm install -g clinic
clinic bubbleprof --help
```
