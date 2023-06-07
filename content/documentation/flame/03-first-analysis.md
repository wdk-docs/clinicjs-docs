---
title: "分析"
priority: 3

# SEO
metaData:
  titleParts:
    - 首先分析
    - Flame
    - Documentation
---

# 分析

现在我们已经准备好分析应用程序了。

让我们尝试使用 repo 中的第一个服务器, `1-server-with-slow-function.js`。

它包含一个 HTTP 服务器，使用 Express 构建带有根路由(`/`)的服务器，该服务器在呈现登陆页面之前执行一些工作。

服务器可以通过`node 1-server-with-slow-function.js`启动，然后通过 http://localhost:3000/在浏览器中访问。
如果登陆页面显示"Hello World"，那么一切正常!

让我们尝试使用 Flame 对服务器进行分析，看看是否可以找到任何瓶颈。

要做到这一点，我们需要一个工具，可以模拟足够强烈的 HTTP 负载。

我们建议使用`autocannon` ，它支持 Windows、Mac 和 Linux，而且使用起来很简单。

让我们从 npm 安装它:

```bash
npm install -g autocannon
```

为了运行分析，我们想用 Flame 运行服务器，当服务器准备好了 - 比如开始监听端口 - 我们想用“autocannon”向它发送大量的请求。

所有这些都可以用一个命令执行，可以原样复制和粘贴:

```bash
clinic flame --on-port 'autocannon localhost:$PORT' -- node 1-server-with-slow-function.js
```

让我们分解这个命令:

- `clinic flame`部分调用`flame`命令工具。
- `——on-port`标志将在服务器开始侦听端口时立即执行提供的脚本。
- 该脚本中的`$PORT`变量被设置为服务器开始侦听的第一个端口。
- 双破折号(`——`)之后的所有内容都是启动我们想要分析的服务器的命令，在本例中是`node 1-server-with-slow-function.js`。

这个命令运行三个可执行文件:`clinic flame`父可执行文件，`autocannon`在`--on-port`中的可执行文件和`node`可执行文件。

运行该命令后，将对进程进行 10 秒的加载测试(按照`autocannon`的默认持续时间)，然后将结果编译成一个 HTML 文件，该文件应自动在浏览器中打开。

生成的 HTML 应该类似于以下内容:

![Flamegraph screenshot](03.png)

这就是所谓的火焰图。

---

## 下一个

[Flamegraphs](/documentation/flame/04-flamegraphs)
