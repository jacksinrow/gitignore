# gitignore

## `.gitignore` 文件是什么？

`.gitignore` 文件是用来管理当前 Git 仓库中哪些文件或者目录不进行版本管理。平时我们用 `SourceTree` 可视化 Git 管理工具的时候，还需要注意全局的 `.gitignore` 文件，`macOS` 底下全局 `.gitignore` 文件目录在：`SourceTree -> Preferences -> Git -> Global Ignore List` 里面，注意确保这个全局 `.gitignore` 文件没有问题。默认的内容如下：

```
*~
.DS_Store
```

以上主要是针对 `macOS` 系统底下需要过滤掉的文件类型。

## Android/iOS 项目应该如何配置 `.gitignore` 文件？

Android/iOS 项目的 `.gitignore` 文件的配置主要和 IDE 和开发语言相关的文件过滤。

Android：Android Studio 相关内容过滤，开发语言：Java/Kotlin 等相关过滤。

iOS：Xcode 相关内容过滤，开发语言：Objective-C/Swift 等相关过滤。

以上具体内容请参见相关文件。

## 中途 `.gitignore` 文件变更该如何处理？

中途 `.gitignore` 文件变更有两种情况，一种是中途加入内容到 `.gitignore` 文件，另外一种是中途从 `.gitignore` 文件中移除内容。

中途加入内容到 `.gitignore` 文件，的处理方式如下：

```
git add [uncommitted changes you want to keep] && git commit
git rm -r --cached .
git add .
git commit -m "fixed untracked files"
```

中途从 `.gitignore` 文件移除内容，如果移除之后，相关的内容能够直接显示被 track 之后，可以通过 `SourceTree` 第三方 Git 管理工具来看，如果相关的内容没有能够显示被 track，就采用以下命令使之生效。

```
git add -f [files you want to track again]
git commit -m "Refresh removing files from .gitignore file."

// For example, if you want the .java type file to be tracked again,
// The command should be:
//     git add -f *.java
```

## `.gitignore` 文件如何配置？

请参考官方文档：[https://git-scm.com/docs/gitignore](https://git-scm.com/docs/gitignore)









