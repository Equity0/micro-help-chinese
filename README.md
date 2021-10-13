<img alt="micro logo" src="https://github.com/zyedidia/micro/blob/master/assets/micro-logo.svg" width="500px"/>

[![Build Status](https://travis-ci.org/zyedidia/micro.svg?branch=master)](https://travis-ci.org/zyedidia/micro)
[![Go Report Card](https://goreportcard.com/badge/github.com/zyedidia/micro)](https://goreportcard.com/report/github.com/zyedidia/micro)
[![Release](https://img.shields.io/github/release/zyedidia/micro.svg?label=Release)](https://github.com/zyedidia/micro/releases)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/zyedidia/micro/blob/master/LICENSE)
[![Join the chat at https://gitter.im/zyedidia/micro](https://badges.gitter.im/zyedidia/micro.svg)](https://gitter.im/zyedidia/micro?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Snap Status](https://snapcraft.io/micro/badge.svg)](https://snapcraft.io/micro)

**micro** 是一个基于终端的文本编辑器，它的目标是易于使用和直观，同时也采取了现代终端的优点。它是一个单一的、自给自足的、静态的，没有任何依赖性的二进制文件；现在就来下载使用吧。

人如其名，micro 旨在通过易于安装和使用的特点，从而成为 nano 编辑器的继承者。
它致力于成为那些喜欢在终端中工作或经常使用 SSH 编辑文件的人的全能编辑器。

下面是使用 micro 编辑其自身源代码的图片。

![Screenshot](https://github.com/zyedidia/micro/blob/master/assets/micro-solarized.png)

要查看 micro 更多的屏幕截图，或更多的颜色方案，请看 [这里](https://micro-editor.github.io)。

你也可以查看 Micro 的网站：https://micro-editor.github.io

## 目录

- [特点](#特点)
- [安装](#安装)
  - [预编译的二进制文件](#预编译的二进制文件)
  - [软件包管理器](#软件包管理器)
  - [从源代码构建](#从源代码构建)
  - [全静态二进制文件](#全静态二进制文件)
  - [macOS 终端](#macOS终端)
  - [支持 Linux 剪贴板](#支持Linux剪贴板)
  - [颜色和语法高亮](#颜色和语法高亮)
  - [Cygwin, Mingw, Plan9](#cygwin-mingw-plan9)
- [用法](#用法)
- [文档和帮助](#文档和帮助)
- [贡献](#贡献)

- - -

## 特点

- 易于安装和使用。
- 无依赖性或其他外部文件 - 只需要你下载页面下方的软件。
- 多个游标。
- 常见快捷键 (<kbd>Ctrl-s</kbd>, <kbd>Ctrl-c</kbd>, <kbd>Ctrl-v</kbd>, <kbd>Ctrl-z</kbd>, ...)。
  - 也可以自定义快捷键。
- 合理的默认设置。
  - 开箱即用，无需过多配置（配置起来也很容易）。
- 支持拆分窗口和标签。
- 类 nano 菜单帮助你更好地记住快捷键。
- 惊艳的鼠标支持。
  - 可以用鼠标拖动选中文本，双击选中文字，三击选中行。
- 跨平台（在所有可以运行 Go 的平台）。
  - 注意，虽然Windows支持Mingw/Cygwin，但不支持（见下文）。
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
- 常见的编辑器功能，如撤销/重做，显示行数，Unicode 支持，软换行, ...

