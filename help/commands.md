# 命令栏

通过快捷键 Ctrl-e 来启用命令栏。这是一个单行的缓冲区，意味着它支持所有来自普通缓冲区的键盘绑定（比如鼠标和选中）。

当你运行一个命令时，你可以使用额外的语法，micro 会在运行命令前展开它。如果你想要使用带空格的参数，请把它放在引号中。命令栏解析器使用的参数解析规则与 `bin/sh` 的规则（单引号，双引号，转义）相同。命令栏不会搜索环境变量。

# 命令

Micro 提供了以下命令以供使用，只需使用命令行 `Ctrl-e` 然后输入即可。参数在本文中使用了单引号，但在 micro 中输入命令时不需要输入这些引号。

* `bind 'key' 'action'` : 将快捷键绑定到操作。请查看 `keybindings` 文档来获取更多有关键位绑定的信息。这个命令会修改 `bindings.json` 文件，并覆盖已绑定的键位。

* `help 'topic'?` : 打开相应的帮助主题。如果没有提供主题会打开默认的帮助页面。

* `save 'filename'?` : 保存当前缓冲区。如果提供了 filename ,它将另存为 filename。

* `quit` : 

* `goto 'line'` :

* `replace 'search' 'value' 'flags'?` :

* `replaceall 'search' 'value'` :

* `set 'option' 'value'` :

* `setlocal 'option' 'value'` :

* `show 'option'` :

* `run 'sh-command'` :

* `vsplit 'filename'` :

* `hsplit 'filename'` : 

* `tab 'filename'` :

* `tabmove '[-+]?n'` :

* `tabswitch 'tab'` :

* `textfilter 'sh-command'` :

* `log` : 

* `plugin list` : 

* `plugin install 'pl'` :

* `plugin remove 'pl'` :

* `plugin update 'pl'` :

* `plugin search 'pl'` : 

* `plugin available` : 

* `reload` :

* `cd 'path'` :

* `pwd` : 

* `open 'filename'` :

* `reset 'option'` : 

* `retab` : 

* `raw` : 

* `showkey` : 

* `term exec?` :

---

以下命令由默认加载的插件提供：

* `lint` : 
* `comment` : 

