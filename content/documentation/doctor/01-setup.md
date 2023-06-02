---
title: '设置'
priority: 1

# SEO
metaData:
  titleParts:
    - Setup
    - Doctor
    - Documentation
---

# 设置

Doctor是Clinic.js工具套装的一部分。要安装Doctor，只需像这样安装Clinic.js:

```bash
npm install -g clinic
```

安装完成后，我们可以通过运行带有 `--help` 标志的 `clinic doctor` 命令来检查Doctor是否已经安装。

```bash
clinic doctor --help
```

它应该输出类似下面的内容:

```
Clinic.js Doctor - v3.12.0

clinic doctor is the first step in profiling your application.
It will show you what kind of problem you are having and recommend the path
forward.

To run clinic doctor

  clinic doctor -- node server.js

If profiling on a server, it can be useful to only do data collection:

  clinic doctor --collect-only -- node server.js

You can then transfer the data and visualize it locally:

  clinic doctor --visualize-only PID.clinic-doctor-sample

Flags
-h | --help                Display Help
-v | --version             Display Version
--collect-only             Do not process data on termination
--visualize-only datapath  Build or rebuild visualization from data
--sample-interval interval Sample interval in milliseconds
--on-port                  Run a script when the server starts listening on a port.
--dest                     Destination for the collect data (default .).
```

---

##### 下一个

[准备](/documentation/doctor/02-getting-ready/)
