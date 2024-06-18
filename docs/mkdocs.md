## 创建个人网站（github pages）并将站点一键托管到Github

亮点：个人网站一键部署，简易文档直接渲染成网页挂载全流程
使用工具：mkdocs和git命令

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

## 3. mkdocs创建站点

我们只需要运行如下命令，就可以创建一个站点：

```
mkdocs new my_wiki(你喜欢的目录名)
```

这个命令会在当前目录下创建一个目录（my_wiki）

然后进入我们创建的目录

```shell
cd my_wiki
```

运行如下命令，即可在本地访问站点：

```
mkdocs serve
```

在浏览器输入地址`http://127.0.0.1:8000`，页面如下：

![1](..\pic\mkdocs_pic\1.png)

在运行站点的同时，我们可以实时修改站点信息，mkdocs会更新并展示在浏览器上，方便我们预览。

我们可以修改`mkdocs.yml`文件中的站点名`site_name`：

```
site_name: 我的第一个站点
```

## 4.部署站点

首先来认识一个命令:

```shell
mkdocs build
```

这个命令会在`learn-mkdocs`目录下生成一个目录`site`，这个目录中包含了静态站点的页面内容。

我们可以在GitHub中创建一个仓库

然后在目录下打开git，并将当前目录设置为一个仓库，然后与GitHub新创建的仓库连接：

    git init
    git remote add origin 仓库地址

然后在目录下打开控制台，执行以下命令：

```shell
mkdocs gh-deploy
```

这个命令会在GitHub项目上创建一个`gh-pages`分支，并执行`mkdocs build`命令，然后将当前目录中的`site`目录下的内容推送到远程的`gh-pages`分支

浏览器访问`http://YourGithubUsername.github.io/repo-name`即可

添加本地的文件到本地仓库：

```shell
git add .
```

这里的.表示所有文件都加进去，这里正常是没有输出反馈的，只要不报错一般就是没问题已经添加成功。

将本地修改保存到本地仓库中：

```shell
git commit -m"first version"
```

推送到远程仓库：

```
git remote add origin 仓库地址
git push -u origin main(or master)
```



## 5.mkdocs简单使用

#### 添加页面

在入门使用中，mkdocs为我们创建了一个页面`index.md`，我们同样可以自己添加页面，比如，在`docs`目录下创建页面`about.md`，然后在配置文件`mkdocs.yml`中添加以下配置项：

```
nav: 

  --主页: index.md

  --关于我: about.md
```



####  更改外观

如果你不满意mkdocs默认的外观样式，我们也可以进行相应的更改。

##### 更改图标

如果使用mkdocs主题，只需要在`docs`目录下创建目录`img`，然后在目录`img`中放入`favicon.ico`图标即可。

![2](..\pic\mkdocs_pic\2.png)

##### 更改主题

mkdocs默认有两个主题：mkdocs和readthedoc，默认使用mkdocs。

我们在配置文件中修改，使用`readthedocs`主题：

```
theme:
  name: readthedocs
```

我们也可以使用第三方主题，第三方主题详细列表如下：

https://[github](https://so.csdn.net/so/search?q=github&spm=1001.2101.3001.7020).com/mkdocs/mkdocs/wiki/MkDocs-Themes

可以参照具体的主题使用教程，进行配置。

在本例中，我们配置一个名为`material`的主题。

首先利用`pip`下载相应的主题：

```
pip install mkdocs-material
```

然后在配置文件中修改主题：

```yaml
theme:
  name: material
```

##### 个性化设置

如果想进行网页左上角logo修改，颜色修改等可加入如下内容

```
theme:
    name: "material"
    logo:
        icon: "mkwiki"
    palette:
        primary: "black"
        accent: "white"
    language: "zh"
```

