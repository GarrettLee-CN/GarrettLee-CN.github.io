---
layout: post
title:  "2020-03-22阅读笔记-考虑遗忘机制的企业隐性知识传播SIR模型研究"
categories: 阅读笔记
tags:  复杂系统 知识传播 SIR模型
author: GarrettLee
---

* content
{:toc}

>本文系阅读上海工程技术大学杨湘浩等人发表在***中国管理科学***期刊上**《考虑遗忘机制的企业隐性知识传播SIR模型研究》**所做的笔记，由于本人水品有限，如理解存在偏差，还请批评指正。

## 1.文献综述

对于隐性知识的传播，首先介绍了SECI模型：该模型认为指出显性知识和隐性知识可以通过社会化、外部化、综合化和内部化的过程实现相互转化和传播。

![Markdown](http://i1.fuimg.com/712071/ed60e7fb95d10c3f.png)

后来随着经济发展，国内学者针对性的优化了该模型[1]，

![Markdown](http://i1.fuimg.com/712071/21b690addff08481.png)

![Markdown](http://i1.fuimg.com/712071/5591e5449715613f.png)

随后国内的相关学习又基于应用心理学的“顿悟学习”和“量子学习”模型的思想提出在顿悟学习基础之上的量子知识创造（Q-SECI）模型[2]。

![Markdown](http://i1.fuimg.com/712071/66f8b31473207fe6.png)

![Markdown](http://i1.fuimg.com/712071/176980c3aa7988a9.png)


在SIR与隐性知识传播研究理论之中，张生太以及王秀红等人认为组织隐性知识传播与传染病传播具有很多相似之处，据此构建了应用系统动力学构建了员工隐性知识传播的“传染病模型”并验证部分推断[3][4]。而对遗忘机制的引入是模型在真实环境中，由于隐性知识长期不得到复习或者受到外界感染而导致的遗忘，其中华中师范大学信息技术系瞿少成等人在研究小世界网络传播机制时考虑了遗忘机制，通过研究发现，考虑了遗忘机制的模型能更好的模拟组织学习网络显性知识的演化。[5]

## 2.模型内容与模型构建
### 2.1模型基本内容
本研究将知识传播者分为三类：学习者、传播者以及免疫者。
* 假设a.学习者以λ几率转化为传播者，开始传播隐性知识；而以1-λ的可能性转化为免疫者，不再参与考察的隐性知识传播。免疫者是指对考察的隐性知识失去兴趣或掌握后不使用也不传播，对考察的隐性知识传播不再产生影响。在传染病模型中会假设人接种疫苗后会对某种传染病产生免疫力，隐性知识的传播过程也是如此，不同的学习者由于不同的原因无法掌握知识而成为免疫者。而传播者由于对传播隐性知识的得益进行评估后，认向其他人传播其拥有的隐性知识是弊大于利的或者其他原因，那个该传播者也会成为免疫者。因此免疫者会有两个来源：一个是传播者一个是学习者。该模型如下图表示。

![Markdown](http://i1.fuimg.com/712071/1b671e3953479b71.png)

* 假设b.时间t内如果传播者因为遗忘导致其从传播者变为免疫者，其几率为δ；另外传播者由于受到免疫者影响也会转化为免疫者，所占据的比例约为η；当传播着与传播者相互交流时，会产生新的认识，对隐性知识产生新的评价，并转化为免疫者：几率为γ。此外假设在概率上存在以下假设：γ<η。

### 2.2数学模型构建
研究假设是建立在混合均匀网络中的，因此建立了平均场方程：

![Markdown](http://i1.fuimg.com/712071/4473dd0f2b302e33.png)

其中k表示网络平均度，I(t),S(t),R(t)分别表示t时刻学习者、传播者和免疫者。且满足：I(t)+S(t)+R(t)=1。假定在隐性知识传播初期只有一名传播者，其余都是学习者，因此可以将隐性知识传播模型的初始条件设置为：

![Markdown](http://i1.fuimg.com/712071/1a2b6da8a982c4e7.png)

## 3.模型推导
### 3.1模型稳态分析
![Markdown](http://i1.fuimg.com/712071/6cd835f7e9a4a16a.png)
![Markdown](http://i1.fuimg.com/712071/e82a8ca432657596.png)
![Markdown](http://i1.fuimg.com/712071/ae79f42e6588cb63.png)
![Markdown](http://i1.fuimg.com/712071/b06cf61e30635bc3.png)
![Markdown](http://i1.fuimg.com/712071/dc71dfb544d8deab.png)
![Markdown](http://i1.fuimg.com/712071/5533647db38b3d8f.png)
![Markdown](http://i1.fuimg.com/712071/c7a42207e880158b.png)

### 3.2仿真
采用Runge-Kuntt方法求解上述微分方程组，设定一下参数：N=10^4，平均度K=10的均匀网络，初始态仅一位传播者，即S(0)=1/10^4，I(0)=(10^4-1)/10^4,R(0)=0。仿真图像如下：
![Markdown](http://i2.tiimg.com/712071/6fc5c49624637c76.png)

## 引用
[1] 姚哲晖,胡汉辉.知识演化和创新的SECI模型之改进研究[J].中国软科学,2007(09):118-124.
[2] 褚建勋,汤书昆.基于顿悟学习的Q-SECI模型及其应用研究[J].科研管理,2007(04):95-99.
[3] 张生太,朱宏淼.人员流动对组织间隐性知识共享影响研究[J].管理科学学报,2016,19(07):78-84.
[4] 王秀红,韩琼,韩光平.员工隐性知识传播的系统动力学模型研究[J].情报杂志,2008(03):57-60.
[5] 瞿少成,李莎,田文汇.基于复杂网络理论的组织学习知识传播模型研究[J].华中师范大学学报(自然科学版),2009,43(04):573-577.

## 声明
作为一名**非科班出身**的教育技术学研究生，**理论水品十分有限**，阅读过程中难免存在理解上的**偏差**，还请各位同仁**批评指正**。目前从事的研究：**社会媒体计算**与**计算心理学**。个人感兴趣的方向（私下喜欢阅读的文献）：**复杂系网络计算**与**知识传播**，感兴趣的同学可以和我交流，互相学习。微信公众号：SMNLP;个人博客:www.litan.tech。如果发布的博文触及您的相关权益，请和我联系，我会及时删除和声明。