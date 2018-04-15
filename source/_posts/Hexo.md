---
title: 关于在windows下使用Hexo创建一篇新的博客
abbrlink: 10674
date: 2018-04-15 12:18:01
tags:
---
欢迎来到我的第一篇博客，这是我的第一篇博客。
下面是我学习如何用Hexok写博客的一些心得体会。
可能我写的不够详细，请参考[hexo官方文档](https://hexo.io/docs/writing.html)。

<!-- more -->
### 创建新的blog
---
<font size="2">在cmd中自己本地的blog目录下执行以下命令</font><br/>
``` bash
$ hexo new [layout] <title>
```
<font size="2">让我们开始看看这条命令吧。</font>
<font>title是你的博客名称</font><br/>
<font size="2">其中layout表示布局，默认表示post</font>
<font size="2">其实它是这样的表示的。</font><br/>
```bash
Layout  Path 
post    source/_posts 
page    source 
draft   source/_drafts 
```


<font size="2">我们可以在命令行下都试一遍，这样自己会更好的理解。</font>

### 使用草稿来写blog
---

<font size="2">前面我们讲过Layout，中有三个模式。其中有一个为draft模式。</font>
<font size="2"> 我们采用命令</font>
``` bash
$ hexo publish [layout] <title>
```
<font size="2">title必须是你的drafts文件夹中要有的文件名,换个角度来说就是你的博客的名称。</font><br/>
<font size="2">&emsp;&emsp;当然这只是如何生成博客，具体的编写还是要自己在自己博客目录下source文件夹下的问价找出自己要编写的方式然后自己根据markdown语法规则来编写。</font>