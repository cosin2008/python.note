# 扩展和优化Markdown

Markdown基础语法非常简洁，学习成本很低，但是在显示效果和功能上还是稍显不足。我们可以通过配置Markdown插件扩展和优化Markdown的语法及排版展示效果。为了获得最佳的兼容性和页面渲染效果，推荐使用material主题。

## material主题内置的markdown扩展

安装material主题后，就会同时获得很多有用的markdown扩展，可在mkdocs.yml里决定是否启用。

```yaml
markdown_extensions:
  - codehilite(guess_lang=false,linenums=true) # 显示优化：代码高亮
  - toc(permalink=true) # 显示优化：为TOC生成URL链接
  - admonition # 语法扩展：支持用!!!标记的文本框
  - footnotes # 语法扩展：支持用[^1]标记的类似论文引用的数字角标，并提供了页面内跳转
  - meta # 语法扩展：支持页面级别的不被会显示的元数据，可以覆写页面的标题等
```

具体效果和语法可参考每个插件各自的文档：

* [codehilite](https://squidfunk.github.io/mkdocs-material/extensions/codehilite/)
* [admonition](https://squidfunk.github.io/mkdocs-material/extensions/admonition/)
* [footnotes](https://squidfunk.github.io/mkdocs-material/extensions/footnotes/)
* [meta](https://squidfunk.github.io/mkdocs-material/extensions/metadata/)

## pymdown-extensions插件包

[pymdown-extensions](https://facelessuser.github.io/pymdown-extensions/)是可以与material主题很好配合的第三方markdown扩展，提供了大量对markdown的排版优化和功能扩展，包含至少[二十多个](https://facelessuser.github.io/pymdown-extensions/extensions/arithmatex/)有用的markdown插件。

使用前pymdown-extensions需要先在python虚拟环境里安装pymdown-extensions包。

```bash
pipenv install pymdown-extensions
```

安装成功后，可以在mkdocs.yml里决定具体启用哪些pymdown-extensions插件。

```yaml
markdown_extensions:
  - pymdownx.arithmatex # 支持LaTeX数学公式的渲染
  - pymdownx.betterem(smart_enable=all) # 优化对加粗斜体等效果的体验
  - pymdownx.caret # 支持下划线
  - pymdownx.critic # 支持插入、删除、替换等文档修订类符号
  - pymdownx.details # 支持一个可折叠或展开的文本框用于描述细节内容
  - pymdownx.emoji(emoji_generator=!!python/name:pymdownx.emoji.to_png) # 支持表情符号转义
  - pymdownx.inlinehilite # 支持嵌入在大段文本里的代码高亮显示
  - pymdownx.magiclink # 自动为Markdown里的地址增加可供链接的锚文本
  - pymdownx.mark # 支持高亮背景
  - pymdownx.smartsymbols # 支持类似©、™、®、¼之类的特殊符号
  - pymdownx.superfences # 支持用TAB分页切换代码块等
  - pymdownx.tasklist # 支持TODO列表类的任务状态显示
  - pymdownx.tilde # 支持数字下标（化学分子式）和删节线

extra_javascript:
  - https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-MML-AM_CHTML # 为了让arithmatex支持数学公式的额外JS  
```

具体效果可以参考[pymdownx](https://squidfunk.github.io/mkdocs-material/extensions/pymdown/)的文档。
