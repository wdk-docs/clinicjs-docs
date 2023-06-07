---
priority: 4

# SEO
metaData:
  titleParts:
    - Managing samples
    - CLI
    - Documentation
---

# 管理样品

在使用 Clinic.js 工具深入了解应用程序的性能、解决了一些观察到的瓶颈并重新测试之后，我们可能会得到一个目录，里面装满了由 Clinic.js 生成的示例。
要删除所有这些文件和目录，我们可以在这些示例所在的目录下运行以下命令:

```bash
clinic clean
```

如果我们把文件放在了其他地方，我们可以简单地添加'——path '标志来指向那个目录:

```bash
clinic clean --path ../some-other-dir
```

运行此命令后，目录中应该没有更多的示例。
如果我们已经完成了对应用程序的分析，并且需要推送代码更改，但又不希望在应用程序的 repo 中看到 Clinic.js 示例，那么这一步就非常方便了。

## 忽略 git 中的文件

使用' git '，我们可以将这个条目添加到应用程序的' .gitignore '文件中，以确保将来忽略任何示例:

```
.clinic
```

或者，我们可以使用全局 gitignore，这样项目就不必为了适应 Clinic.js 而进行更改。
要为 git 配置一个全局忽略文件，并在其中添加' .clinic '，打开命令行并执行:

```bash
git config --global core.excludesfile ~/.gitignore_global
echo '.clinic' >> ~/.gitignore_global
```

---

## 下一个

使用[CLI 参考](./04-reference.md)快速了解 Clinic.js 的来龙去脉.
