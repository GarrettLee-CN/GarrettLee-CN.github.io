---
layout: post
title:  "2020-03-13阅读笔记"
categories: 阅读笔记
tags:  SIR模型 情绪 社交媒体
author: GarrettLee
---

* content
{:toc}


## 经典SIR模型

![SIR模型](http://i1.fuimg.com/712071/4005775c83695a6c.png)

该模型中S表示易感者，I表示染病者，R表示恢复者。在该模型中有这几个限定：a.恢复者不再出现被感染情况；b.该模型所在的系统中总人数K不变化。
因此我们可以将S，I，R认为是一个随着时间t变化的函数：S(t)、I(t)、R(t)。

1.满足上述限定b的定义，还需要满足：S（t）+I(t)+R(t)=K；

2.t时刻假定一个染病者可以将该病毒传染给易感者的数目与该系统内易感者数目存在正相关，且传染率为β，则I(t)个传染者的感染数目为：βS(t)I(t)；

3.t时刻从感染者转化为恢复者的数量认为与感染者存在正比关系，恢复率为γ，则t时刻恢复者数量为γI(t)；

因此在这个系统中，可以存在这样一个机制：易感人数和感染人数以及感染系数共同作用于易感者人数；感染者人数又受到恢复系数和感染人数影响。但是这是一个单向的系统，即恢复者不再是具有易感性。因此得出下面几个变化率：

1.易感个体数下降率：-βS(t)I(t)；

2.感染个体的增长率为：βS(t)I(t)-γI(t)；

3.恢复个体增长率：γI(t)；

因此可以构建这样一个微分方程：
![SIR微分方程](http://i1.fuimg.com/712071/2908bc0b195bf4d1.png)


## 声明
笔记仅代表个人对该论文的阅读后理解，由于笔者理论水品十分有限，阅读过程中难免存在理解上的偏差，还请各位同仁批评指正。