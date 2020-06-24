---
layout: shell-bot—
title: 通过Telegram机器人远程执行shell命令
date: 2020-05-25 15:10:08
categories: 日常折腾
tags: tg-bot
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/06/06/89031d.png
---
<h2 style="text-align: center;"><b>关于Shell-bot</b></h2>
<span style="font-weight: 400;">Shell-bot是一个通过</span><a href="https://zh.m.wikipedia.org/zh-tw/Telegram"><span style="font-weight: 400;">Telegram</span></a><span style="font-weight: 400;">远程运行shell命令的Telegran机器人。</span>

<span style="font-weight: 400;">GitHub项目地址：</span><a href="https://github.com/botgram/shell-bot"><span style="font-weight: 400;">https://github.com/botgram/shell-bot</span></a>
<h2><span style="font-weight: 400;">部署</span></h2>
<span style="font-weight: 400;">第一步安装node-pty依赖项：</span>
<pre class="EnlighterJSRAW" data-enlighter-language="generic">sudo apt install -y make python build-essential</pre>
&nbsp;

<span style="font-weight: 400;">第二步：</span>
<pre class="EnlighterJSRAW" data-enlighter-language="generic">git clone https://github.com/botgram/shell-bot.git &amp;&amp; cd shell-bot
npm install</pre>
<span style="font-weight: 400;">第三步：去Telegram的</span><a href="https://t.me/BotFather"><span style="font-weight: 400;">Botfathe</span></a><span style="font-weight: 400;">r申请一个机器人（步骤并不难所以不作演示了）</span>

<span style="font-weight: 400;">第四步：</span>
<pre class="EnlighterJSRAW" data-enlighter-language="generic">node server</pre>
<span style="font-weight: 400;">把从Botfather申请到的机器人api填进去并通过telegram给机器人发条信息绑定。</span>

<span style="font-weight: 400;">第五步：再运行一次</span>
<pre class="EnlighterJSRAW" data-enlighter-language="generic">node server</pre>
&nbsp;

<span style="font-weight: 400;">显示Bot ready时表示启动成功，可以愉快的通过bot来运行shell命令。</span>

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/05/25/efc851.png" />

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/05/25/003b7d.png" />

具体用法参考GitHub项目说明。

&nbsp;
<h2><b>最后</b></h2>
<span style="font-weight: 400;">类似的bot项目还有：</span><a href="https://github.com/marknote/TeleShellBot"><span style="font-weight: 400;">https://github.com/marknote/TeleShellBot</span></a>