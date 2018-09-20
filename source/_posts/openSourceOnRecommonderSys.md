---
title: 〆 个性化推荐系统开源项目一览
date: 2018-06-25 11:43:51
categories: "Recommender System"
tags:
  - Technology
  - Recommender
  - Open Source Project
---

**<font color="#5A5AAD">I have found it worth living, and would gladly live it again if the chance were offered me. </font>**

## <font color="#FF5151">Open Source Project: </font>整理了关于目前市场上个性化推荐系统的一些开源项目。
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[主要语言] C++/java</font>
<!--more-->

### 1.SVDFeature

主页：[SVDFeature - SVDFeature](http://apex.sjtu.edu.cn/projects/33) 语言：C++
一个feature-based协同过滤和排序工具，由上海交大Apex实验室开发，代码质量较高。在KDD Cup 2012中获得第一名，KDD Cup 2011中获得第三名，相关论文 发表在2012的JMLR中，这足以说明它的高大上。SVDFeature包含一个很灵活的Matrix Factorization推荐框架，能方便的实现SVD、SVD++等方法, 是单模型推荐算法中精度最高的一种。SVDFeature代码精炼，可以用 相对较少的内存实现较大规模的单机版矩阵分解运算。另外含有Logistic regression的model，可以很方便的用来进行ensemble。

### 2.LibMF

主页：[LIBMF: A Software for Matrix Factorization for Recommender Systems](https://www.csie.ntu.edu.tw/~cjlin/libmf/) 语言：C++
作者Chih-JenLin来自大名鼎鼎的台湾国立大学，他们在机器学习领域享有盛名，近年连续多届KDD Cup竞赛上均 获得优异成绩，并曾连续多年获得冠军。台湾大学的风格非常务实，业界常用的LibSVM， Liblinear等都是他们开发的，开源代码的效率和质量都非常高。LibMF在矩阵分解的并行化方面作出了很好的贡献，针对SGD（随即梯度下降）优化方法在并行计算中存在的locking problem和memory discontinuity问题，提出了一种 矩阵分解的高效算法FPSGD（Fast Parallel SGD），根据计算节点的个数来划分评分矩阵block，并分配计算节点。系统介绍可以见这篇 论文（ACM Recsys 2013的 Best paper Award）。

### 3.LibFM

主页：[libFM](http://www.libfm.org/) 语言：C++
作者是德国Konstanz大学的Steffen Rendle，他用LibFM同时玩转KDD Cup 2012 Track1和Track2两个子竞赛单元，都取得了很好的成绩，说明LibFM是非常管用的利器。LibFM是专门用于矩阵分解的利器，尤其是其中实现了MCMC（Markov Chain Monte Carlo）优化算法，比常见的SGD优化方法精度要高，但运算速度要慢一些。当然LibFM中还 实现了SGD、SGDA（Adaptive SGD）、ALS（Alternating Least Squares）等算法。

### 4.Lenskit

主页：[LensKit Recommender Toolkit](http://lenskit.org/) 语言Java
这个Java开发的开源推荐系统，来自美国的明尼苏达大学的GroupLens团队，也是推荐领域知名的测试数据集Movielens的作者。该源码托管在GitHub上，lenskit/lenskit · GitHub。主要包含lenskit-api,lenskit-core, lenskit-knn,lenskit-svd,lenskit-slopone,lenskit-parent,lenskit-data-structures,lenskit-eval,lenskit-test等模块，主要实现了k-NN，SVD，Slope-One等 典型的推荐系统算法。

### 5.GraphLab

主页：[GraphLab - Collaborative Filtering](https://turi.com/products/create/docs/index.html) 语言：C++
Graphlab是基于C++开发的一个高性能分布式graph处理挖掘系统，特点是对迭代的并行计算处理能力强（这方面是hadoop的弱项），由于功能独到，GraphLab在业界名声很响。 用GraphLab来进行大数据量的random walk或graph-based的推荐算法非常有效。Graphlab虽然名气比较响亮（CMU开发），但是对一般数据量的应用来说可能还用不上。GraphLab主要实现了ALS，CCD++，SGD，Bias-SGD，SVD++，Weighted-ALS，Sparse-ALS，Non-negative Matrix Factorization，Restarted Lanczos Algorithm等算法。

### 6.Mahout

主页：[Apache Mahout: Scalable machine learning and data mining](http://mahout.apache.org/) 语言：Java
Mahout 是 Apache Software Foundation (ASF) 开发的一个全新的开源项目，其主要目标是创建一些可伸缩的机器学习算法，供开发人员在 Apache 在许可下免费 使用。Mahout项目是由 Apache Lucene社区中对机器学习感兴趣的一些成员发起的，他们希望建立一个可靠、文档翔实、可伸缩的项目，在其中实现一些常见的用于 聚类和分类的机器学习算法。该社区最初基于 Ngetal. 的文章 “Map-Reduce for Machine Learning on Multicore”，但此后在发展中又并入了更多广泛的机器学习 方法，包括Collaborative Filtering（CF），Dimensionality Reduction，Topic Models等。此外，通过使用 Apache Hadoop 库，Mahout 可以有效地扩展到云中。在Mahout的Recommendation类算法中，主要有User-Based CF，Item-Based CF，ALS，ALS on Implicit Feedback，Weighted MF，SVD++，Parallel SGD等。

### 7.Myrrix

主页：[http://myrrix.com/](http://myrrix.com/) 语言：Java
Myrrix最初是Mahout的作者之一Sean Owen基于Mahout开发的一个试验性质的推荐系统。目前Myrrix已经是一个完整的、实时的、可扩展的集群和推荐系统，主要 架构分为两部分：服务层：在线服务，响应请求、数据读入、提供实时推荐；计算层：用于分布式离线计算，在后台使用分布式机器学习算法为服务层更新机器学习 模型。Myrrix使用这两个层构建了一个完整的推荐系统，服务层是一个HTTP服务器，能够接收更新，并在毫秒级别内计算出更新结果。服务层可以单独使用，无需 计算层，它会在本地运行机器学习算法。计算层也可以单独使用，其本质是一系列的Hadoop jobs。目前Myrrix以被 Cloudera 并入Oryx项目。

### 8.EasyRec

主页：[easyrec :: open source recommendation engine](http://easyrec.org/) 语言：Java
EasyRec是一个易集成、易扩展、功能强大且具有可视化管理的推荐系统，更像一个完整的推荐产品，包括了数据录入模块、管理模块、推荐挖掘、离线分析等。 EasyRec可以同时给多个不同的网站提供推荐服务，通过tenant来区分不同的网站。架设EasyRec服务器，为网站申请tenant，通过tenant就可以很方便的集成到 网站中。通过各种不同的数据收集（view,buy.rating）API收集到网站的用户行为，EasyRec通过离线分析，就可以产生推荐信息，您的网站就可以通过 Recommendations和Community Rankings来进行推荐业务的实现。

### 9.Waffles

主页：[http://waffles.sourceforge.net/](http://waffles.sourceforge.net/) 语言：C++
Waffles英文原意是蜂蜜甜饼，在这里却指代一个非常强大的机器学习的开源工具包。Waffles里包含的算法特别多，涉及机器学习的方方面面，推荐系统位于 其中的Waffles_recommend tool，大概只占整个Waffles的1/10的内容，其它还有分类、聚类、采样、降维、数据可视化、音频处理等许许多多工具包，估计 能与之媲美的也就数Weka了。

### 10.RapidMiner

主页：[Predictive Analytics, Data Mining, Self-service, Open source](https://rapidminer.com/) 语言：Java
RapidMiner（前身是Yale）是一个比较成熟的数据挖掘解决方案，包括常见的机器学习、NLP、推荐、预测等方法（推荐只占其中很小一部分），而且带有GUI的 数据分析环境，数据ETL、预处理、可视化、评估、部署等整套系统都有。另外RapidMiner提供commercial license，提供R语言接口，感觉在向着一个商用的 数据挖掘公司的方向在前进。

### 11.surpriselib

主页：[surpriselib](http://surpriselib.com/) 语言：Python
Surprise is a Python scikit building and analyzing recommender systems.
Surprise was designed with the following purposes in mind:
> Give users perfect control over their experiments. To this end, a strong emphasis is laid on documentation, which we have tried to make as clear and precise as possible by pointing out every detail of the algorithms.
> Alleviate the pain of Dataset handling. Users can use both built-in datasets (Movielens, Jester), and their own custom datasets.
> Provide various ready-to-use prediction algorithms such as baseline algorithms, neighborhood methods, matrix factorization-based ( SVD, PMF, SVD++, NMF), and many others. Also, various similarity measures (cosine, MSD, pearson…) are built-in.
> Make it easy to implement new algorithm ideas.
> Provide tools to evaluate, analyse and compare the algorithms performance. Cross-validation procedures can be run very easily using powerful CV iterators (inspired by scikit-learn excellent tools), as well as exhaustive search over a set of parameters.

### 12 LibRec

主页：[LibRec](https://github.com/guoguibing/librec)国内推荐系统大牛，创办了推荐系统开源项目LibRec。java版本开源推荐系统，包含了70多种经典的推荐算法。


### 13 Recommender-System

python版本开源推荐系统，包含了多种经典的推荐算法。

### 14 Neural Collaborative Filtering

python实现神经协同过滤推荐算法。
