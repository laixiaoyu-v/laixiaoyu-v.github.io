---
title: windos去除图标上的快捷方式小箭头
tags: windows
categories: 日常折腾
cover: 'https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/07/07/456975.png'
abbrlink: a2e5b95d
date: 2020-07-07 17:50:50
---
<h2 style="text-align: center;"><strong>前言</strong></h2>
大家都知道windows系统的应用程序快捷方式图标会有一个小箭头：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/07/07/58fc62.png" />

虽然不会影响软件的使用，但是看着总让人有点强迫症犯瘾（至少本人是这样的）

要去除这个图标旁边的小箭头也并不难。
<h2 style="text-align: center;"><strong>去除小箭头</strong></h2>
首先我们复制以下代码：
```<html>
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Icons" /v 29 /d "%systemroot%\system32\imageres.dll,197" /t reg_sz /f
taskkill /f /im explorer.exe
attrib -s -r -h "%userprofile%\AppData\Local\iconcache.db"
del "%userprofile%\AppData\Local\iconcache.db" /f /q
start explorer
pause
```
然后新建一个文本文档，把复制的代码粘贴进去

然后点左上角的：<span style="color: #ff0000;">文件 </span>→ <span style="color: #ff0000;">另存为</span>

<span style="color: #ff0000;">保存类型：所有文件</span>

<span style="color: #ff0000;">文件名随意但后缀一定要是  .bat</span>

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/07/07/a23e5b.png" />

最后以<span style="color: #ff0000;">管理员身份</span>运行这个<span style="color: #ff0000;">bat</span>文件就可以了：

<img src="https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/2020/07/07/c284bd.png" />

是不是瞬间清爽了许多！！！
<h2 style="text-align: center;"><strong>恢复小箭头</strong></h2>
有去除当然就有恢复！

复制一下代码重复上面的步骤即可：
```<html>
reg delete "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Shell Icons" /v 29 /f
taskkill /f /im explorer.exe
attrib -s -r -h "%userprofile%\AppData\Local\iconcache.db"
del "%userprofile%\AppData\Local\iconcache.db" /f /q
start explorer
pause
```
恢复小箭头我是用不到啦！！！！
留给用得上的人。
<div id="gtx-trans" style="position: absolute; left: 422px; top: 312.719px;">
<div class="gtx-trans-icon"></div>
</div>