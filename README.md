## 安装中文包

因为 micro 的帮助文档是运行时加载的，所以很简单就可以将 micro 中的帮助文档替换为中文：

```sh
git clone https://github.com/yi0322/micro-help-chinese.git && \
cd ./micro-help-chinese && mv ./help ~/.config/micro/
```

Gitee
```sh
git clone https://gitee.com/dizyi/micro-help-chinese.git && \
cd ./micro-help-chinese && mv ./help ~/.config/micro/
```

------

[<img alt="micro logo" src="https://github.com/zyedidia/micro/blob/master/assets/micro-logo.svg" width="500px"/>](https://micro-editor.github.io)

[![Build Status](https://travis-ci.org/zyedidia/micro.svg?branch=master)](https://travis-ci.org/zyedidia/micro)
[![Go Report Card](https://goreportcard.com/badge/github.com/zyedidia/micro)](https://goreportcard.com/report/github.com/zyedidia/micro)
[![Release](https://img.shields.io/github/release/zyedidia/micro.svg?label=Release)](https://github.com/zyedidia/micro/releases)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/zyedidia/micro/blob/master/LICENSE)
[![Join the chat at https://gitter.im/zyedidia/micro](https://badges.gitter.im/zyedidia/micro.svg)](https://gitter.im/zyedidia/micro?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Snap Status](https://snapcraft.io/micro/badge.svg)](https://snapcraft.io/micro)

**micro** 是一个基于终端的文本编辑器，它的目标是易于使用和直观，同时也采取了现代终端的优点。它是一个单一的、自给自足的、静态的，没有任何依赖性的二进制文件；现在就来下载使用吧。

顾名思义，micro 旨在通过易于安装和使用的特点，从而成为 nano 编辑器的继承者。
它致力于成为那些喜欢在终端中工作或经常使用 SSH 编辑文件之人的全能编辑器。

下面是使用 micro 编辑其自身源代码的图片。

![Screenshot](https://github.com/zyedidia/micro/blob/master/assets/micro-solarized.png)

要查看 micro 更多的屏幕截图，或更多的颜色方案，请看 [这里](https://micro-editor.github.io)。

你也可以查看 Micro 的网站：https://micro-editor.github.io

## 目录

- [特点](#特点)
- [安装](#安装)
  - [预编译二进制文件](#预编译二进制文件)
  - [软件包管理器](#软件包管理器)
  - [从源代码构建](#从源代码构建)
  - [全静态二进制文件](#全静态二进制文件)
  - [macOS 终端](#macOS-终端)
  - [Linux 剪贴板支持](#Linux-剪贴板支持)
  - [颜色方案和语法高亮](#颜色方案和语法高亮)
  - [Cygwin, Mingw, Plan9](#cygwin-mingw-plan9)
- [用法](#用法)
- [文档和帮助](#文档和帮助)
- [贡献](#贡献)

- - -

## 特点

- 易于安装和使用。
- 无依赖性或其他外部文件 - 只需要你下载页面下方的软件。
- 多个游标。
- 常见快捷键 ( <kbd>Ctrl-s</kbd>, <kbd>Ctrl-c</kbd>, <kbd>Ctrl-v</kbd>, <kbd>Ctrl-z</kbd> , ...)。
  - 也可以自定义快捷键。
- 合理的默认设置。
  - 开箱即用，无需过多配置（配置起来也很容易）。
- 支持拆分窗口和标签。
- 类 nano 菜单帮助你更好地记住快捷键。
- 惊艳的鼠标支持。
  - 可以用鼠标拖动选中文本，双击选中文字，三击选中行。
- 跨平台（在所有可以运行 Go 的平台）。
  - 注意，虽然 Windows 支持 Mingw/Cygwin，但不支持（见下文）。
- 插件系统（插件采用 Lua 编写）。
  - micro 拥有内置插件管理器来帮助你自动安装，卸载和更新插件。
- 内置 diff gutter 。
- 简单易用的自动补全。
- 支持连续的撤销操作。
- 自动提示和错误提示。
- 超过 [130 种语言](https://github.com/zyedidia/micro/tree/master/runtime/syntax) 的语法高亮
- 颜色方案支持
  - 默认情况下，micro 支持 16， 256，和 true color 主题。
- 支持 True color （将 `MICRO_TRUECOLOR` 环境变量设置为 1 来开启它）。
- 用系统剪切板来复制和粘贴。
- 小而简单。
- 易于配置。
- 支持宏。
- 常见的编辑器功能，如撤销/重做，显示行数，Unicode 支持，自动换行, ...

## 安装

要安装 micro，你可以直接下载预构建二进制文件，或从源代码自己编译。

如果你想了解更多关于如何安装 micro 的方式，请看这个 [wiki 页面](https://github.com/yi0322/micro-help-chinese/wiki/%E5%AE%89%E8%A3%85-Micro)

安装完成后使用 `micro -version` 来获取版本信息。只有你采用预编制二进制文件、Homebrew 或 snap 安装，才能保证你安装的是最新的稳定版本。

在 [assets/packaging](https://github.com/zyedidia/micro/tree/master/assets/packaging) 目录中可以找到一个 `.desktop` 文件和一个 `man page`。

### 预编译二进制文件

预编译二进制文件随 [release](https://github.com/zyedidia/micro/releases) 一起发布。

要卸载 micro ，只需要删除二进制文件，以及 `~/.config/micro` 的配置目录。

#### 快速安装脚本

```bash
curl https://getmic.ro | bash
```

该脚本将 micro 二进制文件安装到当前目录中。你可以把该文件移动到你选择的目录（比如 `sudo mv micro /usr/bin`）。更多信息可查看 [Github repository](https://github.com/benweissmann/getmic.ro)

#### Eget

安装 [Eget](https://github.com/zyedidia/eget) 后，你可以很容易得到一个预编译二进制文件：

```sh
eget zyedidia/micro
```

使用 `--tag VERSION` 来下载一个特定版本。

```
eget --tag nightly zyedidia/micro # download the nightly version (compiled every day at midnight UTC)
eget --tag v2.0.8 zyedidia/micro  # download version 2.0.8 rather than the latest release
```

你可以给 `eget` 命令添加 `--to /usr/local/bin` 选项来安装 `micro`，或者在安装后手动将 `micro` 移动到你的 `$PATH` 里。

参考 [Eget](https://github.com/zyedidia/eget) 获取更多信息。

### 软件包管理器

你在 Mac 上可以通过 Homebrew 安装 micro ：

```
brew install micro --classic
```

**Linux 用户注意：** 为了与本机系统剪切板配合，必须安装 `xclip` 或 `xsel` 。详情请查看页面下方的 [Linux 剪贴板支持](#Linux-剪贴板支持)

Micro 也可以通过 Linux 上的软件包管理器比如 dnf , AUR , Nix ,以及其他操作系统的包管理器。但这些软件包不保证是最新版。

<!-- * `apt install micro` ( Ubuntu 20.04 'focal' 和 Debian `unstable | testing | buster-backports` )。目前这个包(2.0.1-1) 已经过期并且在调试模式中有一个已知错误。-->

* Liunx: 在特定发行版的软件包管理可用。
    * `dnf install micro` (Fedora)
    * `pacman -S micro` (Arch Linux)
    * `eopkg install micro` (Solus)
    * 查看 [wiki](https://github.com/yi0322/micro-help-chinese/wiki/%E5%AE%89%E8%A3%85-Micro#crux) 以获取关于 CRUX, Termux 的更多信息。
* Windows: [Chocolatey](https://chocolatey.org) 和 [Scoop](https://github.com/lukesampson/scoop).
    * `choco install micro`
    * `scoop install micro`
* openBSD: 可在 ports 树中找到，也可作为二进制包来使用。
    * `pkg_add -v micro`
* NetBSD ， macOS ， Linux ， Illumos 等，使用[pkgsrc](http://www.pkgsrc.org/)-current。
    * `pkg_add micro`
* macOS 使用 [MacPorts](https://www.macports.org):
    * `sudo port install micro`

### 从源代码构建

如果你的操作系统没有二进制包版本，但可以运行 Go ，你可以自己从源码构建。

确保你使用的 Go 版本号为 1.11 或更高，并且 Go 模块已经启动。

```sh
git clone https://github.com/zyedidia/micro
cd micro
make build
sudo mv micro /usr/local/bin # optional
```

编译好的二进制文件将被放置在当前目录下，并可以移动到你喜欢的任何地方（例如 `/usr/local/bin`）。

使用 `make install` 将安装二进制文件到 `$GOPATH/bin` 或 `$GOBIN` 。

你可以直接用 `go get` 来安装（`go get github.com/zyedidia/micro/cmd/micro`），但这并不被推荐，因为它在构建 micro 时没有版本信息（插件管理器需要用到此信息），而且不能禁用调试模式。

### 全静态二进制文件

默认情况下，micro 二进制文件将与核心系统库进行动态链接（为了安全和可移植性，通常推荐这样做）。然而，有一个完全静态的预构建二进制文件，以 `linux-static.tar.gz` 的形式提供给 amd64，
要从源码构建一个全静态二进制文件，运行

```sh
CGO_ENABLED=0 make build
```

### macOS 终端

如果你使用的是 macOS ，你应该考虑使用 [iTerm2](http://iterm2.com/) 而不是默认终端（ Terminal.app ）。
iTerm2 终端对鼠标的支持要好得多，而且对按键事件的处理也更好。为了获得最佳的键盘绑定行为，请在 `Preferences->Profiles->Keys->Presets...` 中选择 `xterm defaults` ，并在同一菜单中选择 `Esc+` 作为 `Left Option Key` 。最新版本还支持真彩色。

如果你仍然坚持使用默认的Mac终端，一定确保在 `Preferences->Profiles->Keyboard` 中设置 `Use Option key as Meta key`，将 <kbd>option</kbd> 作为 <kbd>alt</kbd> 。

### Linux 剪贴板支持

在 Linux 上，剪贴板支持需要：
- 在 X11 上，安装 `xclip` 或 `xsel` (对 Ubuntu : `sudo apt install xclip`)
- 在 Wayland，安装 `wl-clipboard`

如果你没有安装这些软件， micro 将会使用内部剪贴板来复制和粘贴，但它不会与外部程序一起工作。

### 颜色方案和语法高亮

如果你打开 micro 并发现语法高亮不起作用，那大概是因为你在使用的终端不支持 256 颜色模式。
请尝试改变颜色方案为 `simple` ，请打开 micro 后按 <kbd>Ctrl-e</kbd> 然后输入 `set colorscheme simple`。

如果你使用的是 Ubuntu 默认终端，请确保你的 `TERM` 变量设置为 `xterm-256color` 以启用 256 色支持。

很多窗口终端不支持超过16色，这意味着 micro 的默认颜色方案看起来不会那么好看。你可以将颜色方案设置为 `simple`，或者下载和配置一个更好的终端模拟器来替代默认终端。

### Cygwin, Mingw, Plan9

不幸的是，Cygwin 、 Mingw 和 Plan9 都没有得到官方支持。在 Cygwin和 Mingw 中，使用 `winpty` 工具运行时， micro 通常可以工作。

```
winpty micro.exe ...
```

Micro 使用了不起的 [tcell 库](https://github.com/gdamore/tcell) ，但这这意味着 micro 被限制在 tcell 支持的平台上。因此， micro 不支持 Plan9 和 Cygwin （尽管这在将来可能会改变）。Micro 也不支持 NaCl （反正已经被废弃了）。

## 用法

一旦你拥有了编辑器，你可以通过运行 `micro path/to/file.txt` 打开文件，或运行 `micro` 打开一个空缓冲区。

micro 同样支持从 `stdin` 创建缓冲区。

```sh
ifconfig | micro
```

你可以用方向键和鼠标来移动光标。

同样可以使用鼠标来操作文本。点击和拖动鼠标将选中文本。你也可以双击鼠标选中词和三击鼠标选中一行。

## 文档和帮助

micro 拥有内置帮助系统，你可以通过按键 <kbd>Ctrl-e</kbd> 然后输入 `help` 来打开它，此外你也可以在这里浏览帮助文件：
- [help](https://github.com/yi0322/micro-help-chinese/blob/main/help/help.md)
- [keybindings](https://github.com/zyedidia/micro/tree/master/runtime/help/keybindings.md)
- [commands](https://github.com/zyedidia/micro/tree/master/runtime/help/commands.md)
- [colors](https://github.com/zyedidia/micro/tree/master/runtime/help/colors.md)
- [options](https://github.com/zyedidia/micro/tree/master/runtime/help/options.md)
- [plugins](https://github.com/zyedidia/micro/tree/master/runtime/help/plugins.md)

我还建议阅读[教程](https://github.com/yi0322/micro-help-chinese/blob/main/help/tutorial.md)，这里简要介绍了 micro 提供的更加强大的配置功能。

## 贡献

如果你发现任何 bugs，请告诉我！我也很乐意接受任何人的 PR 。

你可以使用 [GitHub issue tracker](https://github.com/zyedidia/micro/issues) 来报告 bugs， 提出问题，或建议新的功能。

如果想在一个更非正式的环境中讨论此编辑器，你可以加入 [Gitter chat](https://gitter.im/zyedidia/micro)。

有时候我没有回应，我很抱歉！如果发生这种情况的话请与我联系。
