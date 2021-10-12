# 教程

这是对 micro 的配置系统的简要介绍，它将给出一些简单示例展示如何调整设置、重新绑定快捷键
和使用 `init.lua` 根据自己的喜好配置 micro 。

希望对你有所帮助。

有关默认快捷键的使用和解释，请参阅 `> help defaultkeys`。

### 设置

在 micro 中，你的配置文件位于 `~/.config/micro/settings.json` 文件中。
这是您第一次运行 micro 时创建的。这是一个 json 文件，其中包含所有设置及其值。
要更改选项，您可以更改 `settings.json` 文件中的值，或者您可以在使用 micro 时直接输入。 

按 Ctrl-e 进入命令模式，然后输入 `set option value` （此后我将使用 `> set option value` 来表示按 Ctrl-e）。
改变会立即生效，也会保存到`settings.json`文件中，这样即使在你关闭 micro 后设置也会保持不变。

你也可以在设置局部配置，这意味着该设置只在当前缓冲区中可用。
例如，如果你有两个拆分窗口，你输入 `> setlocal tabsize 2` ，制表符大小将只在当前两个窗口中有用。micro 不会
将这个配置变化保存到 `settings.json` 文件。

然而，你仍然可以在 `settings.json` 文件中设置局部配置。例如，如果你希望 `tabsize` 只在 Ruby 文件中为 2，
其他情况下为 4，你可以在 `settings.json` 中设置如下。

```json
{
    "*.rb"。{
        "tabsize": 2
    },
    "tabsize": 4
}
```

Micro 将只在与 `*.rb` 相匹配的文件中把 `tabsize` 设置为 2。

如果你想了解更多配置项，请看 `options` 主题 (`> help options`)。

### 快捷键绑定

修改快捷键的方式与修改设置的方式基本相同。
你可以通过 `~/.config/micro/bindings.json` 文件来修改它们。

例如，如果你想把 `Ctrl-r` 绑定到撤销，你可以把以下内容放在 `bindings.json` 中。

```json
{
    "Ctrl-r": "Redo"
}
```

非常简单。

你也可以在 micro 中通过使用 `> bind key action` 命令来绑定按键。
但是你用这个命令做的绑定将不会被保存到 `bindings.json` 文件。

### 使用 Lua 配置

如果 json 文件无法满足你的需求，你可以使用 `init.lua` 文件创建更强大的功能。
在 `~/.config/micro` 中创建它。这个文件是一个lua文件，在 micro 启动时运行的 lua 文件，
本质上是一个单文件的插件。该插件的名字是 `initlua` 。

下面这个例子将告诉你如何使用 `init.lua` 文件，
通过创建一个功能并绑定到 `Ctrl-r`，它的功能是在当前文件中执行 bash 命令 `go run`，
鉴于当前文件是一个Go文件。

你可以通过在 `init.lua` 中添加以下内容来实现。

```lua
local config = import("micro/config")
local shell = import("micro/shell")

function init()
    -- true means overwrite any existing binding to Ctrl-r
    -- this will modify the bindings.json file
    config.TryBindKey("Ctrl-r", "lua:initlua.gorun", true)
end

function gorun(bp)
    local buf = bp.Buf
    if buf:FileType() == "go" then
        -- the true means run in the foreground
        -- the false means send output to stdout (instead of returning it)
        shell.RunInteractiveShell("go run " .. buf.Path, true, false)
    end
end
```

另外，你可以去掉 `TryBindKey` 所在行，把这一行放在 `bindings.json` 文件中。

```json
{
    "Ctrl-r": "lua:initlua.gorun"
}
```

关于插件和 micro 使用的 lua 系统的更多信息，请参阅 `plugins` 帮助主题（ `> help plugins` ）。
