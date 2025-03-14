# vscode 常用插件

## verilog相关

### Verilog-HDL/SystemVerilog/Bluespec SystemVerilog

经典插件，提供verilog语法纠错，代码高亮等

### verilog-autoline

使用快捷键`ctrl+k ctrl+/`添加代码分隔行，可配置长度、符号、行数，演示如下：

```
//==========================================================
// 
//==========================================================
```

### SystemVerilog and Verilog Formatter

verilog格式化插件，基于Verible，可以自定义  
附上本人设置，win系统选择`win64`
```
 --column_limit=300 --indentation_spaces=8 --assignment_statement_alignment=preserve --named_port_alignment=preserve --port_declarations_alignment=align --module_net_variable_alignment=align
```

### Verible

非常强大的verilog格式化插件，功能和SystemVerilog and Verilog Formatter重复，但是会把error标出来，一般用来本地纠错

### Verilog Hdl Format

verilog代码格式化插件，可以识别信号定义并跳转，一般用来查找未定义信号

## c/c++

### Cmake

## 全局

### CodeSnap

一个代码截图插件

### git-commit-plugin

提供git commit框架，使用快捷键`ctrl+shift+p`打开命令面板选择`show git commit template`

### marcos

marcos可以通过设置全局宏实现自定义输入，例如在docker环境里无法下载的插件verilog-autoline，可以通过设置marcos实现同样效果

实例操作：
1. 下载marcos插件后打开全局设置setting.json，添加：

```json
"macros.list": {
    "end_verilog_autoline": [
        "cursorLineEnd",
            {
            "command": "type",
            "args": {
                "text": "//=============================================================================="
            }
        },
    ]
}
```

- 其中`"end_verilog_autoline"`为自定义的marcos名称，`"cursorLineEnd"`意思是在当前光标之后。  
注意不能写macros，会提示识别不到。

2. 在命令面板输入`keyb`选择`Open keyboard Shortcuts`，打开keybindings.json，添加自定义快捷键：

```json
[
    {
        "key": "ctrl+shift+/",
        "command": "macros.end_verilog_autoline"
    }
]
```

3. 保存后，按`ctrl+shift+/`即可实现自定义输入。