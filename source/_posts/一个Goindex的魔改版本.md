---
title: 一个Goindex的魔改版本
abbrlink: a3ab42cc
date: 2020-05-27 15:10:31
tags: 日常折腾
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/73118788_p0_master1200.jpg
---
<h2 style="text-align: center;"><strong>关于Goindex</strong></h2>
<code>GoIndex</code>是一款部署在<code>Cloudflare Workers</code>的<code>Google Drive</code>目录索引程序，无需提供服务器，可以直接列出你谷歌网盘的所有文件，同时下载和访问也不需要挂梯子，也可以在线观看某些格式的视频文件。

原版Github地址<strong>：</strong><a href="https://github.com/donwa/goindex" target="_top" rel="noopener noreferrer">https://github.com/donwa/goindex</a>

原版作者由于某些原因已经删库。

这次主要介绍的是基于原版Goindex的一个魔改版本
<div align="left">Github项目地址 ：<a href="https://github.com/Aicirou/goindex-theme-acrou" target="_blank" rel="noopener noreferrer">https://github.com/Aicirou/goindex-theme-acrou</a></div>
<div align="left"></div>
<div align="left">此魔改版本的特色：</div>
<div align="left">
<ul>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🗂 多盘切换</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🔐 Http Basic Auth</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🎨 网格视图模式（文件预览）</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🎯 分页加载</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🌐 I18n（多国语言）</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🛠 html渲染</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🖥 视频在线播放(mp4,mkv,webm,flv,m3u8)</li>
 	<li class="task-list-item"><input id="" class="task-list-item-checkbox" checked="checked" disabled="disabled" type="checkbox" /> 🚀 拥有更快的速度</li>
</ul>
开发者demo <a href="https://oss.achirou.workers.dev/" target="_blank" rel="noopener noreferrer">https://oss.achirou.workers.dev/</a>

</div>
<h2 style="text-align: center;" align="left"><strong>部署</strong></h2>
此魔改版本同样支持快速部署：
<ol>
 	<li>打开<a href="https://goindex-quick-install.glitch.me/" rel="nofollow">https://goindex-quick-install.glitch.me</a></li>
 	<li>授权并获取授权码</li>
 	<li>将代码部署到 <a href="https://www.cloudflare.com/" rel="nofollow">Cloudflare Workers</a></li>
</ol>
关于使用自己的api部署可以查阅项目介绍页的说明，由于本人较懒使用的是快速部署所以就不过多介绍了。

使用个人api部署好处就是安全点，高峰期也不容易爆炸。
<h2 align="left"></h2>