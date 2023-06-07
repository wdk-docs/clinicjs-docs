---
priority: 1

# SEO
metaData:
  titleParts:
    - Simulating load
    - CLI
    - Documentation
---

# 模拟负载

如果我们的应用程序处理请求，在测试它的性能时，简单地将 Clinic.js 指向它并不会特别有洞察力，因为除非我们手动使用正在运行的应用程序，否则不会有负载需要监控。
解决这个问题的一种方法是使用基准测试工具(如[autocannon](https://github.com/mcollina/autocannon))模拟负载。

## 使用 autocannon

我们可以很容易地使用`--autocannon`标志在我们的服务器上模拟负载:

```bash
clinic doctor --autocannon [ 'localhost:$PORT' ] -- node server.js
```

Clinic.js 会自动将`$PORT`的值替换为服务器在`server.js`中侦听的实际端口。
为了使事情变得更简单，如果我们已经将服务器设置为使用`PORT`环境变量作为应用程序端口，我们可以产生与上述命令相同的结果，如下所示:

```bash
clinic doctor --autocannon [ / ] -- node server.js
```

Here `/` is the same as `'localhost:$PORT'` inside the subargs: `[ ]`.

_小心确保在开始方括号之后和结束方括号之前有空格，以确保正确解析子参数。_

### 常见的自动标签

所有可用的标志都可以在[autocannon README](https://github.com/mcollina/autocannon#command-line)中看到，但下面记录了一些更常见的标志。

#### 连接数

默认情况下，autocannon 将并发连接数设置为 10。
例如，要将其更改为 100，我们可以将`-c`或`——connections`标记设置为子参数，如下所示:

```bash
clinic doctor --autocannon [ -c 100 / ] -- node server.js
```

#### HTTP methods

假设我们有一个带有 POST 端点的 API，我们想要测试和监控，这很容易使用`-m`或`——method`标志作为子参数来完成:

```bash
clinic doctor --autocannon [ -m POST /api/item ] -- node server.js
```

如果没有在请求体中发送一些实际数据，这可能没有那么有用，所以让我们使用`-b`或`——body`标志作为子参数添加一些数据:

```bash
clinic doctor --autocannon [ -m POST /api/item -b '{"my": "data"}' ] -- node server.js
```

使用 JSON 字符串或任何其他数据类型作为命令的一部分，这可能有点难以管理，特别是如果我们想要使用不同的数据集或不同的长度测试不同的端点。
autocannon 支持使用本地文件为请求体提供数据，所以对于一些 JSON 文件，我们可以使用`-i`标记简化负载测试，如下所示:

```bash
clinic doctor --autocannon [ -m POST /api/item -i my-data.json ] -- node server.js
```

干净!

## 使用我们自己的命令

为了获得更多的控制，我们可以使用`——on-port`标志将任何自定义命令指向我们的服务器。
全局安装`autocannon`后，我们可以在应用程序上模拟加载，如下所示:

```bash
clinic doctor --on-port 'autocannon localhost:$PORT' -- node server.js
```

就像使用`——autocannon`标志一样，Clinic.js 将`$PORT`的值替换为服务器在`server.js`中侦听的实际端口。

`——on-port`标志的优点是，它使我们能够灵活地使用我们喜欢的任何命令，包括其他基准测试工具，如[wrk](https://github.com/wg/wrk)。
例如，在全局安装了`wrk`的情况下，类似的命令是:

```bash
clinic doctor --on-port 'wrk http://localhost:$PORT' -- node server.js
```

然后，Clinic.js 简单地监视应用程序在模拟负载下的性能，并在运行`——on-port`的脚本退出时生成一个示例。
我们使用哪个脚本完全取决于我们，我们可能已经有一些复杂的测试命令，如[NPM 脚本](https://docs.npmjs.com/cli/run-script.html)，所以我们可以很容易地调用其中一个:

```bash
clinic doctor --on-port 'npm run load-test' -- node server.js
```

---

## 下一个

[控制输出](./02-controlling-the-output.md)
