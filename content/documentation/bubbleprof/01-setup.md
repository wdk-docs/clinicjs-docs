---
title: "配置"
priority: 1

# SEO
metaData:
  titleParts:
    - Setup
    - Bubbleprof
    - Documentation
---

# 配置

Bubbleprof 是 `Clinic.js` 工具套装的一部分。
要安装 Bubbleprof，只需像这样安装 `Clinic.js`:

```bash
npm install -g clinic
```

在安装之后，我们可以通过运行带有`--help`标志的`clinic bubbleprof`命令来检查是否已经安装了 Bubbleprof。

```bash
clinic bubbleprof --help
```

它应该输出类似下面的内容:

```
Clinic.js BubbleProf - v1.11.0

clinic bubbleprof helps you find asynchronous bottlenecks and debug event loop blocking.

To run clinic bubbleprof

  clinic bubbleprof -- node server.js

If profiling on a server, it can be useful to only do data collection:

  clinic bubbleprof --collect-only -- node server.js

You can then transfer the data and visualize it locally:

  clinic bubbleprof --visualize-only PID.clinic-bubbleprof-sample

Flags
-h | --help                Display Help
-v | --version             Display Version
--collect-only             Do not process data on terminiation
--visualize-only datapath  Build or rebuild visualization from data
```

---

## 下一个

[准备](/documentation/bubbleprof/02-getting-ready/)
