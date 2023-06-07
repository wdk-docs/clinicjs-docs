---
priority: 5

# SEO
metaData:
  titleParts:
    - Reference
    - CLI
    - Documentation
---

# 命令参考

本页包含了所有 Clinic.js 支持的命令和标志的参考，以帮助我们最大限度地利用 Clinic.js。

## 命令

### `clinic doctor`

用'——'分隔符分隔，该命令为 Node.js 应用程序获取一个启动脚本，并生成[Doctor](/doctor/)样本来诊断性能问题。

**Example**:

```bash
clinic doctor -- node server.js
```

有关更多技术信息，请访问[Doctor docs](/documentation/doctor/).

### `clinic flame`

用'——'分隔符分隔，该命令为 Node.js 应用程序提供一个启动脚本，并生成[Flame](/flame/)示例，以发现带有火焰图的代码中的瓶颈和热函数。

**Example**:

```bash
clinic flame -- node server.js
```

有关更多技术信息，请访问[Flame 文档](/documentation/flame/).

### `clinic bubbleprof`

这个命令用'——'分隔符分隔，它需要一个 Node.js 应用程序的启动脚本，并生成[Bubbleprof](/bubbleprof/)样本来观察和映射异步操作。

**Example**:

```bash
clinic bubbleprof -- node server.js
```

有关更多技术信息，请访问[Bubbleprof 文档](/documentation/bubbleprof/).

## 旗帜

下面是一个有用的标志(选项)的参考列表，当使用 Doctor、Flame 和 Bubbleprof 生成样本时，这些标志(选项)可以传递给 Clinic.js。

### `--on-port`

接受一个命令字符串，当被分析的应用程序开始监听端口时执行。

**Example**:

```bash
clinic doctor --on-port 'my-script localhost:$PORT' -- node server.js
```

关于这个用例标志的更多信息可以在[模拟加载文档](/documentation/cli/01-simulating-load/#using-our-own-command)中找到。

### `--autocannon`

在'[]'中获取子参数，并将其传递给 autocannon。

**Example**:

```bash
clinic doctor --autocannon [ 'localhost:$PORT' ] -- node server.js
```

关于这个用例标志的更多信息可以在[模拟加载文档](/documentation/cli/01-simulating-load/#using-autocannond)中找到。

### `--collect-only`

如果使用的话，Clinic.js 工具只会生成一个样本信息目录，没有可视化的 HTML。

**Example**:

```bash
clinic doctor --collect-only -- node server.js
```

关于这个标志的更多信息可以在[控制输出文档](/documentation/cli/02-controlling-the-output/#collecting-data-only)中找到。

### `--visualize-only`

获取先前收集的 Clinic 工具示例数据目录的路径，并生成可视化 HTML，以便在浏览器中查看输出。

**Example**:

```bash
clinic doctor --visualize-only .clinic/1234.clinic-doctor
```

关于这个标志的更多信息可以在[控制输出文档](/documentation/cli/02-controlling-the-output/#visualizing-existing-data)中找到。

### `--dest`

获取本地目录的路径，生成的示例输出将保存到该目录。

**Example**:

```bash
clinic doctor --dest ../some-other-dir -- node server.js
```

关于这个标志的更多信息可以在[控制输出文档](/documentation/cli/02-controlling-the-output/#changing-the-output-destination)中找到。

**Default**: `.` (current directory)

### `--sample-interval`

获取一个数字，并以毫秒为单位改变 Doctor 对应用程序进行采样的速率。

**Example**:

```bash
clinic doctor --sample-interval 100 -- node server.js
```

**Default**: `10`

_此标志适用于`clinic doctor`命令。_

### `--version`

如果使用，将输出当前安装的 Clinic.js 版本或特定的 Clinic.js 工具。

**例子**:

```bash
clinic --version
# or
clinic -v

clinic doctor --version
# or
clinic doctor -v
```

### `--help`

如果使用，将输出带有示例命令的帮助文本和支持的 Clinic.js 或特定的 Clinic.js 工具的标志。

**例子**:

```bash
clinic --help
# or
clinic -h

clinic doctor --help
# or
clinic doctor -h
```
