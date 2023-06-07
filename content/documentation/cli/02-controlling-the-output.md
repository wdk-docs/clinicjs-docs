---
priority: 3

# SEO
metaData:
  titleParts:
    - Controlling the output
    - CLI
    - Documentation
---

# 控制输出

默认情况下，任何 Clinic.js 工具命令都会生成一个编译后的 HTML 文件和数据目录，所以下面的命令:

```bash
clinic doctor -- node server.js
```

将生成如下的文件结构:

```
.clinic/1234.clinic-doctor/1234.clinic-doctor-processstat
.clinic/1234.clinic-doctor/1234.clinic-doctor-systeminfo
.clinic/1234.clinic-doctor/1234.clinic-doctor-traceevent
.clinic/1234.clinic-doctor.html
```

_确切的输出将在[Doctor](/doctor/), [Flame](/flame/) 和 [Bubbleprof](/bubbleprof/)之间变化，因为每个工具生成和需要略微不同的数据来创建样本。_

## 仅收集数据

为了防止任何工具生成 HTML，我们可以像这样使用`——collect-only`标志:

```bash
clinic doctor --collect-only -- node server.js
```

这将生成一个目录，从中可以生成 HTML 配置文件，其文件结构类似如下:

```
.clinic/1234.clinic-doctor/1234.clinic-doctor-processstat
.clinic/1234.clinic-doctor/1234.clinic-doctor-systeminfo
.clinic/1234.clinic-doctor/1234.clinic-doctor-traceevent
```

## 可视化现有数据

要从 Clinic.js 收集的数据中生成或重新生成 HTML 配置文件，我们可以使用`——visualization -only`标志，并将现有数据的本地路径传递给它，如下所示:

```bash
clinic doctor --visualize-only .clinic/1234.clinic-doctor
```

这将在其数据目录`1234.clinic-doctor`的同一目录下生成以下 HTML 文件:

```
.clinic/1234.clinic-doctor.html
```

请注意，由于我们是从现有示例生成示例可视化，因此在将目录路径传递给`——visualize-only`标志时，不需要在`——`标志分隔符之后调用任何服务器启动脚本。

## 更改输出目的地

默认情况下，所有工具示例文件都将在运行命令的目录(`.`)中生成。
要改变这种情况，我们可以使用`--dest`标志指向不同的目的地，如下所示:

```bash
clinic doctor --dest ../some-other-dir -- node server.js
```

这在生成大量的 Clinic.js 文件时非常有用，以确保它们不在项目目录中，并避免任何版本控制错误!

---

## 下一个

[管理样品](./03-managing-samples.md)
