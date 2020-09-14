---
title: Termux-安卓终端模拟器和Linux环境应用程序
abbrlink: 58ebd63
date: 2020-03-23 15:10:08
tags: Termux
categories: 日常折腾
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200606195744.png
---
<h2 style="text-align: center;">前言</h2>
偶然间在柜子里翻出了一个闲置的古董安卓手机。

于是开始挖掘有没有什么方法可以榨干它的剩余价值（其实就是爱折腾）

于是被我发现了Termux这个软件。
<h2 style="text-align: center;"><strong>关于Termux</strong></h2>
<a href="https://termux.com/">Termux</a> 是一款基于 Android 平台的开源 Linux 终端模拟器，使用 pkg(apt) 进行软件包的管理。最重要的是，它无需 root 权限，因此，绝大多数 Android 都可以运行。
<!-- more -->
因为 Termux 是一款 Linux 终端模拟器，因此，在命令的使用方面和 Linux 是一致的。
<h3 class="ss-hIdChildren-2">pkg 使用命令速记</h3>
<ul>
 	<li>pkg search &lt;query&gt; 搜索包</li>
 	<li>pkg install &lt;query&gt; 安装包</li>
 	<li>pkg uninstall &lt;query&gt; 卸载包</li>
 	<li>pkg update 更新源</li>
 	<li>pkg upgrade 升级软件包</li>
 	<li>pkg shoe &lt;packge&gt; 显示某个包的详细信息</li>
</ul>
<strong><span style="color: #ff0000;">没错！这里吧啦吧啦了一大堆Termux的介绍其实都是我从网上抄来的！</span></strong>
<h2 style="text-align: center;">我个人的实际应用</h2>
<h2>搭建Hexo</h2>
没错！！！说到底还是Hexo(其实是因为我暂时也就想到这个，难道我对博客的搭建热度还没减退？？）

<strong>实际操作：</strong>

首先更新一下软件包和软件源：
```<code>
apt update
apt upgrade
```
安装Nodejs和Git：
```<code>
apt install git
apt install nodejs
```
剩下的参考我之前的文章：

<span style="color: #0000ff;"><a class="post-title" style="color: #0000ff;" href="https://b.laixiaoyu.cf/posts/beebccd2.html">记一次Hexo博客的搭建过程。</a></span>

<span style="color: #0000ff;"><a class="post-title" style="color: #0000ff;" href="https://b.laixiaoyu.cf/posts/86b3a32e.html">Hexo主题更换及配置个性域名</a></span>

部署Hexo的方法和跟上面的两篇文章说的大同小异。
<h2></h2>
<h2 style="text-align: center;"><strong>通过ssh工具连接Termux</strong></h2>
既然是一个Linux终端模拟器在安卓端操作或许不太方便（个人习惯吧）

那能不能用电脑ssh连接上去呢？

答案是肯定的（不能的话可能就不写这篇文章了）

<strong>实际操作：</strong>

安装openssh：
```<code>
apt install openssh
```
打开端口服务
```<code>
sshd
```
获取用户名

（其实用户名是可以随意填的，因为Termux是单用户系统。即使你登陆时带上了用户名，Termux也会忽略该用户名，所以用户名获取只是走流程）
```<code>
whoami
```
设置ssh密码
```<code>
passwd
```
查看ip
```<code>
ifconfig
```
<span style="color: #ff0000;"><strong>端口（默认是8022）</strong></span>

接着就是电脑端打开ssh工具输入ip、用户名、密码、端口（8022）就可以了

<h2 style="text-align: center;"><strong>最后吐槽</strong></h2>
折腾了半天其实好像也没有榨干我的古董安卓机的剩余价值！！！
