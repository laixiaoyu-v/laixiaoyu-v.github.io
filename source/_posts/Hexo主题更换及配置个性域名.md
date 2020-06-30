---
abbrlink: 86b3a32e
date: 2020-03-21 15:10:08
categories: 日常折腾
tags: hexo
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200606195854.png
---
<h2 style="text-align: center;">前言</h2>
上次我们讲到了<a href="https://blog.laixiaoyu.cf/?p=45"><strong><span style="color: #0000ff;">Hexo的基本搭建以及部署到Github</span></strong></a>

这次我接着讲一下Hexo的主题更换及配置个性域名


<h2 style="text-align: center;"><strong>主题更换 </strong></h2>

我们先来到Hexo的官网：<span style="color: #0000ff;"><strong><a style="color: #0000ff;" href="http://hexo.io">hexo.io</a></strong></span>

选择Themes

点击主题图片可以预览主题

点击主题名字会跳到主题的Github的项目介绍页

找到自己喜欢的主题并在夏目介绍页下载这个主题

我就用<span style="color: #0000ff;"><a style="color: #0000ff;" href="https://github.com/JoeyBling/hexo-theme-yilia-plus">yilia</a></span>这个主题作演示吧:

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200321185529.png" alt="" />
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200321185706.png" alt="" />

&nbsp;

&nbsp;

下载完后解压到hexo搭建目录下的<span style="color: #ff0000;">themes</span>目录内

修改hexo的<span style="color: #ff0000;">_config.yml<span style="color: #000000;">文件</span></span>

<span style="color: #ff0000;"><span style="color: #000000;">找到 <span style="color: #ff0000;">theme: landscape <span style="color: #000000;">（默认主题）</span><span style="color: #000000;">这一行，</span></span></span></span>

<span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;"><span style="color: #ff0000;"><span style="color: #000000;">把</span> landscape</span>修改成你解压的主题名字（我的是yilia）</span></span></span></span>

&nbsp;

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 164823.png" alt="" />
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 165253.png" alt="" />

<span style="color: #ff0000;">_config.yml  <span style="color: #000000;">文件内也有很多可修改项目</span></span>

例如：博客标题  ，博客描述， 博主昵称等等
大家可以参考官方文档自行修改 ：<a href="https://hexo.io/zh-tw/docs/configuration"><span style="color: #0000ff;">Hexo官网文档</span></a>

<span style="color: #ff0000;"><span style="color: #000000;">主题的</span><strong> _config.yml </strong><span style="color: #000000;">文件也是有很多可修改选项具体参考主题的GitHub介绍页</span></span>

<span style="color: #ff0000;"><strong>注意：</strong><span style="color: #000000;">修改时破坏原有结构或多添加标点字符都有可能造成博客的崩溃，所以修改前注意备份以便还原</span></span>

修好好后重新生成静态页并部署：
```<code>
hexo g
hexo d
```
&nbsp;

部署成功后刷新你的博客就能看见效果：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 172744.png" alt="" />

&nbsp;

&nbsp;
<h2 style="text-align: center;"><strong>配置个性域名</strong></h2>
这一项大家必需有自己的域名才能设置

关于购买域名和免费域名的申请大家可以自行查找资料我在这里不多作赘述

&nbsp;

先来到博客目录下的<span style="color: #000000;"><span style="color: #ff0000;">source</span>目录内添加一个名为 <span style="color: #ff0000;">CNAME </span> 的<span style="color: #ff0000;">无后缀文件</span></span>

文件的内容为：<span style="color: #ff0000;">你的域名</span>

<span style="color: #ff0000;">注意：</span>文件一定不能有后缀

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 174045.png" alt="" />
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 174121.png" alt="" />

&nbsp;

添加完CNAME 文件后重新生成静态页并部署到GitHub：
```<code>
hexo g
hexo d
```
&nbsp;

最后来到你的域名管理平台

在<span style="color: #ff0000;">DNS</span>设置这一项下添加一个<span style="color: #ff0000;"> CNAME</span> 指向 <span style="color: #ff0000;">你的GitHub仓库地址</span>

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200321194553.png" alt="" />

地址栏输入你的域名：
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 174335.png" alt="" />

Done！！！域名也设置好了！！！

你可以把你的博客正式分享给你的小伙伴们了。

&nbsp;
<h2 style="text-align: center;"><strong>最后吐槽一下：</strong></h2>
其实这些个性化设置弄起来非常简单，写成文章就略显啰嗦了

希望大家有所收获！！！！

我的Hexo博客地址：<a href="http://b.laixiaoyu.cf"><span style="color: #0000ff;"><strong>赖小瑜</strong></span></a>