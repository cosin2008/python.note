# Markdown科学写作

Markdown本身对科学写作的支持不强，但搭配一些插件也可以满足日常所需，比如嵌入LaTeX数学公式和化学分子式等。

## 引文与出处

搭配footnotes插件，可以扩展markdown，不但支持论文里常见的数字角标引文，还支持页面内引文和出处间互相跳转，非常方便。

语法 | 功能
:-- | :--
\[^n\] | 表示第n个引用文献

下面是一个实际效果，注意引文内容一般会被自动聚集到页面结尾。

这里是引文1[^1]，这里是引文2[^1]，这里是引文3[^2]。

[^1]: 这里是出处1

[^2]: 这里是出处2

## 注解

在admonition和pymdownx.details插件的配合下，可以提供比>方式更为丰富的注解内容。

| 语法／示例 | 说明
| :-- | :--
| !!! | 非折叠注解，需要搭配admonition插件
| ??? | 折叠注解，需要搭配pymdownx.details插件
| \{\>>sth<<\} | 灰色背景高亮的内嵌注解

!!! 这是一个非折叠注解

    这是非折叠注解的内容，比较适合作为注意事项等使用。

??? 这是一个折叠注解

    这是折叠注解的内容，比较适合仅供少数读者需要阅读的细节。

这是一个灰色背景高亮的{>>内嵌注解<<}的效果。

## 上标、下标和化学分子式

配合pymdownx.tilde插件，我们可以很方便的显示化学分子式或数字下标。

语法 | 效果
:-- | :--
\~n~ | CH~3~CH~2~OH
\^n^ | X^3^和Y^2^
\~n~ | CH~3~CH~2~OH

## 数学公式

搭配pymdownx.arithmatex插件，可以让Markdown支持LaTeX数学公式。除了在mkdocs.yml里启用插件外，还需要设置额外的javascript。

### 插件配置

```yaml
markdown_extensions:
  - pymdownx.arithmatex # 支持LaTeX数学公式的渲染
extra_javascript:
  # MathJax For Latex配置，支持用LaTex、Math ML或ASCII Math语法来书写数学公式
  - https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-MML-AM_CHTML
```

### 公式块和内嵌公式

语法 | 功能
:-- | :--
\$$ | 标记公式块开始或结束，单独一行

!!! 公式块

    以下是公式块的效果：
    $$
    \frac{n!}{k!(n-k)!} = \binom{n}{k}
    $$

### 公式块和内嵌公式

语法 | 功能
:-- | :--
\$...\$ | 标记内嵌公式开始或结束

!!! 内嵌公式

    以下是文字内嵌公式的效果：$p(x|y) = \frac{p(y|x)p(x)}{p(y)}$

    还可以在表格内嵌公式：

    语法 | 功能
    :-- | :--
    \$...\$ | $p(x\|y) = \frac{p(y\|x)p(x)}{p(y)}$
    \$...\$ | $\frac{n!}{k!(n-k)!} = \binom{n}{k}$

### MathJax公式语法

实际上[MathJax](https://www.mathjax.org/)支持的书写数学公式的语法包括三种：[LaTex](https://www.latex-project.org/)、MathML和AsciiMath。但pymdownx.arithmatex插件搭配实际使用的仍然只有LaTex。所以，之前的示例全都是用LaTex格式书写的。

## 文档修订符号

|语法 | 功能与效果
| :-- | :--
| \^\^sth\^\^ | ^^文字下划线^^
| \~\~sth\~\~ | ~~文字中横线~~
| \{\++sth++\} | {++文字下划线,绿色背景高亮++}
| \{\--sth--\} | {--文字中横线,红色背景高亮--}
| \{\~\~false\~\>true\~\~\} | {~~文字下划线接文字横线,绿接红背景高亮~~}
| \=\=sth\=\= | ==黄色背景高亮==
| \{\=\=sth\=\=\} | {==黄色背景高亮==}
