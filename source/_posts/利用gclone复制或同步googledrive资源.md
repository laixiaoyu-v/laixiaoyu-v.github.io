---
title: 利用gclone复制或同步googledrive资源
abbrlink: ee8270f4
date: 2020-04-01 07:51:59
categories: 日常折腾
tags: Gclone
cover: https://cdn.jsdelivr.net/gh/laixiaoyu-v/ImgHosting/blogimage_2020-03-19_13-26-38.png
---
<h2>前言</h2>
虽然早就听说了<a href="https://github.com/donwa/gclone/blob/master/README_zh.md">gclone</a>功能更加强大，但是由于一开始接触googledrive资源搬运时先使用的是folderclone，所以习惯安逸的我也就一直没有选择改用gclone。这段时间闲来无事所以还是尝试了一下，尝试的结果很明显gclone真香！！！

gclone是要配合<a href="https://github.com/Spazzlo/folderclone">FoldeRclone</a>或者<a href="https://github.com/xyou365/AutoRclone/blob/master/Readme.md">AutoRclone</a>使用才能发挥他的完整功能，没有用过以上两个工具的同学请自行google补课！！！
<!-- more -->
&nbsp;
<h2 style="text-align: center;">关于gclone</h2>
gclone是rclone的一个魔改版本。

为Google Drive操作增加自动切换账户和命令行根目录id操作支持。

能够在 Google Drive 账号之间、谷歌团队盘之间快速拷贝、传输学习资料。

调用 Service Accounts，实现达到750G流量限制后，自动切换账户。

其他功能与原版rclone相同。

&nbsp;
<h2 style="text-align: center;">安装及配置</h2>
安装gclone：
<pre class="EnlighterJSRAW" data-enlighter-language="null">bash &lt;(wget -qO- https://git.io/gclone.sh)</pre>
查看版本信息：
<pre class="EnlighterJSRAW" data-enlighter-language="null">gclone version</pre>
&nbsp;

配置gclone：
<pre class="EnlighterJSRAW" data-enlighter-language="null">gclone config
</pre>
&nbsp;

前面提到过gclone是要配合folderclone或aoturclone的service accounts使用

配置过程中，当出现 <span style="color: #ff0000;"><code>service_account_file</code></span> 选项时，要填上accounts目录下的任意<span style="color: #ff0000;">.json<span style="color: #000000;">的路径</span></span>

当出现 <code>service_account_file_path</code> 时，填写<span style="color: #ff0000;">accounts</span>的目录路径

我这里就把folderclone的accounts目录放在root目录下演示一次配置过程：
<pre class="EnlighterJSRAW" data-enlighter-language="null">[root ~]# gclone config
2020/04/01 14:11:45 NOTICE: Config file "/root/.config/rclone/rclone.conf" not found - using defaults
No remotes found - make a new one
n) New remote
s) Set configuration password
q) Quit config
n/s/q&gt; n
#输入n新建
name&gt; fz
#名字随意输
Type of storage to configure.
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / 1Fichier
   \ "fichier"
 2 / Alias for an existing remote
   \ "alias"
 3 / Amazon Drive
   \ "amazon cloud drive"
 4 / Amazon S3 Compliant Storage Provider (AWS, Alibaba, Ceph, Digital Ocean, Dreamhost, IBM COS, Minio, etc)
   \ "s3"
 5 / Backblaze B2
   \ "b2"
 6 / Box
   \ "box"
 7 / Cache a remote
   \ "cache"
 8 / Citrix Sharefile
   \ "sharefile"
 9 / Dropbox
   \ "dropbox"
10 / Encrypt/Decrypt a remote
   \ "crypt"
11 / FTP Connection
   \ "ftp"
12 / Google Cloud Storage (this is not Google Drive)
   \ "google cloud storage"
13 / Google Drive
   \ "drive"
14 / Google Photos
   \ "google photos"
15 / Hubic
   \ "hubic"
16 / In memory object storage system.
   \ "memory"
17 / JottaCloud
   \ "jottacloud"
18 / Koofr
   \ "koofr"
19 / Local Disk
   \ "local"
20 / Mail.ru Cloud
   \ "mailru"
21 / Mega
   \ "mega"
22 / Microsoft Azure Blob Storage
   \ "azureblob"
23 / Microsoft OneDrive
   \ "onedrive"
24 / OpenDrive
   \ "opendrive"
25 / Openstack Swift (Rackspace Cloud Files, Memset Memstore, OVH)
   \ "swift"
26 / Pcloud
   \ "pcloud"
27 / Put.io
   \ "putio"
28 / QingCloud Object Storage
   \ "qingstor"
29 / SSH/SFTP Connection
   \ "sftp"
30 / Sugarsync
   \ "sugarsync"
31 / Transparently chunk/split large files
   \ "chunker"
32 / Union merges the contents of several remotes
   \ "union"
33 / Webdav
   \ "webdav"
