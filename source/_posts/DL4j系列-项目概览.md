---
title: DL4j系列-项目概览
date: 2018-06-10 12:36:42
tags:
---


本文解读 DL4j的特点

- 官网
    - https://deeplearning4j.org/cn/index.html
    - https://deeplearning4j.org/index.html

- DL4j的overview资料
    - https://deeplearning4j.org/overview
    - https://deeplearning4j.org/cn/overview


DeepLearning4J（DL4J）是一套基于Java语言的神经网络工具包，可以构建、训练和部署神经网络。

- 特点: 
    - 基于java
    - 开源
    - 分布式, 可以和hadoop/spark集成
    - 可以和tensorflow/keras连接
    - 底层c++支持

# 基于java

大数据基础设施都是java系语言构建和工程化,对于很多已经投入大量的资金/人力投入的公司,想当然的模型的线上部署和服务应该以java为准.

# 开源
可以根据自己的业务/性能需求来修改和扩展代码,

# 分布式
将DL4j和spark进行集成,进行分布式训练,并可以连接生成训练数据的阶段,形成工作流: **Spark的准备数据 -> 处理清洗数据 -> 训练模型**

# python连接

可以形成工作流:  ** Hadoop/Spark积累训练数据 -> python训练 -> DL4j导入模型并部署**

# 性能

底层的向量矩阵计算由javacpp项目支持,即由JNI的方式调用c++代码,性能更高效


