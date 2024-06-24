激活Typora

1.找到typora的安装目录

2.按照 Typora  --->  resources  --->  page-dist  --->  static  --->  js 这个路径找到LicenseIndex.180dd4c7.b98d5f1f.chunk.js和LicenseIndex.180dd4c7.d0150291.chunk.js这两个文件

![img](https://img-blog.csdnimg.cn/ff37559e7fad4c1087d3b401fdb333ad.png)

3.打开这两个文件，Ctrl + F 搜索 hasActivated="true"==e.hasActivated，并将其替换为 hasActivated="true"=="true"

`hasActivated="true"==e.hasActivated`

`替换为`

`hasActivated="true"=="true"`

![img](https://img-blog.csdnimg.cn/f3b3702c39454b31afb0904a0b510d53.png)