34 / Yandex Disk
   \ "yandex"
35 / http Connection
   \ "http"
36 / premiumize.me
   \ "premiumizeme"
Storage&gt; 13
#选择googledrive（这里是13）
** See help for drive backend at: https://rclone.org/drive/ **

Google Application Client Id
Setting your own is recommended.
See https://rclone.org/drive/#making-your-own-client-id for how to create your own.
If you leave this blank, it will use an internal key which is low performance.
Enter a string value. Press Enter for the default ("").
client_id&gt; 
#回车（默认）
Google Application Client Secret
Setting your own is recommended.
Enter a string value. Press Enter for the default ("").
client_secret&gt; 
#回车（默认）
Scope that rclone should use when requesting access from drive.
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / Full access all files, excluding Application Data Folder.
   \ "drive"
 2 / Read-only access to file metadata and file contents.
   \ "drive.readonly"
   / Access to files created by rclone only.
 3 | These are visible in the drive website.
   | File authorization is revoked when the user deauthorizes the app.
   \ "drive.file"
   / Allows read and write access to the Application Data folder.
 4 | This is not visible in the drive website.
   \ "drive.appfolder"
   / Allows read-only access to file metadata but
 5 | does not allow any access to read or download file content.
   \ "drive.metadata.readonly"
scope&gt; 1
#权限，1即可
ID of the root folder
Leave blank normally.

Fill in to access "Computers" folders (see docs), or for rclone to use
a non root folder as its starting point.

Note that if this is blank, the first time rclone runs it will fill it
in with the ID of the root folder.

Enter a string value. Press Enter for the default ("").
root_folder_id&gt; 
#回车（默认）
Service Account Credentials JSON file path 
Leave blank normally.
Needed only if you want use SA instead of interactive login.
Enter a string value. Press Enter for the default ("").
service_account_file&gt; /root/accounts/05874f9b8fae7fe40f477fa95e6453e8522bc75f.json
#输入accounts目录下任意.json的路径！
Service Account Credentials JSON file path .

Enter a string value. Press Enter for the default ("").
service_account_file_path&gt; /root/accounts/
#输入accounts目录所在路径！
Edit advanced config? (y/n)
y) Yes
n) No (default)
y/n&gt; n
#回车（默认）
Remote config
Configure this as a team drive?
y) Yes
n) No (default)
y/n&gt; y
#如果你的是团队盘，则输入y，否则n
Fetching team drive list...
Choose a number from below, or type in your own value
 1 / 中转站！
   \ "0AOz4RIdA06URUk8PVA"
Enter a Team Drive ID&gt; 1
--------------------
[fz]
type = drive
scope = drive
service_account_file = /root/accounts/05874f9b8fae7fe40f477fa95e6453e8522bc75f.json
service_account_file_path = /root/accounts/
team_drive = 0AOz4RIdA06URUk8PVA
--------------------
y) Yes this is OK (default)
e) Edit this remote
d) Delete this remote
y/e/d&gt; y
#选y确认
Current remotes:

Name                 Type
====                 ====
fz                   drive

e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q&gt; q
#选q退出
[root ~]# 
</pre>
这样就配置完了！！！
<h2 style="text-align: center;">使用</h2>
复制：
<pre class="EnlighterJSRAW" data-enlighter-language="null">gclone copy gc:{目录1的id} gc:{目录2的id}  --drive-server-side-across-configs -v</pre>
<strong><span style="color: #ff0000;">注释：</span></strong>

<span style="color: #ff0000;"><strong>gc是配置gclone时的name</strong></span>

<span style="color: #ff0000;"><strong>目录1的id是要复制的文件的id</strong></span>

<span style="color: #ff0000;"><strong>目录2的id是复制文件的存放路径</strong></span>

<span style="color: #ff0000;"><strong>目录id可以是:普通目录，共享目录，团队盘。支持{目录id}后,跟后续路径，如：{目录id}/电影/喜剧/</strong></span>

<span style="color: #ff0000;"><strong><code>--drive-server-side-across-configs</code> 用于谷歌盘之间传输时使用，不走服务器流量，传输速度也更快</strong></span>

<span style="color: #ff0000;"><strong><code>-v</code> 用于查看传输过程的速度(不想查看可不加-v）</strong></span>

&nbsp;

同步：
<pre class="EnlighterJSRAW" data-enlighter-language="null">gclone sync gc:{目录1的id} gc:{目录2的id}  --drive-server-side-across-configs -v</pre>
<strong>用法和复制基本相同，用于同步两个目录。</strong>

&nbsp;

本地上传：
<pre class="EnlighterJSRAW" data-enlighter-language="null">gclone copy 本地文件或目录路径 gc:{目录的id} -v</pre>
&nbsp;

其他用法与rclone相同，用法包括但不限于本文提到的这几个，请自行挖掘。

&nbsp;

&nbsp;

&nbsp;