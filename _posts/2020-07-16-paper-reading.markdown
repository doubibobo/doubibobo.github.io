---
layout: post
title:  "论文阅读笔记"
date:   2020-07-16 19:46:33 +0800
categories: jekyll update
---
### __文章一：Memory Fusion Network for Multi-view Sequential Learning[@Zadeh2018]__
> 2018年AAAI会议文章，主要工作是构造了针对多模态数据的MFN  

#### __Basic concepts__
多模态的序列学习包括两个过程
1. ***view-specific interactions*** that handle only one view  
2. ***cross-view interactions*** which are defined across different views and need to handle multi-views

so, the modeling of view-specific interactions and cross-view interactions is the ***core question*** of multi-view sequential learning[@Zadeh2018]

文章将多模态学习分为三类，基本思路是将不同模态下的特征向量映射到同一个特征子空间
1. the first category of models have relied on concatenation of all multiple views into a single view to simplify the learning setting  
> **思路：**通过将不同模态映射到某个单一模态来获得**input层次**的级联，再送入神经网络进行学习，得到特征向量  
> **问题：**简单的级联忽视了不同模态的数据本来就有专属特征  
2. the second category of models introduce multi-view variants to the structured learning approaches of the first category
> **思路：**对第一种的改进，单独学习每个模态的特征向量，是**特征层次**上的级联  
> **问题：**  *特征向量的级联*，如$${v}, {a}, {l} -> {v, a, l}$$并没有做到真正的数据融合  
3. the third category of models rely on collapsing the time dimension from sequences by learning a temporal representation for each of the different views.
> **思路：** 按照时间维度融合多模态的数据，融合后的特征向量是几个模态的平均，是**特征层次**上的级联，是*modality fusion*，或者通过voting的方式获取结果
>> my question: I don't think that combining models by voting is a fusion method which should do fusion before generating decision, but the author classified it to the thrid category.  

> **问题：** 平均的方式掩盖了不同模态之间的差异性

#### __Motivation__

#### __Innovation__

#### __DataSets__

Memory Fusion Network (MFN) 由三部分构成：
1. __the Systems of LSTMs for view-specific interactions__
2. __a special attention mechanism for cross-view interactions(DMAN)__ 
3. __Multi-view Gated Memory for summarization__

### 文章二：Tensor Fusion Network for Multimodal Sentiment Analysis.

这是普通的文字

#### 论文笔记前传

![LSTM结构单元示意图]({{site.url}}/image/LSTM-constructor.jpeg)

![结构一]({{site.url}}/image/2020-07-16 20-29-10.png)

![结构二]({{site.url}}/image/2020-07-16 20-30-18.png)

