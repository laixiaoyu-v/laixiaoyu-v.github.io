---
title: Hexo博客的一个备份插件
categories: 实用工具
tags: hexo
abbrlink: 8c99dd7c
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200622182835.png
date: 2020-06-19 12:48:11
---
<h2 style="text-align: center;">前言</h2>
说到博客备份我想大家都有自己的方法进行备份吧。

我的hexo博客搭建起来其实也有一段时间了，

但是我一直用最傻瓜的方式对博客进行备份。

那就是直接打包hexo的源文件然后进行保存。

这个方法简直粗暴简单，就算换了台设备只要配置好操作环境把博客源文件解压出来就可以继续愉快的写文章了。

虽然上面提到的方法粗暴简单，但是我还是发现了更加方便的另一种方法。

那就是用hexo的插件<a href="https://github.com/coneycode/hexo-git-backup" target="_blank" rel="nofollow noopener noreferrer">hexo-git-backup</a> 进行备份。

插件备份的好处很明显：
<ol>
 	<li>一条命令就能完成备份</li>
 	<li>直接备份到github的仓库或者仓库分支</li>
 	<li>更换了设备只要配置好环境后直接克隆仓库或者仓库分支就能恢复</li>
</ol>
&nbsp;
<h2 id="具体操作" style="text-align: center;">具体操作</h2>
首先检测一下hexo的版本：
```<code>
hexo version
```
然后按照不同版本使用以下命令进行安装

&nbsp;

如果你的 Hexo 版本是 2.x.x，则使用以下命令安装：
```<code>
npm install hexo-git-backup@0.0.91 --save
```
如果你的 Hexo 版本是3.x.x则使用这条命令：
```<code>
npm install hexo-git-backup --save
```
安装好插件去创建一个githui创库或者在已部署了hexo的仓库下创建一个分支

我为了节约资源就直接创建一个仓库分支吧，

输入要创建的分支名进行创建：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200619165648.png" />

&nbsp;

然后打开博客目录下的<span style="color: #ff0000;">_config.yml<span style="color: #000000;">文件</span></span>

在最下方添加：
```<code>
    type: git
    repository:
       github: git@github.com:xxx/xxx.github.io.git,branchName
       coding: git@github.com:xxx/xxx.github.io.git,branchName
```
xxx表示你的github用户名（共四处）

branchName表示你的仓库的分支名
<h2 style="text-align: center;">使用</h2>
直接执行：
```<code>
hexo backup 
```
或者：
```<code>
hexo b
```
这样就大功告成把hexo博客源文件备份到GitHub仓库中了
<h2 style="text-align: center;">恢复备份</h2>
首先安装hexo
```<code>
npm install hexo-cli -g
```
然后克隆远程仓库：
```<code>
git clone 你的仓库（分支）地址 blog
```
进入克隆好的hexo源文件目录：
```<code>
cd blog
```
利用package.json安装相关插件：
```<code>
npm install
```
这样就恢复了hexo博客了，又可以愉快的写作了。