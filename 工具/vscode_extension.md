# vscode ���ò��

## verilog���

### Verilog-HDL/SystemVerilog/Bluespec SystemVerilog

���������ṩverilog�﷨�������������

### verilog-autoline

ʹ�ÿ�ݼ�`ctrl+k ctrl+/`��Ӵ���ָ��У������ó��ȡ����š���������ʾ���£�

```
//==========================================================
// 
//==========================================================
```

### SystemVerilog and Verilog Formatter

verilog��ʽ�����������Verible�������Զ���  
���ϱ������ã�winϵͳѡ��`win64`
```
 --column_limit=300 --indentation_spaces=8 --assignment_statement_alignment=preserve --named_port_alignment=preserve --port_declarations_alignment=align --module_net_variable_alignment=align
```

### Verible

�ǳ�ǿ���verilog��ʽ����������ܺ�SystemVerilog and Verilog Formatter�ظ������ǻ��error�������һ���������ؾ���

### Verilog Hdl Format

verilog�����ʽ�����������ʶ���źŶ��岢��ת��һ����������δ�����ź�

## c/c++

### Cmake

## ȫ��

### CodeSnap

һ�������ͼ���

### git-commit-plugin

�ṩgit commit��ܣ�ʹ�ÿ�ݼ�`ctrl+shift+p`���������ѡ��`show git commit template`

### marcos

marcos����ͨ������ȫ�ֺ�ʵ���Զ������룬������docker�������޷����صĲ��verilog-autoline������ͨ������marcosʵ��ͬ��Ч��

ʵ��������
1. ����marcos������ȫ������setting.json����ӣ�

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

- ����`"end_verilog_autoline"`Ϊ�Զ����marcos���ƣ�`"cursorLineEnd"`��˼���ڵ�ǰ���֮��  
ע�ⲻ��дmacros������ʾʶ�𲻵���

2. �������������`keyb`ѡ��`Open keyboard Shortcuts`����keybindings.json������Զ����ݼ���

```json
[
    {
        "key": "ctrl+shift+/",
        "command": "macros.end_verilog_autoline"
    }
]
```

3. ����󣬰�`ctrl+shift+/`����ʵ���Զ������롣