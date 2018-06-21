# mkdocs入门

!本文主要面向有基本计算机使用技能、至少学习过一种编程语言接受过编程知识普及教育且有一定英文阅读能力的读者。

## 前提条件

- [Python](https://www.python.org/downloads/)：推荐安装Python 3.6以上版本（Python 2.7已经快要退役了）
- [pipenv](https://docs.pipenv.org/)：比较优秀的Python虚拟环境管理工具
- [VSCode](https://code.visualstudio.com/Download)：微软出品的免费、跨平台、程序员友好、功能强大的文本编辑器
- [ms-python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)：微软官方出品的VSCode插件，用于支持Python基本开发调试环境
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)：一款优秀的VSCode插件，用于Markdown文档的编辑和预览
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)：一款优秀的VSCode插件，用于自动检查markdown语法错误并在编辑的同时给予提示
- [Git](https://git-scm.com/downloads)：优秀的文档版本管理工具，程序员的标配，也是将文档发布到Github 上所必须的工具
- [Github账号](https://github.com)：Github是最著名的免费开源项目的代码仓库服务商，如果你想把静态网站的内容发布到Github上，请预先申请一个Github账号

## 安装mkdocs

创建一个工作目录，新建一个与之配套python虚拟环境。如工作目录和配套的Python虚拟环境已准备好，可略过这一步。

```bash
cd your-workspace
pipenv install
```

激活Python虚拟环境，安装mkdocs包

```bash
pipenv shell
pipenv install mkdocs
```

后面所有步骤命令，都默认假定你已经激活Python虚拟环境。

## 新建mkdocs项目

新建一个mkdocs项目。

```bash
mkdocs new your-project
```

如果新建成功，会在当前目录下新创建一个名为your-project的子目录。进入这个子目录，可以先初步认识一下项目目录的基本结构：

    ```bash
    cd your-project
    tree /f
    ```

    mkdocs.yml    # mkdocs生成文档网站时所用的配置文件
    docs/
        index.md  # mkdocs生成的文档网站的主页
        ...       # 网站的其它页面、图片、文件等

- mkdocs.yaml：位于根目录，用于定义，包括具体的页面。
- index.md：位于docs子目录下，是一个由mkdocs生成的默认项目主页。未来，可以在docs子目录下新建更多的makrdown文档。

后面所有步骤的命令，都默认当前目录为新创建出来的文档项目目录，同时也激活了Python虚拟环境。

## 预览新建的网站

运行下面的命令在本地预览新创建好的网站。

```bash
cd your-project
mkdocs serve
```

打开浏览器，访问<http://127.0.0.1:8000/>，你就可以看到新创建出来的网站的样子。

## 编辑文档

现在，你可以自由编辑docs子目录下的index.md（如不熟悉markdown语法，可暂当做普通文本文件）。每次保存文件时，如果在预览状态，浏览器页面一般会自动同步更新，向你展示出最新修改的结果。你也可以在docs子目录下创建一个新的子目录或新的markdown文件来表示一个新页面和文档层级结构。这些修改都会及时的即使反映在浏览器的预览页面里。

## 生成静态网站

运行下面的命令在本地计算机上生成静态网站的内容。如果运行命令时加上--clean的参数，可以同时清理掉上一次build中生成的过时文件和垃圾。

```bash
cd your-project
mkdocs build
mkdocs build --clean
tree site
```

如果build成功，你将在根目录下发现一个名为site的子目录，在里面保存着被mkdocs生成的网站所需的全部静态内容。现在只要把site文件夹里的内容上传到任何web服务器上，就可以把静态网站发布在网络上。

## 发布到Github Pages

mkdocs为Github Pages发布提供了很便利的集成工具。Github作为程序员们所熟知的世界上最大的免费、开源代码仓库，也同时为静态建站提供了优质的免费服务[Github Pages](https://pages.github.com/)。

在Github网站上创建一个全新的空项目仓库，然后执行下面的命令将本地项目目录初始化为git项目，并
echo "# python.note" >> README.md
git init
git remote add origin https://github.com/your-account/your-github-repo.git
git push -u origin master

git add README.md
git commit -m "first commit"

git remote add origin https://github.com/cosin2008/python.note.git
git push -u origin master

目前，Github Pages对静态建站的[使用限制](https://help.github.com/articles/what-is-github-pages/)相当宽松。

- 代码仓库容量和静态网站大小都不超过1G
- 网站带宽月流量不超过100G
- 每小时网站内容发布不超过10次。


