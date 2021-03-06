---
title: 〆 推荐算法实战 项亮
date: 2018-09-12 15:20:23
categories: "Book Notes"
tags:
  - Technology
  - Recommender
    Arithmetic
---

**<font color="#5A5AAD">⚠  The best of all ways to strengthen our days is to steal hours from the night.   </font>**

## <font color="#FF5151">Step One: </font>enviroment -- python3.7

<!--more-->

# 评测指标

### 数据集分类

一般的，数据集分成四类

> - 系统检索到的相关文档（A）
> - 系统检索到的不相关文档（B）
> - 相关但是系统没有检索到的文档（C）
> - 不相关且没有被系统检索到的文档（D）

### 评测指标

> 用户满意度
> 预测准确度
>> 评分预测
>> TopN 预测 
> 覆盖率
> 多样性
> 新颖性
> 惊喜度
> 信任度
> 实时性
> 健壮性
> 商业目标

#### 评分预测

评分预测的预测准确度一般通过均方根误差（RMSE）和平均绝对误差（MAE）计算。

**关于RMSE和MAE这两个指标的优缺点， Netflix认为RMSE加大了对预测不准的用户物品评分的惩罚（平方项的惩罚），因而对系统的评测更加苛刻。研究表明，如果评分系统是基于整数建立的（即用户给的评分都是整数），那么对预测结果取整会降低MAE的误差。**

#### TopN预测

**网站在提供推荐服务时，一般是给用户一个个性化的推荐列表，这种推荐叫做TopN推荐。TopN推荐的预测准确率一般通过准确率（precision）/召回率（recall）度量。**

**注意** ：有的时候，为了全面评测TopN推荐的准确率和召回率，一般会选取不同的推荐列表长度N，计算出一组准确率/召回率，然后画出准确率/召回率曲线（precision/recall curve）。

#### 覆盖率

##### 长尾理论

长尾理论生动而形象地反映了我们的经济和文化，正在产生从为数较少的主流产品和市场（需求曲线的头部）向数量众多的狭窄市场（需求曲线的尾部）转移的现象和趋势。其基本原理是：只要存储和流通的渠道足够大，需求不旺或销量不佳的产品所共同占据的市场份额可以和那些少数热销产品所占据的市场份额相匹敌，甚至有过之而无不及。

**覆盖率（coverage）描述一个推荐系统对物品长尾的发掘能力。覆盖率有不同的定义方法，
最简单的定义为推荐系统能够推荐出来的物品占总物品集合的比例。**

注意: 覆盖率为100%的推荐系统可以将每个物品都推荐给至少一个用户。

通过研究物品在推荐列表中出现次数的分布描述推荐系统挖掘长尾的能力。如果这个分布比
较平，那么说明推荐系统的覆盖率较高，而如果这个分布较陡峭，说明推荐系统的覆盖率较低。
在信息论和经济学中有两个著名的指标可以用来定义覆盖率。

> 信息熵
> 基尼因数

##### 基尼因数原理

