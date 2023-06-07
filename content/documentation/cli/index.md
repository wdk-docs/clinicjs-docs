---
priority: 4

# SEO
metaData:
  titleParts:
    - CLI
    - Documentation
---

# CLI

Clinic.js 提供了许多工具来帮助我们识别 Node.js 应用程序中的性能问题。
一旦安装了[Clinic.js](/documentation/)，就可以使用顶层的' clinic '命令访问所有这些工具。

## 命令的剖析

生成[Doctor](/doctor/)样本的最简单形式的 Clinic.js 命令如下:

```
clinic doctor -- node server.js
```

“——”表示[命令和标志的结束](https://nodejs.org/api/cli.html#cli_1)，将命令分为以下两个相关部分:

**1.** ' clinic doctor '通知 Clinic.js 我们希望使用[clinic .js doctor](/documentation/doctor/)来获得应用程序当前性能的概述。

**2.** ' node server.js '是我们用来从命令行正常运行 Node.js 应用程序的命令。

如果我们的应用程序需要一些[环境变量](https://nodejs.org/api/cli.html#cli_environment_variables)，我们可以事先设置它们:

```
NODE_ENV=production clinic doctor -- node server.js
```

从这里开始，我们可以通过[simulating load](./01-simulating-load.md)开始充分利用 Clinic.js。

## 查看工具信息

要查看与 Clinic.js 工具相关的所有帮助信息，包括版本和[支持的标志](/documentation/cli/04-reference/#flags)，我们可以简单地运行:

```
clinic doctor --help
```

或者，快速查看每个 Clinic.js 工具的版本:

```
clinic flame --version
```

如果我们只想查看有关已安装的 Clinic.js 版本的信息:

```
clinic --help
```

或者，查看已安装的 Clinic.js 版本:

```
clinic --version
```

有关完整的选项列表，请参阅[CLI 参考](./04-reference.md).

---

##### 下一个

[模拟负载](./01-simulating-load.md)
