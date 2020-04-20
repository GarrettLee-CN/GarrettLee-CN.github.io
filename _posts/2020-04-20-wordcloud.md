---
layout: post
title:  "Python实现文件的字符云"
categories: Python
tags:  Python
author: GarrettLee
---

* content
{:toc}

> 教育研究中，有时需要对一个文档进行可视化展示——字符云。而有时还需要对多个文档内容合并进行可视化展示。本文首先给出通过调用[oset（教育技术开源库）](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology)实现字符云最简单的方式（见第2小节）;随后将介绍[oset](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology)中实现该原理的源码，供有需要的同学研究和二次开发。

## 1.文件夹内容展示
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200420162838731.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMyODYzNTQ5,size_16,color_FFFFFF,t_70)
## 2.字符云展示
### 2.1单个文件字符云可视化
```python
#如仅仅对上述文件夹中“教育学部.txt”文件进行可视化展示
from oset import Chineseword
Chineseword.wordcloud('C:\\Users\\Administrator\\Desktop\\test\\教育学部.txt')
```
**可视化结果如下：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200420161246101.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMyODYzNTQ5,size_16,color_FFFFFF,t_70)
### 2.1多个文件字符云可视化
```python
#将test文件夹中所有的
from oset import Chineseword
Chineseword.wordcloud('C:\\Users\\Administrator\\Desktop\\test')
```
**可视化结果如下：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200420162528934.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMyODYzNTQ5,size_16,color_FFFFFF,t_70)
## 3.wordcloud()函数源码
**所有的原码以及原理说明，请见下面代码中的注释：**
```python
def wordcloud(filepath):
       '''判断出是否为单个文件还是存有多个文件的文件夹，
		  如果是多个文件则调用oset库中File类combfile()函数
		  首先实现文件合并,并读取合并后文件内容。无论是单个文
		  件还是多个文件合并后的结果，均通过sentence变量存取
		  文档的结果'''
		try:
			File.combfile(filepath)
			sentence=File.readfile(filepath+'\\combfile_Fin.txt')
		except:
			sentence=File.readfile(filepath)
			filepath = os.path.dirname(filepath)
		'''调用oset库中，Chineseword类的cutword函数，实现
		   对文件的分词，并将sentence承接'''
		sentence=Chineseword.cutword(sentence)
		'''通过wordcount函数实现对分词后文档词频进行统计，
		并以字典形式返回'''
		worddict=Chineseword.wordcount(sentence)
		keylist,valuelist = worddict.keys(),worddict.values()
		outputFile = filepath+'\\osetwordcloud.html'
		'''调用pyecharts库中WordCloud函数实现字符云绘制'''
		cloud = WordCloud('wordcloud', width=1000, height=600)
		cloud.add(
			' ',keylist,valuelist,
			shape='circle',
			)
		cloud.render(outputFile)
```
### 声明
上述原码来源于我编写的[oset开源库]((https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology))，该库旨在帮助教育研究者便捷处理日常科研、工作中遇到的问题。

作为一名**非科班出身**的教育技术学研究生，技术水平**十分有限**。近期看到教育工作者在处理数据是比较困难，包括本教育技术学的科研工作者在面对大批量数据时也是束手无策，于是萌生了为教育工作者写一个开源库的想法，意图通过简单的几行代码就可以完成诸如文件合并、字符云等复杂功能。[欢迎关注该项目](https://github.com/GarrettLee-CN/Open-Source-Program-for-Educational-Technology),如果有同学在此方面感兴趣和可以和我联系，我们一起维护该项目！

本人感兴趣的研究方向:**复杂系统计算**与**可解释性的深度学习**以及**自然语言处理**。微信公众号：**SMNLP**;个人博客:[www.litan.tech](http://www.litan.tech)。