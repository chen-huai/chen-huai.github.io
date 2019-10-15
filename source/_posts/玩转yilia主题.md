---
title: 玩转yilia主题
date: 2019-08-10 15:49:54
tags:
	- 兴趣
	- hexo
	- 主题
---
### 第一章：目的
*关于yilia主题的一些设置和问题*
**常见问题**
* 关于yilia主题所有文章显示不全问题
* yilia主题中_config.yml配置文件
* 菜单
* 子导航
* 文章内容仅显示摘要
* 图片设置
* 友情链接
* 关于我
* 文章中图片显示

<!-- more -->
### 第二章：内容
**解决方案**
#### 关于yilia主题所有文章显示不全问题
如图：

![yilia](/img/yilia设置.png)
在blog文件夹，输入代码：
```
npm i hexo-generator-json-content --save
```
等待安装完成，并在博客配置文件_config.yml添加如下内容，注意格式请保持一致。
```
jsonContent:
    meta: false
    pages: false
    posts:
      title: true
      date: true
      path: true
      text: false
      raw: false
      content: false
      slug: false
      updated: false
      comments: false
      link: false
      permalink: false
      excerpt: false
      categories: false
      tags: true
      
```
素质三连，一般这时已经修复bug。
*如果实在不能修复并网上找的方法一律不行时，请将blog文件删除，并重新搭建博客再试一遍*
#### yilia主题中_config.yml配置文件
这里你会发现有两个_config.yml配置文件，一个是博客的基础配置文件，一个是主题的配置文件。博客配置文件一般只需要修改作者，网站信息等一些基本需求和修复上述bug时所添加的内容。而主题配置需要修改的比较多，这样才能打造出个性化界面。
#### 菜单
在yilia主题中，menu功能有些类似于分类的标签，修改配置文件_config.yml：
```
menu:
  主页: /
  随笔: /tags/随笔/
  python: /tags/python/
```
主页为所有文章，按时间顺序排列；随笔和python为标签，能在这下面找到带有相应标签的所有文章。而一篇文章可以添加数个标签，如：
```
---
title: hexo+github搭建个人网站
date: 2019-08-08 19:27:42
tags:
    - 随笔
    - hexo
    - github
    
---
注意 ”-“ 后面紧跟一个空格
```
这样这篇文章就出现在随笔标签页中，像极了将文章分类。
#### 子导航
子导航中，选择自己需要的并添加链接即可，其它的可以注释，修改配置文件_config.yml：
```
subnav:
  github: "https://github.com/chen-huai"
  #weibo: "#"
  #rss: "#"
```

#### 文章内容仅显示摘要
在blog主页会发现每一篇文章都会将全部内容显示出来，不利于我们查看文章，这时我们只需要开头一部分内容显示，即可方便查找也能知道文章大致内容。而这是需要一些设置的，如图在文章正文部分添加一个代码：
```
<!-- more -->
```
![more](/img/yilia设置2.png)
主题配置文件_config.yml，默认为more
```
# 文章太长，截断按钮文字
excerpt_link: more
```
这时在hexo搭建的博客首页就会发现文章只显示"more"之前的内容，之后的内容则被隐藏。而"more"这行代码在HTML中是被注释内容，不显示。
#### 图片设置
设置打赏功能，网站小图标，头像添加图片
需要在主题文件夹中/themes/yilia/source/添加一个assets，并将所有图片放入其中，然后将需要设置的图片信息填入配置文件_config.yml中即可。
##### 打赏功能
修改配置文件_config.yml：
```
# 打赏
# 打赏type设定：0-关闭打赏； 1-文章对应的md文件里有reward:true属性，才有打赏； 2-所有文章均有打赏
reward_type: 2
# 打赏wording
reward_wording: '谢谢你请我吃糖果'
# 支付宝二维码图片地址，跟你设置头像的方式一样。比如：/assets/img/alipay.jpg
alipay: /assets/支付宝收款.jpg
# 微信二维码图片地址
weixin: /assets/微信收款.jpg
```
打赏功能其实只是将微信和支付宝收款二维码的图片显示在网站上。
##### 网站小图标
修改配置文件_config.yml：
```
favicon: /assets/ch.ico
```
##### 头像
修改配置文件_config.yml：
```
avatar: /assets/279759ee3d6d55fbd90b8a9e6c224f4a21a4ddbd.jpg
```

#### 友情链接
我在这边会添加一些好的博主链接，直接修改主题配置文件_config.yml。
```
friends:
  廖雪峰博客: https://www.liaoxuefeng.com/wiki/896043488029600
  小丁博客: https://tding.top/archives/9a232bbe.html
  litten博客: http://litten.me/
```
当然也可以完全不需要友链，将其注释掉即可：
```
smart_menu:
  innerArchive: '所有文章'
  #friends: '友链'
  aboutme: '关于我'
```
#### 关于我
可以写一些自己的基本情况，看你想写些什么都可以。
```
aboutme: 兴趣<br><br>只做自己<br>

注意：支持部分HTML语法
```
#### 文章中图片显示
hexo文章一般是markdown格式的，但是图片引用时最好需要一些设置以确保网站生效时，图片能正常显示。
需要在博客最初文件夹blog/source/中新建一个img文件夹，并将所需要的图片放入其中（一般是文章中图片较少时适用）。然后用markdown图片语法即可，不要用绝对路径。
```
![图片](/img/图片名字.png)
```
最后，记得素质三连
***
*yilia主题设置和一些问题已经解决，大家可以将自己制作的网站分享给自己的好友啦*