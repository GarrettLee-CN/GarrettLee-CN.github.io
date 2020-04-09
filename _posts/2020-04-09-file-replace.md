---
layout: post
title:  "Python自定义函数参数类型全解"
categories: Python
tags:  Python
author: GarrettLee
---

* content
{:toc}

> 在实际工作中，经常会涉及到需要去替换文件中某一个词，而传统的做法是：通过编辑软件中自带的“替换/查找”功能进行处理。但是如果涉及到成百上千个文件需要这样的处理，该怎么解决？本篇博文将介绍一种基于Python的解决方案。

## 1.读取文件夹中所有的文件名
Python中**os**库中**listdir**函数用于读取文件夹下的所有文件名，并返回出来列表。
```python
fileList = os.listdir(filename)
```
+ filename：需要批量替换内容文件所处的文件夹地址
+ fileList ：该文件夹下的所有文件名列表

## 2.读取文件内容并替换
正则表达式是将帮助我们完成符合要求字符串的替换，Python中**re**库是正则表达式库。
```python
def repfilecont(filepath,content,replacecontent):
		f=open(filepath,'r')
		alllines=f.readlines()
		f.close()
		f=open(filepath,'w+')
		for eachline in alllines:
			content=re.sub(content,replacecontent,eachline)
			f.writelines(content)
		f.close()
```
+ filepath：需要进行替换的文件名
+ content：需要替换的内容
+ replacecontent：替换的内容
如：**repfilecont(教育学部.txt,"天津师范大学",“天师大”)**
将教育学部.txt文件中"天津师范大学"替换成"天师大"
## 3.批量替换文件
```python
def repbatfilecont(filepath,content,replacecontent):
		filelist = File.readfilesname(filepath)
		content = content
		replacecontent = replacecontent
		for file in filelist:
			File.repfilecont(filepath+'/'+file,content,replacecontent)
			print(file+' 处理完毕！')
```
+ filepath：文件夹地址
+ content：需要替换的内容
+ replacecontent：替换的内容
## 4.调用函数
```python
File.repbatfilecont('C:\\Users\\Administrator\\Desktop\\test',"天津师范大学","天师大")
```
## 5.示例
![Markdown](https://imgconvert.csdnimg.cn/aHR0cDovL2kxLmZ1aW1nLmNvbS83MTIwNzEvNDUxYjE2ZmY2YzE4NjIxMS5wbmc?x-oss-process=image/format,png)
### 声明
上述原码来源于我编写的[oset开源库]((https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology))，该库旨在帮助教育研究者便捷处理日常科研、工作中遇到的问题。

作为一名**非科班出身**的教育技术学研究生，技术水平**十分有限**。近期看到教育工作者在处理数据是比较困难，包括本教育技术学的科研工作者在面对大批量数据时也是束手无策，于是萌生了为教育工作者写一个开源库的想法，意图通过简单的几行代码就可以完成诸如文件合并、字符云等复杂功能。[欢迎关注该项目](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology),如果有同学在此方面感兴趣和可以和我联系，我们一起维护该项目！

本人感兴趣的研究方向:**复杂系统计算**与**可解释性的深度学习**以及**自然语言处理**。微信公众号：**SMNLP**;个人博客:[www.litan.tech](http://www.litan.tech)。