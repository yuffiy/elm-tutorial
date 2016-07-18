# Hello World

## Elm 安装

可以在 http://elm-lang.org/install 下载到适合你操作系统的安装包。

## 我们的第一个 Elm 程序

让我们开始写我们的第一个 Elm 程序。首先创建一个文件夹，在这个文件夹下运行下面的命令：

```bash
elm package install elm-lang/html
```

这样会安装一个 _html_ 模块。然后添加一个 `Hello.elm` 的文件，并填入下面的代码：

```elm
module Hello exposing (..)

import Html exposing (text)


main =
    text "Hello"
```

接着键入下面的命令：

```bash
elm reactor
```

这时控制台会显示：

```
elm reactor 0.17.0
Listening on http://0.0.0.0:8000/
```

在浏览器中打开 `http://0.0.0.0:8000/`，单击 `Hello.elm` 就会看到 `Hello`。

现在让我们来看一下代码：

### 导入

在 Elm 中，你需要明确的导入使用到的__模块__。这里我们需要用到 __Html__ 模块。

这个模块包含了很多关于 html 的函数。这里我们用到了 `.text`，所以需要使用 `exposing` 来从当前模块中导入这个函数。

### main 函数

Elm 程序开始于一个叫做 `main`的函数。`main` 函数返回一个 element 并将他画在页面上。在这里我们返回了一个 Html 元素（由 `text` 函数创建）。

### elm reactor

Elm __reactor__ 会创建一个 server 并编译 Elm 源码。__reactor__ 可以很方便的用于开发程序而不用担心繁琐的构建过程。然而，__reactor__ 能做的事情有限，最终我们还是需要切换到项目的构建上来。
