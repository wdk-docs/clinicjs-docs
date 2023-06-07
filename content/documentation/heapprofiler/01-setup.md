---
title: "设置"
priority: 1

# SEO
metaData:
  titleParts:
    - Setup
    - Heap
    - Documentation
---

# 设置

堆分析器是 Clinic.js 工具套装的一部分。
要安装堆分析器，只需像这样安装 Clinic.js:

```bash
npm install -g clinic
```

在安装之后，我们可以运行带有“——help”标志的“clinic HeapProfiler”命令来检查 HeapProfiler 是否已经安装。

```bash
clinic heapprofiler --help
```

它应该输出类似下面的内容:

```
Clinic.js Heap Profiler - v3.0.0

clinic heapprofiler helps you find memory leaks
by creating a flamegraph visualization that assists in identifying
function calls that may be leaking memory.

To run clinic heapprofiler

  clinic heapprofiler -- node server.js

Once you exit (Ctrl-C) the process, your report will open in a browser window. You can disable this behavior:

  clinic heapprofiler --open=false -- node server.js

If profiling on a server, it can be useful to only do data collection:

  clinic heapprofiler --collect-only -- node server.js

You can then transfer the data and visualize it locally:

  clinic heapprofiler --visualize-only PID.clinic.heapprofile

You can use the --autocannon flag to simulate load on your server.
--autocannon accepts configuration for autocannon using "subarg" syntax:

  clinic heapprofiler --autocannon [ -m POST /api/example ] -- node server.js

When configuring --autocannon, the $PORT environment variable contains the
port your server is listening on:

  clinic heapprofiler --autocannon [ -m POST 'http://localhost:$PORT/?\$page=1' ] -- node server.js

Note that dollar signs ($) appearing in the URL must be escaped, else they
will be treated as environment variables as well.

Flags
-h | --help                Display Help
-v | --version             Display Version
--collect-only             Do not process data on termination
--visualize-only datapath  Build or rebuild visualization from data
--on-port                  Run a script when the server starts listening on a port.
--autocannon               Run the autocannon benchmarking tool when the server starts listening on a port.
--open                     Boolean to enable or disable your report opening in your web browser.
--dest                     Destination for the collected data (default .clinic/).
```

---

## 下一个

[准备](/documentation/heapprofiler/02-getting-ready/)
