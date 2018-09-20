---
title: 〆 template [important key]
date: 2018-01-18 16:08:31
categories: "Template"
tags:
  - Technology
  - Template
  - tags1
---

**<font color="#5A5AAD">A pearl is a temple built by pain around a grain of sand.</font>**

## <font color="#FF5151">How to study RS: </font>整理了一些学习推荐系统的相关文献和书籍资料。
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[主要语言] C++/java</font>

<!--more-->

# Ochuunn

## 特点
* 文章界面很清晰，很适合阅读~
* Google Search Console
* Google Analytics
* [LiveRe](https://livere.com/) (我去掉了disqus, 国内不翻墙压根连不上)
* 打赏
*   页面滚动快捷键 (j, k, t, b, n, m 具体功能自己尝试, console 有提示~)

## Demo
[I am Oliver](http://ochukai.me)

![你想输入的替代文字](template/avatar.jpg)
# ⚠ 这里很重要

```sh
npm install hexo-renderer-pug --save
```

## Install

1. In the `root` directory:

```git
$ git clone https://github.com/ochukai/hexo-theme-ochuunn.git themes/ochuunn
```

2. Change the `theme` property in the `config.yml` file.

```yml
# theme: landscape
theme: ochuunn
```

## 不足

* 不支持 link 类型的文章
* 不支持 category，只有 tag

(在目录的最下面， 是 hexo 的测试文章，按 b 键直达~)

.ignore
git提交时过滤掉不需要提交的文件，很方便，有些本地文件是不需要提交到Git上的。

CamelCase
将不是驼峰格式的名称，快速转成驼峰格式，安装好后，选中要修改的名称，按快捷键shift+alt+u。

Lombok plugin
开发神器，可以简化你的实体类，让你i不再写get/set方法，还能快速的实现builder模式，以及链式调用方法，总之就是为了简化实体类而生的插件。

Mybatis plugin
可以在mapper接口中和mapper的xml文件中来回跳转，就想接口跳到实现类那样简单。

codehelper.generator
可以让你在创建一个对象并赋值的时候，快速的生成代码，不需要一个一个属性的向里面set,根据new关键字，自动生成掉用set方法的代码，还可以一键填入默认值。

GenAllSetter 特性

在Java方法中, 根据 new 关键词, 为Java Bean 生成所有Setter方法。
按GenAllSetter键两次, 会为Setter方法生成默认值。
可在Intellij Idea中为GenAllSetter设置快捷键。
如何使用:
将光标移动到 new 语句的下一行。
点击主菜单Tools-> Codehelper-> GenAllSetter, 或者按下GenAllSetter快捷键。
GenDaoCode 特性

根据Pojo 文件一键生成 Dao，Service，Xml，Sql文件。

Pojo文件更新后一键更新对应的Sql和mybatis xml文件。

提供insert，insertList，update，select，delete五种方法。

能够批量生成多个Pojo的对应的文件。

自动将pojo的注释添加到对应的Sql文件的注释中。 

丰富的配置，如果没有配置文件，则会使用默认配置。

可以在Intellij Idea中快捷键配置中配置快捷键。

目前支持MySQL + Java，后续会支持更多的DB。

如果喜欢我们的插件，非常感谢您的分享。

GenDaoCode 使用方法

主菜单Tools-> Codehelper-> GenDaoCode 按键便可生成代码。

方法一：点击GenDaoCode，然后根据提示框输入Pojo名字，多个Pojo以 | 分隔。

Codehelper Generator会根据默认配置为您生成代码。

方法二：在工程目录下添加文件名为codehelper.properties的文件。

点击GenDaoCode，Codehelper Generator会根据您的配置文件为您生成代码

LecturesCS10 : The Beauty and Joy of Computing - check the Distributed Computing (interesting) (http://inst.eecs.berkeley.edu/~cs10/sp11/)CS 162 Operating Systems and Systems Programming -section Networks and Distributed Systems (http://webcast.berkeley.edu/course_details.php?seriesid=1906978341)Google: Cluster Computing and MapReduce (http://code.google.com/edu/submissions/mapreduce-minilecture/listing.html)Publications CEPH (http://ceph.newdream.net/publications/)TheoryDistributed systems principles and paradigms (http://rads.stackoverflow.com/amzn/click/0130888931)An introduction to distributed algorithms By Valmir C. Barbosa (http://books.google.com/books?id=fPaGrO8KFqQC&printsec=frontcover&dq=ISBN%3a%200262024128&source=bl&ots=QpvNn0J_Or&sig=np9ReVb48vsvTY0ZorrVNBpg_hI&hl=en&ei=r6WoTaHSLcn3rQfk_oioCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Distributed Systems: An Algorithmic Approach (http://rads.stackoverflow.com/amzn/click/1584885645)Design and analysis of distributed algorithms By Nicola Santoro (http://books.google.com/books?id=iXlBscntcUgC&printsec=frontcover&dq=ISBN%200471719978&source=bl&ots=fXmWi9Ja-n&sig=h7ew1WFPXjQSyznQUJZP4__9wbI&hl=en&ei=7KaoTZnBDo_MrQe8wYWoCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Distributed network systems: from concepts to implementations (http://books.google.com/books?id=_pYyEgj0fX8C&printsec=frontcover&dq=ISBN-10%3a%200387238395&source=bl&ots=fa1zPXorXp&sig=1IDXLYBcVbPdsCeEbLRTTlomfpM&hl=en&ei=ZaWoTfrXB4eurAfDrJWnCA&sa=X&oi=book_result&ct=result&resnum=2&ved=0CBwQ6AEwAQ#v=onepage&q&f=false)Distributed systems security: issues, processes, and solutions (http://books.google.com/books?id=ygWEYjk_rEUC&printsec=frontcover&dq=ISBN%3a%200470519886&source=bl&ots=xX09rNCXO-&sig=JFKaStVHQgKrF-F7UP9m9WqZLMg&hl=en&ei=CKWoTcXLNYrXrQeg_oWoCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Principles of Distributed Database Systems (http://books.google.com/books?id=TOBaLQMuNV4C&printsec=frontcover&dq=ISBN%3a%201441988335&source=bl&ots=LpxihM-W_9&sig=qSwyqG9DrW8-EKJLG-ITaFNGIuQ&hl=en&ei=_6ioTa6UNsSsrAebwfmnCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBwQ6AEwAA#v=onepage&q&f=false)Pattern-Oriented Software Architecture: A Pattern Language for Distributed (http://books.google.com/books?id=WVQF2PK2tlgC&printsec=frontcover&dq=ISBN%3a%200470059028&source=bl&ots=jTc3Ri_9cs&sig=n1Ci_a2xMSPNobBx6cGCIhj1QrM&hl=en&ei=L6aoTeaSKNDIrQfOqOypCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Distributed and parallel systems: from cluster to grid computing (http://books.google.com/books?id=XKgwLhMZmKAC&printsec=frontcover&dq=ISBN%3a%200387698574&source=bl&ots=h87M4gQ3cz&sig=X3ZlkzBYNIzWthyGCme4KIPLUgk&hl=en&ei=fKaoTf-jMcHWrQeSmJDyCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBcQ6AEwAA#v=onepage&q&f=false)Distributed Computing: Fundamentals, Simulations, and Advanced Topics (http://rads.stackoverflow.com/amzn/click/0471453242)Advanced distributed systems: third international school and ..., Volume 3 (http://books.google.com/books?id=gLyeWkC-OQ4C&printsec=frontcover&dq=ISBN%3a%203540221727&source=bl&ots=W2uoBB4hPD&sig=r4M7WwyM8C3-iektNV4I2oRk5Hw&hl=en&ei=tqSoTYPlB5GrrAei3ICoCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Distributed data management for grid computing (http://books.google.com/books?id=biIxEDynbpMC&printsec=frontcover&dq=ISBN%3a%200471687197&source=bl&ots=oraHUvLUxK&sig=93APYZC9T30jNpI2p5IbYrP8Zl4&hl=en&ei=bKeoTdfcD4PtrAfHzoinCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Distributed multimedia retrieval strategies for large scale networked systems (http://books.google.com/books?id=6NNtMkw3zKsC&printsec=frontcover&dq=ISBN%3a%200387288732&source=bl&ots=8y8olIZJx9&sig=5FjhddaT_gkwf5VFEPDsG3Nxe_E&hl=en&ei=wKeoTefLCcq3rAeGqYWoCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)New horizons of parallel and distributed computing (http://books.google.com/books?id=32oUVpzVNBQC&printsec=frontcover&dq=ISBN%3a%200387244344&source=bl&ots=JY_TRyTmUt&sig=8URoXyf5grzEfXm31LXvRL3Y0sM&hl=en&ei=5KeoTZmOBM7irAf5hPGnCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Elements of distributed algorithms: modeling and analysis with Petri nets (http://books.google.com/books?id=I4Ft3T0jRfIC&printsec=frontcover&dq=ISBN%3a%203540627529&source=bl&ots=0ZQnwcegLO&sig=CkljuyrkxDX-_jA2ijo7j6pGxZQ&hl=en&ei=eKioTfScI8ymrAe7yomoCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBcQ6AEwAA#v=onepage&q&f=false)ProgrammingParallel and Distributed Programming Using C++ (http://www.canadapost.ca/shopper/items/1006730/Parallel-and-Distributed-0321544676)Distributed .NET programming in C# (http://www.google.com/products/catalog?hl=en&biw=1352&bih=839&q=ISBN%3a%201590590392&um=1&ie=UTF-8&cid=6743176020645370485&sa=X&ei=6amoTc3qEMTVrQec4JGoCA&ved=0CFkQ8wIwCg#)Java network programming and distributed computing (http://books.google.com/books?id=vhwlwVVsUlgC&printsec=frontcover&dq=ISBN%3a%200201710374&source=bl&ots=UyX2BmUI0v&sig=OzJrlo2iOnYNt0U7iYd2mo6b1kk&hl=en&ei=JaeoTZfaGonmrAf035SnCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q=ISBN%3a%200201710374&f=false)Java Distributed Computing (http://oreilly.com/catalog/9781565922068)Hadoop: The Definitive Guide (http://oreilly.com/catalog/0636920010388/)Distributed systems architecture: a middleware approach (http://books.google.com/books?id=BLx8408_s4cC&printsec=frontcover&dq=ISBN%201558606483&source=bl&ots=rI__pXaEXk&sig=JyOtai5x8W5Ht-ZRZBn93usl39A&hl=en&ei=MamoTZXyCIPOrQe1_4mnCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)Tools and environments for parallel and distributed computing (http://books.google.com/books?id=BLx8408_s4cC&printsec=frontcover&dq=ISBN%201558606483&source=bl&ots=rI__pXaEXk&sig=JyOtai5x8W5Ht-ZRZBn93usl39A&hl=en&ei=MamoTZXyCIPOrQe1_4mnCA&sa=X&oi=book_result&ct=result&resnum=1&ved=0CBMQ6AEwAA#v=onepage&q&f=false)


统计
1. Frequentist StatisticsCasella, G. and Berger, R.L. (2001). “Statistical Inference” Duxbury Press.—Intermediate-level statistics book.Ferguson, T. (1996). “A Course in Large Sample Theory” Chapman & Hall/CRC.—For a slightly more advanced book that’s quite clear on mathematical techniques.Lehmann, E. (2004). “Elements of Large-Sample Theory” Springer.—About asymptotics which is a good starting place.Vaart, A.W. van der (1998). “Asymptotic Statistics” Cambridge.—A book that shows how many ideas in inference (M estimation, the bootstrap, semiparametrics, etc) repose on top of empirical process theory.Tsybakov, Alexandre B. (2008) “Introduction to Nonparametric Estimation” Springer.—Tools for obtaining lower bounds on estimators.B. Efron (2010) “Large-Scale Inference: Empirical Bayes Methods for Estimation, Testing, and Prediction” Cambridge,.—A thought-provoking book.2. Bayesian StatisticsGelman, A. et al. (2003). “Bayesian Data Analysis” Chapman & Hall/CRC.—About Bayesian.Robert, C. and Casella, G. (2005). “Monte Carlo Statistical Methods” Springer.—about Bayesian computation.3. Probability TheoryGrimmett, G. and Stirzaker, D. (2001). “Probability and Random Processes” Oxford.—Intermediate-level probability book.Pollard, D. (2001). “A User’s Guide to Measure Theoretic Probability” Cambridge.—More advanced level probability book.Durrett, R. (2005). “Probability: Theory and Examples” Duxbury.—Standard advanced probability book.4. OptimizationBertsimas, D. and Tsitsiklis, J. (1997). “Introduction to Linear Optimization” Athena.—A good starting book on linear optimization that will prepare you for convex optimization.Boyd, S. and Vandenberghe, L. (2004). “Convex Optimization” Cambridge.Y. Nesterov and Iu E. Nesterov (2003). “Introductory Lectures on Convex Optimization” Springer.—A start to understand lower bounds in optimization.5. Linear AlgebraGolub, G., and Van Loan, C. (1996). “Matrix Computations” Johns Hopkins.—Getting a full understanding of algorithmic linear algebra is also important.6. Information TheoryCover, T. and Thomas, J. “Elements of Information Theory” Wiley.—Classic information theory.7. Functional AnalysisKreyszig, E. (1989). “Introductory Functional Analysis with Applications” Wiley.—Functional analysis is essentially linear algebra in infinite dimensions, and it’s necessary for kernel methods, for nonparametric Bayesian methods, and for various other topics.