---
# SEO
metaData:
  titleParts:
    - Documentation
---

# 开始

在开始使用Clinic.js之前，首先让我们确保将其安装在我们的机器上，并运行几个测试以确保一切正常。让我们按照以下步骤开始:

**1.** 注意:你必须使用Node.js `>= 8.11.1`版本

```bash
npm install -g clinic
```

**2.** 确认它已经安装好了:

```bash
clinic --help
```

**3.** 它应该输出类似下面的内容:

```
Clinic.js - v2.2.1

Getting started
As a first step, run the clinic doctor:

  clinic doctor -- node server.js

Then benchmark your server with wrk or autocannon:

  wrk http://localhost:3000
  autocannon http://localhost:3000

Finally shut down your server (Ctrl+C). Once the server process has shutdown
clinic doctor will analyse the collected data and detect what type of issue
you are having. Based on the issue type, it will provide a recommendation for
you.

For example, to debug I/O issues, use Clinic.js Bubbleprof:

  clinic bubbleprof -- node server.js

Then benchmark your server again, just like you did with clinic doctor.

Report an issue
If you encounter any issue, feel free to send us an issue report at:

  https://github.com/clinicjs/node-clinic/issues

Utilities
When using clinic a bunch you have fill up your directory with data folders and files.
You can clean these easily using clinic clean.

More information
For information on the clinic sub-commands, use the --help option:

  clinic doctor --help
  clinic bubbleprof --help
  clinic clean --help
  clinic flame --help
  clinic heapprofiler --help

Flags
-h | --help                Display Help
-v | --version             Display Version
```

**4.** 我们在Github上有一组示例应用程序。让我们使用[Clinic.js Doctor](/doctor/)和autocannon来运行第一个:

```bash
git clone git@github.com:nearform/node-clinic-doctor-examples.git
cd node-clinic-doctor-examples
npm install
clinic doctor --autocannon [ / ] -- node ./slow-io
```

这将对一个有IO问题的简单应用程序运行autocannon，一旦它完成，它将自动启动浏览器中的Doctor工具。

---

##### 下一个

通常，在使用Clinic.js时，我们首先使用Clinic.js Doctor来识别应用程序中存在的性能问题。然后医生会给我们建议下一步要做什么工具和询问。

[开始使用Clinic.js Doctor](./doctor/index.md).

或者，您可以深入了解CLI的概述。
[CLI](./cli/index.md).
