---
title: CentOS 安装Python
abbrlink: 8240d80f
date: 2020-03-25 15:10:08
categories: 日常折腾
tags: Linux
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200606200146.png
---
<h4>首先安装 Python 必要的依赖包：</h4>
<pre class="EnlighterJSRAW" data-enlighter-language="null">yum -y groupinstall development
yum install -y zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel</pre>
<h4></h4>
<h4>然后下载安装包：</h4>
这里有两种方法
<ol>
 	<li>在<a href="https://link.jianshu.com/?t=https%3A%2F%2Fwww.python.org%2F" target="_blank" rel="nofollow noopener noreferrer">python官网</a>下载源码格式的安装包，然后通过winscp或者xftp上传到你的服务器。</li>
 	<li>使用wget命令联网在线下载：
```<code>
wget https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tgz
```
&nbsp;</li>
</ol>
<h4>安装：</h4>
<ol>
 	<li>解压并进入目录：
```<code>
tar xf Python-3.8.2.tgz
cd Python-3.8.2
```
&nbsp;</li>
 	<li>进行编译安装（我们将python3.8.2安装在/usr/local/python3目录下）
```<code>
./configure --prefix=/usr/local/python3
make &amp;&amp; make install
```
&nbsp;</li>
 	<li>验证是否安装
```<code>
python3
```
