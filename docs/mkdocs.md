## 1. mkdocs介绍

MkDocs is a fast, simple and downright gorgeous static site generator that’s geared towards building project documentation. Documentation source files are written in Markdown, and configured with a single YAML configuration file.

MkDocs是一个快速的、简单的、优美的静态站点生成器，主要用于构建项目文档。文档源文件采用Markdown格式，配置文件采用一个YAML格式文件。

## 2. mkdocs安装

**安装mkdocs前需要安装python环境。mkdocs要求python版本为：python 3.5、python 3.6 、python 3.7和python 3.8。**

安装mkdocs非常简单，只需要在控制台运行如下命令即可：

```
pip install mkdocs
```

查看mkdocs是否安装成功，只需要运行如下命令：

```
mkdocs --version
```

如果提示不能运行`mkdocs`命令，简单的解决方法只需要在命令前加上`python -m`，即：

```
python -m mkdocs --version
```

永久的解决方法是将python安装目录下的`Scripts`加入环境变量`Path`中。