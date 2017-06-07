---
title: 记录我的Hexo博客搭建过程
---

使用hexo搭建这个个人博客，第一篇文章就记录一下自己的搭建过程。

# 1. hexo安装

要安装hexo需要先安装Node.js。在安装Node.js的时候会自动添加环境变量和安装npm。[Node.js下载地址](https://nodejs.org/dist/v6.10.3/node-v6.10.3-x64.msi)。安装后在命令行窗口中输入如下命令检查是否安装成功。
```bash
node -v
npm -v
```
然后使用npm命令安装hexo，先新建一个文件夹来存放自己的博客，然后当前路径下shift+鼠标右键打开命令行窗口，输入
```bash
npm install -g hexo
```
在安装完成后，进行博客初始化，输入
```bash
hexo init
```
然后输入以下命令启动hexo服务进行测试
```bash
hexo g
hexo s
```
在浏览器中输入：localhost:4000可以看到生成的初始博客。

# 2. 推送网站

接下来要做的是推送网站，也就是发布博客。这里选择的是推送到github上，github支持用户建立自己的静态主页。
首先需要修改站点配置文件，在博客的根目录下打开_config.yml文件，翻到最后，修改为

```
deploy:
  type: git
  repo: https://github.com/username/username.github.io.git
  branch:master
```
这里要注意的是冒号后面需要加一个空格，否则无法推送。
在修改完后，在命令行窗口中输入命令进行推送。
```bash
hexo d
```
在完成后打开个人的github主页可以看到自己的推送上去的网站。


# 3.扩展

## hexo主题

hexo能够自定义主题，也可以下载别人的主题应用到自己的网页上。[主题下载地址](https://hexo.io/themes/)。将下载下来的主题放在根目录的themes位置，同时修改_config.yml文件的theme属性就可以启用下载下来的主题。

## Markdown

hexo的博客内容使用markdown语法编写，使用时需要熟悉一定的markdown语法。[markdown语法参考链接](http://www.appinn.com/markdown/)。[markdown编辑器推荐](http://www.williamlong.info/archives/4319.html)

## hexo常用命令

### 创建新的页面

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### 启动本地服务

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### 产生静态页

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### 网页推送

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/deployment.html)
