---
abbrlink: beebccd2
date: 2020-03-19 15:10:08
categories: 日常折腾
tags: hexo
urlname: 2
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200606194054.png
---
<h1 style="text-align: center;">前言</h1>
<h3 style="text-align: center;">什么是hexo?</h3>
Hexo是一款基于Node.js的静态博客框架，依赖少易于安装使用，可以方便的生成静态网页托管在GitHub和Heroku上，是搭建博客的首选框架。
<p style="text-align: center;">为什么要搭建Hexo博客呢？</p>

<ol>
 	<li>我的博客最近刚刚搭建起来趁着热度没减退再搭建一个!</li>
 	<li>Hexo可以部署在GitHub不需要服务器</li>
 	<li>因为好玩!!</li>
<!-- more -->
</ol>
<p style="text-align: center;">准备工具</p>

<ol>
 	<li><a href="https://nodejs.org/en/" target="_blank" rel="noopener noreferrer"><span style="color: #ff0000;">Node.js</span></a></li>
 	<li><a href="https://git-scm.com/" target="_blank" rel="noopener noreferrer"><span style="color: #ff0000;">Git</span></a></li>
 	<li>GitHub账号</li>
</ol>
<h1 style="text-align: center;">搭建Hexo</h1>
安装Node.js和Git ：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 144713.png" alt="" /> 没什么难度无脑下一步

&nbsp;

输入：
```<code>
git --version
node -v
```
检查一下是否安装成功：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 145338.png" alt="" />

&nbsp;

因为考虑到NPM是国外的东西，也就是说他的源是国外的

我们可以把他的源改成国内淘宝的源这样安装速度会快些
```<code>
npm config set registry https://registry.npm.taobao.org –global 
npm config set disturl https://npm.taobao.org/dist –global
```
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 150726.png" alt="" />

&nbsp;

安装hexo组件：
```<code>
npm install -g hexo-cli
```
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 151025.png" alt="" />


本地安装部署hexo：
```<code>
hexo init blog               //blog是我的是我自定义的目录
```
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 151353.png" alt="" />

这时候你就可以看见这个目录下的已经创建了你的博客：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 151704.png" alt="" />


进入这个目录并执行：
```<code>
cd blog
hexo s
```
这时候打开<span style="color: #ff0000;"> <a style="color: #ff0000;" href="http://://localhost:4000" target="_blank" rel="noopener noreferrer">http://localhost:4000</a> </span>
你就能在本地的4000端口看到你的博客：
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 151931.png" alt="" />


要写博文的话可以用自己喜欢的文本编辑器往blog\source\_posts目录下添加 <span style="color: #ff0000;">.md <span style="color: #000000;">文件</span></span>

我就用记事本添加一个测试一下

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 153126.png" alt="" />


添加完后要重新生成静态页并部署到本地：
```<code>
hexo g 
hexo s
```
再刷新一下<a href="http://://localhost:4000"><span style="color: #ff0000;">http://localhost:4000</span></a>
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 154148.png" alt="" />
这就是我刚刚添加的测试文章
<h2 style="text-align: center;">部署到Github</h2>
首先去github新建一个仓库：
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200319210800.png" alt="" />


这里仓库名要按照 <span style="color: #ff0000;">你的github用户名.github.io <span style="color: #000000;">的格式设置：</span></span>

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200319211423.png" alt="" />



仓库创建完成后回到blog目录，编辑 <span style="color: #000000;"><span style="color: #ff0000;">_config.yml </span></span>

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 160019.png" alt="" />



拉到最下面添加
```<code>
type: git                                               //修改为git
repo:     你的仓库地址                                 //添加
branch: master                                        //添加
```

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 160418.png" alt="" />
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 160742.png" alt="" />


安装一键部署插件 <span style="color: #ff0000;">hexo-deployer-git</span> 并执行部署 ：
```<code>
npm install hexo-deployer-git --save
hexo d
```
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 161944.png" alt="" />


可以看见他报错了
它让我们先执行：
```<code>
git config --global user.email "你的GitHub邮箱"
git config --global user.name "你的GitHub用户名"
```
我们按它说的执行一下：
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200319213825.png" alt="" />



再次 <span style="color: #ff0000;">hexo d</span> 部署一下：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 162922.png" alt="" />

&nbsp;

输入你的GitHub账号和密码：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 163113.png" alt="" />

Done！部署成功

刷新一下你的GitHub仓库
在浏览器地址栏打开你的GitHub仓库名

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 163206.png" alt="" />
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/批注 2020-03-19 163417.png" alt="" />

&nbsp;

Done！现在你可以把你的GitHub仓库名分享给你的小伙伴

告诉他们这是你的新博客！！

至此Hexo的基本部署已结束！

<del>有空我再写一篇文章介绍一下hexo的主题更换及自定义域名！！</del>

已更新：<a class="post-title" href="https://b.laixiaoyu.cf/posts/86b3a32e.html">Hexo主题更换及配置个性域名</a>

&nbsp;

最后附上

Hexo官网：

<a href="https://hexo.io/zh-cn/"><span style="color: #3366ff;">https://hexo.io/zh-cn/</span></a>

Hexo官方文档：

<a href="https://hexo.io/zh-cn/docs/"><span style="color: #3366ff;">https://hexo.io/zh-cn/docs/</span></a>

Node.js官网：

<a href="https://nodejs.org/en/"><span style="color: #3366ff;">https://nodejs.org/en/</span></a>

Git官网：

<a href="https://git-scm.com/"><span style="color: #3366ff;">https://git-scm.com/</span></a>

