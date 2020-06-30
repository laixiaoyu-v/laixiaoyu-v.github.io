---
abbrlink: 5c74a5cd
date: 2020-04-24 15:10:08
categories: 实用工具
tags: 图床
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blog/20200606200408.png
---
<!-- wp:paragraph -->
<p>&nbsp;</p>
<!-- /wp:paragraph -->
<h2>前言</h2>
<p>之前给大家介绍过一款免费、高效、实用的图床管理工具—<a href="https://blog.laixiaoyu.cf/?p=105">PicGo</a></p>
<p>这次再给大家介一个图床工具，同样是利用Github和jsDelivr的资源搭建cdn加速图床。</p>
<p>这次要用到网站环境，VPS 或者虚拟主机都可以！！！</p>
<h2 >搭建</h2>
<p>首先要创建一个Github仓库</p>
<p>过程我就不演示了，过程可以参考我的这篇文章：<a href="https://likexy.me/?p=105">传送门</a></p>
<p>接下来我们去autoPicCdn的GitHub项目地址下载源码：<a href="https://github.com/peng4740/autoPicCdn">传送门</a></p>
<p>解压下载的源码并修改 up.php 里的变量</p>
```<code>
error_reporting(0);
date_default_timezone_set("PRC");
define("REPO","此处填写你的GitHub仓库名");//必须是下面用户名下的公开仓库
define("USER","此处填写你的GitHub用户名");//必须是当前GitHub用户名
define("MAIL","mail@foxmail.com");//
define("TOKEN","此处填写在GitHub上获取的token");//https://github.com/settings/tokens 去这个页面生成一个有写权限的token（write:packages前打勾）
 ```

<p>然后将 index.html 和 up.php 上传到你的网站空间、vps或者虚拟主机上。</span></span></span></span></p>
<p>访问你的网站空间、vps或者虚拟主机即可：</p>
<p><img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/04/24/66cb4d.png" /></p>
<p>选择图片上传即可获得经过cdn加速到图片链接。</p>
