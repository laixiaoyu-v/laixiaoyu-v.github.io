---
title: PicGo – 一款免费、高效、实用的图床管理工具
abbrlink: 95a2046f
date: 2020-03-22 15:10:08
categories: 实用工具
tags: 图床
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200606195421.png
---
<h2 style="text-align: center;"><strong>前言</strong></h2>
无意中看见了一款非常好用的图床软件：PicGo，搭配GitHub和jsDelivr CDN 可以实现快速上传图片并获取CDN加速的图片URL链接。
<h2 style="text-align: center;"><strong>关于PicGo</strong></h2>
<strong>PicGo是 一个用于快速上传图片并获取图片URL链接的工具</strong>

<strong>PicGo 本体支持如下图床</strong>：
<ul>
 	<li><del><code>微博图床</code> v1.0</del> 微博图床从 2019 年 4 月开始进行防盗链，不建议继续使用</li>
 	<li><code>七牛图床</code> v1.0</li>
 	<li><code>腾讯云 COS v4\v5版本</code> v1.1 &amp; v1.5.0</li>
 	<li><code>又拍云</code> v1.2.0</li>
 	<li><code>GitHub</code> v1.5.0</li>
 	<li><del><code>SM.MS</code> v1.5.1</del> 由于官方不再支持V1版本，暂时请使用<a href="https://github.com/xlzy520/picgo-plugin-smms-user">smms-user</a>插件</li>
 	<li><code>阿里云 OSS</code> v1.6.0</li>
 	<li><code>Imgur</code> v1.6.0</li>
<!-- more -->
</ul>
本体不再增加默认的图床支持。你可以自行开发第三方图床插件。详见 <a href="https://picgo.github.io/PicGo-Core-Doc/" rel="nofollow">PicGo-Core</a>。

<strong>特色功能</strong>：
<ul>
 	<li>支持拖拽图片上传</li>
 	<li>支持快捷键上传剪贴板里第一张图片</li>
 	<li>Windows和macOS支持右键图片文件通过菜单上传 (v2.1.0+)</li>
 	<li>上传图片后自动复制链接到剪贴板</li>
 	<li>支持自定义复制到剪贴板的链接格式</li>
 	<li>支持修改快捷键，默认快速上传快捷键：<code>command+shift+p</code>（macOS）| <code>control+shift+p</code>（Windows\Linux)</li>
 	<li>支持插件系统，已有插件支持Gitee、青云等第三方图床
<ul>
 	<li>更多第三方插件以及使用了 PicGo 底层的应用可以在 <a href="https://github.com/PicGo/Awesome-PicGo">Awesome-PicGo</a> 找到。欢迎贡献！</li>
</ul>
</li>
 	<li>支持通过发送HTTP请求调用 PicGo 上传（v2.2.0+)</li>
 	<li>更多功能等你自己去发现，同时也会不断开发新功能
<ul>
 	<li>开发进度可以查看 <a href="https://github.com/Molunerfinn/PicGo/projects">Projects</a>，会同步更新开发进度</li>
 	<li>欢迎加入<a href="https://gitter.im/picgo-all/PicGo?utm_source=share-link&amp;utm_medium=link&amp;utm_campaign=share-link" rel="nofollow">官方Gitter频道</a>与我交流</li>
</ul>
</li>
</ul>
如果第一次使用，请参考应用<a href="https://picgo.github.io/PicGo-Doc/zh/guide/getting-started.html" rel="nofollow">使用文档</a>。遇到问题了还可以看看 <a href="https://github.com/Molunerfinn/PicGo/blob/dev/FAQ.md">FAQ</a> 以及被关闭的 <a href="https://github.com/Molunerfinn/PicGo/issues?q=is%3Aissue+is%3Aclosed">issues</a>。

&nbsp;
<p class="custom-block-title"><span style="color: #ff0000;"><strong>注意：</strong></span></p>
<span style="color: #ff0000;">请确保你安装了 Node.js， 并且版本 &gt;= 8。</span>

&nbsp;

&nbsp;
<h1 class="title-article" style="text-align: center;">PicGo+GitHub+jsDelivr CDN</h1>
我个人比较推荐：PicGo+GitHub+jsDelivr CDN这个组合（高效、免费、高速）

&nbsp;

<strong>下面我就介绍一下具体搭建方法：</strong>

登录GitHub创建一个新的仓库
<ol>
 	<li>名字随意</li>
 	<li>仓库得设置为 <code>Public</code>       （公开）</li>
 	<li>Initialize this repository with a README（勾上）</li>
</ol>
&nbsp;

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322151533.png" />

&nbsp;

&nbsp;

创建完后点击你的GitHub头像选择Setting（设置）

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322152137.png" />

再点Developer settings

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322152232.png" />

再点Personal access tokens

选择 Generate new token

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322152522.png" />

Note：随便输

勾选 repo

拉到最下面点Generate new token

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322153243.png" />

&nbsp;

创建成功后你会得到一个token

复制生成的token

<span style="color: #ff0000;"><strong>注意：token只显示一次，关闭网页后就无法再找到，所以要保存一下</strong></span>

&nbsp;

配置PicGo：
<ol>
 	<li>设定仓库名：<span style="color: #ff0000;"><strong>你的GitHub用户名</strong><span style="color: #000000;"><strong>/</strong><span style="color: #000000;"><strong><span style="color: #ff0000;">仓库名</span></strong></span></span></span></li>
 	<li>设定分支名：<strong><span style="color: #ff0000;">master</span></strong></li>
 	<li>设定Token：<strong><span style="color: #ff0000;">填写刚刚生成的token</span></strong></li>
 	<li>指定存储路径：<span style="color: #ff0000;"><strong>相当于在仓库设定一个存储的文件夹（自定义吧）</strong></span></li>
 	<li>设定自定义域名：<strong><span style="color: #ff0000;">https://cdn.jsdelivr.net/gh/你的GitHub用户名/仓库名/</span></strong></li>
</ol>
<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322154912.png" />

&nbsp;

这样就配置完成了！！！

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200322155045.png" />

&nbsp;

<strong><span style="color: #ff0000;">注意：这个图库并不是私人的，任何人都可以在GitHub上查看你上传的图片</span></strong>

我是用来存放我博文的图片可以提高创作效率。

&nbsp;

&nbsp;
<h2 style="text-align: center;">最后附上：</h2>
<ol>
 	<li>PicGo在GitHub上的项目地址：<a href="https://github.com/Molunerfinn/PicGo" target="_blank" rel="noopener noreferrer">PicGo</a></li>
 	<li>PicGo的使用文档：<a href="https://picgo.github.io/PicGo-Doc/zh/guide/getting-started.html" target="_blank" rel="noopener noreferrer">PicGo使用文档</a></li>
</ol>
&nbsp;