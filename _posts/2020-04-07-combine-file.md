---
layout: post
title:  "Python自定义函数参数类型全解"
categories: Python
tags:  Python
author: GarrettLee
---

* content
{:toc}

> 教育研究中经常会遇到需要将许多访谈记录合并的情况。缺乏编程能力的老师或者同学需要不断复制、粘贴...不但耗时，而且容易存在遗漏复制文本等问题。本文给出我已经编写并且测试完成的函数，如果需要可以直接复制并使用。
> **注：**以下程序来源于我编写的教育技术开源库（oset），欢迎关注,感兴趣的同学可以和我联系，我们一起维护！[点击进入教育技术开源库](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology)

 ## 1 定义相关类
 ```python
class File:

	def readfile(filename):
		data = open(filename,'r',encoding = 'utf-8')
		return data.read()

	def readfilesname(filename):
		fileList = os.listdir(filename)
		return fileList
	
	def  combfile(filepath,**outpath):
		filelist = File.readfilesname(filepath)
		if outpath != {}:
			data = open(outpaht+'/combfile_Fin.txt','w+',encoding = 'utf-8')
		else:
			data = open(filepath+'/combfile_Fin.txt','w+',encoding = 'utf-8')
		for file in filelist:
			data.write(File.readfile(filepath+'/'+file)+'\n')
```	
在上述File类中：
+ readfile函数用于读取文件中的内容，并返回结果
+  readfilesname函数用于读取文件夹下所有子文件的文件名
+  combfile函数用于拼接所有文件，其中调用到上述两个函数
## 2 调用
```	python
File.combfile('C:\\Users\\Administrator\\Desktop\\test')
```
![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kyLnRpaW1nLmNvbS83MTIwNzEvNzg0MTZlMjE2YjAwMzVjYi5wbmc?x-oss-process=image/format,png)
作为一名**非科班出身**的教育技术学研究生，技术水平**十分有限**。近期看到教育工作者在处理数据是比较困难，包括本教育技术学的科研工作者在面对大批量数据时也是束手无策，于是萌生了为教育工作者写一个开源库的想法，意图通过简单的几行代码就可以完成诸如文件合并、字符云等复杂功能。[欢迎关注该项目](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology),如果有同学在此方面感兴趣和可以和我联系，我们一起维护该项目！

本人感兴趣的研究方向:**复杂系统计算**与**可解释性的深度学习**以及**自然语言处理**。微信公众号：**SMNLP**;个人博客:[www.litan.tech](http://www.litan.tech)。