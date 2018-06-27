# mkdocs主题material

![Material Design](https://material.io/design/)是Google公司定义的界面风格规范。mkdocs-material主题是第三方制作的符合Material Design的mkdocs文档风格。主要特点有：

* 简洁美观，自适应界面，移动阅读体验很好
* 对markdown内置插件和扩展的显示效果做了很多优化，与其它mkdocs插件配合较好

## 安装

用pipenv安装mkdocs-material包。

```bash
pipenv install mkdocs-material
```

## 使用

在mkdocs.yml里配置启用material主题。

```yaml
theme:
  name: material # Google提倡的material风格
```

## 配色

Material风格规范共定义了19种主题配色和16种鼠标悬停超链接文字颜色，可以通过mkdocs.yml配置：

```yaml
  palette:
    primary: Grey # 官方19中主题配色方案，默认Indigo
    accent: Orange # 官方16种鼠标悬停超链接文字颜色，默认Indigo
```

## 网站图标和标识

请![提前准备](https://www.flaticon.com/)好网站图标和标识图片，把它们放到doc下的特定目录里。然后在mkdocs.yml的主题配置里增加如下配置项。

```yaml
theme:
  favicon: images/favicon.ico # 网站图标
  logo: 'images/logo.svg' # 网站标识图片，显示在界面顶部左侧
```

## 启用导航条

默认情况下顶部导航条是被禁用的。如果你想启用它，可以增添如下配置项：

```yaml
theme:
  feature:
    tabs: true
```
