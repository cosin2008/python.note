# Markdown嵌入代码

Markdown提供了嵌入代码的支持，在插件的支持下，可以实现语法高亮等多种形式。

## 代码块

| 语法／示例 | 用途 | 效果
| :-- | :-- | :--
| \`\`\`py3 | 标记代码块开始 |
| import tensorflow as tf | 代码块（有插件配合可语法高亮显示）
| \`\`\` | 标记代码块结束 |

!!! 高亮代码块显示效果

    > 有插件codehilite支持，可以显示行号和语法高亮

    ```py3
    import tensorflow as tf
    import numpy as np

    def hello(name):
      print('hello' % name)
    ```

## 内嵌代码

| 语法／示例 | 用途 | 效果
| :-- | :-- | :--
| \`some code\` | 文本行内嵌代码 |
| \`!#py3 some code\` | 文本行内嵌代码 | 代码以!#py3 开头可配合插件内嵌高亮显示

!!! 行内嵌入代码显示效果

    这段代码`import tensorflow as tf`是内嵌代码。

    > 有pymdownx.inlinehilite插件配合，可以实现内嵌高亮语法提示。

    这段代码`#!py3 import tensorflow as tf`是内嵌代码。

## 代码块分页

  配合pymdownx.superfences插件可以实现代码块分页效果

| TAB | 代码块 |

!!! 多语言代码块切换效果

    需安装和启用插件。

    ```py3 TAB=
    import tensorflow as tf
    import numpy as np

    def hello(name):
      print('hello' % name)
    ```
