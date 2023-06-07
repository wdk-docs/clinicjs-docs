---
title: "设置"
priority: 1

# SEO
metaData:
  titleParts:
    - Setup
    - Flame
    - Documentation
---

# 设置

Flame 是 Clinic.js 工具套装的一部分。要安装 Flame，只需像这样安装 Clinic.js:

```bash
npm install -g clinic
```

安装后，我们可以运行带有 `--help` 标志的 `clinic flame` 命令来检查 Flame 是否已经安装。

```bash
clinic flame --help
```

它应该输出类似下面的内容:

```
Clinic.js Flame - v3.6.0 (0x v4.7.2)

clinic flame helps you find synchronous bottlenecks
by creating a flamegraph visualization that assists in identifying
function calls that may be blocking the event loop.

For more information see the 0x readme, https://github.com/davidmarkclements/0x

To run clinic flame

  clinic flame -- node server.js

If profiling on a server, it can be useful to only do data collection:

  clinic flame --collect-only -- node server.js

You can then transfer the data and visualize it locally:

  clinic flame --visualize-only PID.clinic.flame

Flags
-h | --help                Display Help
-v | --version             Display Version
--collect-only             Do not process data on termination
--visualize-only datapath  Build or rebuild visualization from data
```

---

## 下一个

[准备](/documentation/flame/02-getting-ready/)
