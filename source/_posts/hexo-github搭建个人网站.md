---
title: hexo+github搭建个人博客
date: 2019-08-08 19:27:42
tags:
	- 兴趣
	- hexo
	- GitHub
---
### 第一章：目的
*hexo+GitHub搭建个人博客*
**主要步骤**
* 安装git-------------远程安装环境
* 安装node.js--------hexo安装环境
* 安装hexo ----------博客生成软件
* github配置---------远程托管网站
* 远程配置 -----------搭建远程
* 更换主题 -----------选择自己所喜风格

<!-- more -->
### 第二章：内容
**具体操作**
*以下步骤都是基于Windows操作系统*

#### 安装git

git[官网](https://git-scm.com/)直接下载git，并默认安装。
安装完成后，还需要最后一步设置，在命令行输入：
```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以每个机器都必须自报家门：你的名字和Email地址。
*建议*：

1.建议先学习一些Linux命令，b站有[视频](https://www.bilibili.com/video/av15976434?from=search&seid=16920500767321526702)只需要了解一些简单命令，Linux命令在整个学习过程中都有用到，学会了更容易理解和操作；
2.然后再学git[教程](https://www.liaoxuefeng.com/wiki/896043488029600)(当然可以b站找[视频](https://www.bilibili.com/video/av10475153?from=search&seid=15072902551637942848)结合学习)，再学习后面的教程，这个教程包括了github的配置。
#### 安装node.js

node.js[官网](https://nodejs.org/en/)下载LTS，默认安装即可。
找位置新建一个文件夹，如：hexo；在该文件夹下再新建一个文件夹，如blog（这个文件夹即是你的博客，出现错误删除即可重新来）。
#### 安装hexo软件

在blog文件夹右击Git Bash Here（后续所有命令均在该文件夹执行），
第一步：安装hexo命令和查看hexo版本：
```
npm i -g hexo
#安装完成，查看hexo版本
hexo -v
```
第二步：初始化命令（真正搭建blog）
```
hexo init
```
这时blog文件夹会生成一些必要的文件：
1. node_modules：是依赖包
2. public：存放的是生成的页面
3. scaffolds：命令生成文章等的模板
4. source：用命令创建的各种文章
5. themes：主题
6. _config.yml：整个博客的配置_
7. db.json：source解析所得到的
8. package.json：项目所需模块项目的配置信息
为了检测我们的网站雏形，分别按顺序输入以下命令：
```
hexo clean #清理缓存
hexo g  #hexo generate 生效
hexo s  #hexo server 启动服务预览
```
这些命令在后面作介绍，完成后，打开浏览器输入地址：localhost:4000，即可看到搭建的博客内容。
到这里本地blog已经搭建完成，下面需要一些配置将搭建好的博客实现远程访问。
#### github配置
*上面建议学完可以忽略github配置教程*

自行注册[github账号](https://github.com/) ,由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以，需要一点设置：
第1步：创建SSH Key
```
ssh-keygen -t rsa -C "youremail@example.com"
```

你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
![github设置.png](/img/hexo-github搭建个人网站/github设置.png)

![github设置2.png](/img/hexo-github搭建个人网站/github设置2.png)


第三步：创建远程库
创建一个与github用户名一致的repository，即username.github.io(必须是这种命名规则)
![github设置3.png](/img/hexo-github搭建个人网站/github设置3.png)
#### 远程配置
接下来在blog根目录里的_config.yml文件称为站点配置文件，即图片所示文件（如果不清楚可以b站找相关[视频](https://www.bilibili.com/video/av44544186?from=search&seid=8638809533597874960)）。
![github设置4.png](/img/hexo-github搭建个人网站/github设置4.png)

用编辑器打开此文件，找到deploy位置，并添加并保存文件。
```
deploy:
    type: git
    repo: 这里填入你之前在GitHub上创建仓库的完整路径，记得加上 .git
    （即clone仓库URL链接,#如：repo: https://github.com/chen-huai/chen-huai.github.io.git）
    branch: master
    
    注意：
这个文件冒号后面是要加一个空格，不然会报错。
```
这其实就是给hexo d 这个命令做相应的配置，让hexo知道你要把blog部署在哪个位置，很显然，我们需要部署在自己的GitHub仓库里。最后安装Git部署插件，输入命令：
```
npm install hexo-deployer-git --save
```
好了，最后再来一套素质三连
```
hexo clean #清理缓存
hexo g  #hexo generate 生效
hexo d  #hexo deploy 部署
```
这样在浏览器输入username.githun.io即可访问你自己的博客。
这里解释一下hexo的命令：
1. hexo clean #清理缓存
2. hexo n "我的博客" == hexo new "我的博客" #新建文章
2. hexo g == hexo generate #生效
3. hexo s == hexo server #启动服务预览
4. hexo d == hexo deploy #部署
#### 更换主题

如果你不喜欢Hexo默认的主题，可以更换不同的主题，主题传送门：[Themes](https://hexo.io/themes/)，可以在blog目录中的themes文件夹中查看你自己主题是什么。
第一步：下载主题，以yilia主题为例，打开命令行输入：
```
git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
#themes/yilia为下载主题保存位置
```
第二步：更改_config.yml配置文件，修改主题为yilia
```
theme： yilia
```
记得素质三连
***
*最后祝大家玩得愉快*