设实际收入分配曲线和收入分配绝对平等曲线之间的面积为A，实际收入分配曲线右下方的面积为B。并以A除以（A+B）的商表示不平等程度。这个数值被称为基尼系数或称洛伦茨系数。如果A为零，基尼系数为零，表示收入分配完全平等；如果B为零则系数为1，收入分配绝对不平等。收入分配越是趋向平等，洛伦茨曲线的弧度越小，基尼系数也越小，反之，收入分配越是趋向不平等，洛伦茨曲线的弧度越大，那么基尼系数也越大。另外，可以参看帕累托指数(是指对收入分布不均衡的程度的度量）。

##### 洛伦兹曲线

洛伦兹曲线（Lorenz curve），也译为“劳伦兹曲线”。就是，在一个总体（国家、地区）内，以“最贫穷的人口计算起一直到最富有人口”的人口百分比对应各个人口百分比的收入百分比的点组成的曲线。

# <font style="color: blue;font-weight: bold;font-size: 16px;">不理解:</font>
<选择累积数量作为x轴的原因: 是因为连续性需要吗？>

##### 马太效应

社会学领域有一个著名的马太效应，即所谓强者更强，弱者更弱的效应。如果一个系统会增
大热门物品和非热门物品的流行度差距，让热门的物品更加热门，不热门的物品更加不热门，那
么这个系统就有马太效应。  -- 搜索引擎的PageRank算法也具有一定的马太效应。

推荐系统的初衷是希望消除马太效应，使得各种物品都
能被展示给对它们感兴趣的某一类人群。但是，很多研究表明现在主流的推荐算法（比如协同过
滤算法）是具有马太效应的。评测推荐系统是否具有马太效应的简单办法就是使用基尼系数。如
果G1是从初始用户行为中计算出的物品流行度的基尼系数，G2是从推荐列表中计算出的物品流
行度的基尼系数，那么如果G2 > G1，就说明推荐算法具有马太效应。
数值大，代表分布不平衡差距更大，所以，等于增大了变化度，所以具有马太效应。

#### 多样性

**尽管用户的兴趣在较长的时间跨度中是一样的，但具体到用户访问推荐系统的某一刻，
其兴趣往往是单一的，那么如果推荐列表只能覆盖用户的一个兴趣点，而这个兴趣点不是用户这
个时刻的兴趣点，推荐列表就不会让用户满意。反之，如果推荐列表比较多样，覆盖了用户绝大
多数的兴趣点，那么就会增加用户找到感兴趣物品的概率。因此给用户的推荐列表也需要满足用
户广泛的兴趣，即具有多样性。**

# <font style="color: blue;font-weight: bold;font-size: 16px;">不理解:</font> 多样性描述了推荐列表中物品两两之间的不相似性。因此，多样性和相似性是对应的。假设si j ( , ) [0,1]  定义了物品i和j之间的相似度，那么用户u的推荐列表R(u)的多样性

多样性通俗解析: 可以提供4种不同的推荐列表：

> A列表中有10部动作片，没有动画片；
> B列表中有10部动画片，没有动作片；
> C列表中有8部动作片和2部动画片；
> D列表有5部动作片和5部动画片。

在这个例子中，一般认为C列表是最好的，因为它具有一定的多样性，但又考虑到了用户的主要兴趣。A满足了用户的主要兴趣，但缺少多样性，D列表过于多样，没有考虑到用户的主要兴趣。B列表即没有考虑用户的主要兴趣，也没有多样性，因此是最差的。

#### 新颖性

**新颖的推荐是指给用户推荐那些他们以前没有听说过的物品。**

<font style="color: red;">如何在不牺牲精度的情况下提高多样性和新颖性</font>

#### 惊喜度

**如果推荐结果和用户的历史兴趣不相似，但却让用户觉得满意，那么就可以说推荐结果的惊喜度很高，而推荐的新颖性仅仅取决于用户是否听说过这个推荐结果。**

#### 信任度

**提高推荐系统的信任度主要有两种方法。首先需要增加推荐系统的透明度（transparency），而增加推荐系统透明度的主要办法是提供推荐解释。只有让用户了解推荐系统的运行机制，让用户认同推荐系统的运行机制，才会提高用户对推荐系统的信任度。其次是考虑用户的社交网络信息，利用用户的好友信息给用户做推荐，并且用好友进行推荐解释。这是因为用户对他们的好友一般都比较信任，因此如果推荐的商品是好友购买过的，那么他们对推荐结果就会相对比较信任。**

#### 实时性

推荐系统的实时性包括两个方面。

> 首先，推荐系统需要实时地更新推荐列表来满足用户新的行为变化。比如，当一个用户购买了iPhone，如果推荐系统能够立即给他推荐相关配件，那么肯定比第二天再给用户推荐相关配件更有价值。很多推荐系统都会在离线状态每天计算一次用户推荐列表，然后于在线期间将推荐列表展示给用户。这种设计显然是无法满足实时性的。与用户行为相应的实时性，可以通过推荐列表的变化速率来评测。如果推荐列表在用户有行为后变化不大，或者没有变化，说明推荐系统的实时性不高。
> 实时性的第二个方面是推荐系统需要能够将新加入系统的物品推荐给用户。这主要考验了推荐系统处理物品冷启动的能力。关于如何将新加入系统的物品推荐给用户，本书将在后面的章节进行讨论，而对于新物品推荐能力，我们可以利用用户推荐列表中有多大比例的物品是当天新加的来评测。

#### 健壮性

**任何一个能带来利益的算法系统都会被人攻击，这方面最典型的例子就是搜索引擎。搜索引擎的作弊和反作弊斗争异常激烈，这是因为如果能让自己的商品成为热门搜索词的第一个搜索果，会带来极大的商业利益。推荐系统目前也遇到了同样的作弊问题，而健壮性（即robust,鲁棒性）指标衡量了一个推荐系统抗击作弊的能力。**

常见的健壮性的体现：

> 设计推荐系统时尽量使用代价比较高的用户行为。比如，如果有用户购买行为和用户浏览行为，那么主要应该使用用户购买行为，因为购买需要付费，所以攻击购买行为的代价远远大于攻击浏览行为。
> 在使用数据前，进行攻击检测，从而对数据进行清理。

#### 商业目标

***设计推荐系统时需要考虑最终的商业目标，而网站使用推荐系统的目的除了满足用户发现内容的需求，也需要利用推荐系统加快实现商业上的指标。**

### 总结

如何优化离线指标来提高在线指标是推荐系统研究的重要问题：
离线实验的优化目标是：

> 最大化预测准确度
> 使得 覆盖率 > A
> 多样性 > B
> 新颖性 > C


## 评测维度

**在评测系统中还需要考虑评测维度，比如一个推荐算法，虽然整体性能不好，但可能在某种情况下性能比较好，而增加评测维度的目的就是知道一个算法在什么情况下性能最好。这样可以为融合不同推荐算法取得最好的整体性能带来参考。**

常见的评测纬度分类:

> 用户维度 主要包括用户的人口统计学信息、活跃度以及是不是新用户等。
> 物品维度 包括物品的属性信息、流行度、平均分以及是不是新加入的物品等。
> 时间维度 包括季节，是工作日还是周末，是白天还是晚上等。

# 利用用户行为数据

著名的 啤酒与尿布 故事

用户行为数据中蕴涵着很多不是那么显而易见的规律，而个性化推荐算法的任务就是通过计算机去发现这些规律，从而为产品的设计提供指导，提高用户体验。

**基于用户行为分析的推荐算法是个性化推荐系统的重要算法，学术界一般将这种类型的算法称为协同过滤算法。顾名思义，协同过滤就是指用户可以齐心协力，通过不断地和网站互动，使自己的推荐列表能够不断过滤掉自己不感兴趣的物品，从而越来越满足自己的需求。**

## 用户行为数据简介

用户行为在个性化推荐系统中一般分两种——显性反馈行为（explicit feedback）和隐性反馈
行为（implicit feedback）。

有代表性的数据集主要分类为:

> 无上下文信息的隐性反馈数据集每一条行为记录仅仅包含用户ID和物品ID。Book-Crossing就是这种类型的数据集。
> 无上下文信息的显性反馈数据集 每一条记录包含用户ID、物品ID和用户对物品的评分。
> 有上下文信息的隐性反馈数据集 每一条记录包含用户ID、物品ID和用户对物品产生行为的时间戳。Lastfm数据集就是这种类型的数据集。
> 有上下文信息的显性反馈数据集 每一条记录包含用户ID、物品ID、用户对物品的评分和评分行为发生的时间戳。Netflix Prize提供的就是这种类型的数据集。

协同过滤算法的方法常见的有:

> 基于邻域的方法（neighborhood-based）
> 隐语义模型（latent factor model）
> 基于图的随机游走算法（random walk on graph）等。在这些方法中，

最著名的、在业界得到最广泛应用的算法是基于邻域的方法，而基于邻域的方法主要包含下
面两种算法。

> 基于用户的协同过滤算法 这种算法给用户推荐和他兴趣相似的其他用户喜欢的物品。
> 基于物品的协同过滤算法 这种算法给用户推荐和他之前喜欢的物品相似的物品。

### 基于于用户的协同过滤算法

> (1) 找到和目标用户兴趣相似的用户集合。
> (2) 找到这个集合中的用户喜欢的，且目标用户没有听说过的物品推荐给目标用户。

