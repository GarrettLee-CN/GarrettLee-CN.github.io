---
layout: post
title:  "将GitHub上的项目克隆到本地并完成更新并上传"
categories: GitHub
tags:  GitHub
author: GarrettLee
---

* content
{:toc}

> GitHub是一个面向开源及私有软件项目的托管平台，因为只支持git 作为唯一的版本库格式进行托管，故名GitHub。GitHub于2008年4月10日正式上线，除了Git代码仓库托管及基本的 Web管理界面以外，还提供了订阅、讨论组、文本渲染、在线文件编辑器、协作图谱（报表）、代码片段分享（Gist）等功能。托管版本数量也是非常之多，其中不乏知名开源项目 Ruby on Rails、jQuery、python 等。[1]是科研和技术人员的理想代码托管平台；本博客首先阐述如何在GitHub上创建一个项目，然后讲述如何将该项目下载到本地，最后阐述如何完成更新，并上传。

## 1.在GitHub上创建一个项目
> 首先需要注册一个github的账号，这里不再赘述了，直接进入正题。

+ **1.1 进入首页，点击左上角的New，进入创建项目页面**

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvYmVjMWFiNTgzODdiZjY4My5wbmc?x-oss-process=image/format,png)

+ **1.2 进入项目信息页面，填写先关项目信息并创建**

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kyLnRpaW1nLmNvbS83MTIwNzEvZWUyMTk2MTFlM2FmMDRjMC5wbmc?x-oss-process=image/format,png)

**如果是新建库请将下面的Initialize this repository with a README**勾选上，如果已经存在一个现成的库，则跳过此步骤。

+ **1.3 创建完毕**

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kyLnRpaW1nLmNvbS83MTIwNzEvN2MxYTNiOWExZTJmNjcyNC5wbmc?x-oss-process=image/format,png)

## 2.将该空项目克隆到本地
> 这里拟需要下载一个git工具，下载地址：https://gitforwindows.org/；随后在本地创建一个文件夹用于保存克隆下的项目。
+ **2.1 进入项目空间，点击“克隆与下载”，并复制项目的下载链接** 

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvYzAzOTMwNzMxOWRiMjc3ZS5wbmc?x-oss-process=image/format,png)

+ **2.2 在本地准备保存项目的地方，新建文件夹，进入git**

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kyLnRpaW1nLmNvbS83MTIwNzEvNWMxODU5YzVlNzc3NjMzMi5wbmc?x-oss-process=image/format,png)

+ **2.3 在git中输入 git clone XXXXXXXX（其中XXXXXX为2.1复制的克隆链接）**

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvZTJiNGFiY2EzNTJjMzJiOS5wbmc?x-oss-process=image/format,png)
随后会自动下载，下完完成后如下图所示：
![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvNGMzMDc3YzcwN2Q5MjU2ZS5wbmc?x-oss-process=image/format,png)

## 3.更新文件并上传
+ **3.1 更新文件**
![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvMjNhYmIyODA1YTJhM2ZlNi5wbmc?x-oss-process=image/format,png)

+ **3.2 与上述2.2步骤一样，进入git，一步步输入以下命令：**

 git add .
 
 git commit -m "你的备注"

 git push

![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvYmU1NWIyM2M4NmZjZWFjMi5wbmc?x-oss-process=image/format,png)
**其中git push以后会有弹框，让你输入github的用户名和密码**

+ **3.3 进入github仓库，文件已经更新完毕**
![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kyLnRpaW1nLmNvbS83MTIwNzEvM2MxYWRjNzZmMzUxMmI5Mi5wbmc?x-oss-process=image/format,png)

## 引用
[1] https://baike.baidu.com/item/github/10145341?fr=aladdin

作为一名**非科班出身**的教育技术学研究生，技术水平**十分有限**，近期看到教育工作者在处理数据是比较困难，包括本教育技术学的科研工作者在面对大批量数据时也是束手无策，于是萌生了为教育工作者写一个开源库的想法，意图通过简单的几行代码就可以完成诸如文件合并、字符云等复杂功能。[欢迎关注该项目](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology),如果有同学在此方面感兴趣和可以和我联系，我们一起维护该项目！

本人感兴趣的研究方向:**复杂系统计算**与**可解释性的深度学习**以及**自然语言处理**。微信公众号：**SMNLP**;个人博客:[www.litan.tech](http://www.litan.tech)。