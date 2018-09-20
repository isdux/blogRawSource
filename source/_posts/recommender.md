---
title: 〆 Recommender System Handdbook
date: 2018-06-12 20:24:45
categories: "Book Notes"
tags:
  - Technology
  - Recommender
    Arithmetic
---

**<font color="#5A5AAD">⚠  Do not let your dream be dream.   </font>**

## <font color="#FF5151">Preface: </font>Just study from now on.
<!--more-->

## Vocabulary 词汇表

```
    word    phonogram   definition/translate
    vocabulary  [və(ʊ)'kæbjʊlərɪ]   词汇，词表，词汇量，字汇
    recommend   [rekə'mend] 推荐，介绍，劝告，使受欢迎，托付，建议
    handbook    ['hæn(d)bʊk]    手册，指南
    arithmetic  [ə'rɪθmətɪk]    算法，算术，运算，四则运算
    various ['veərɪəs]  各种各样的，多方面的
    migration   [maɪ'greɪʃ(ə)n] 迁移，移民，移动，移行
    delicate    ['delɪkət]  微妙的，精美的，雅致的，柔和的，娇弱的，精巧的
    dedicate    ['dedɪkeɪt] 致力，献身，题献，做贡献
    prove   [pruːv] 证明，检验，显示，证明是，证实，显示出
    cope    [kəʊp]  处理，对付，竞争，长袍，应付
    overload    [əʊvə'ləʊd] 超载，超过负荷，负荷过大，重载
    electronic  [ɪˌlekˈtrɒnɪk]  电子的，电子电路，电子器材，电子化，电子商务
    commerce    ['kɒmɜːs]   贸易，商业，商务
    corresponding   [,kɒrɪ'spɒndɪŋ] 相当的，相应的，一致的，通信的，相配，类似
    propose [prə'pəʊz]  建议，打算，计划，求婚，提出
    generation  [dʒenə'reɪʃ(ə)n]    一代，产生，一代人，生殖
    deploy  [dɪ'plɒɪ]   配置，展开，使疏开，部署
    commercial  [kə'mɜːʃ(ə)l]   商业的，营利的，靠广告收入的，商业广告的
    disciplinary    ['dɪsɪplɪn(ə)rɪ; ,dɪsɪ'plɪn-]   规律的，训练的，训诫的，多学科的，纪律的，惩戒性的
    multi   ['mʌltɪ]    多，多用，多向
    involve [ɪn'vɒlv]   包含，牵涉，使陷于，潜心于，使卷入
    expert  ['ekspɜːt]  熟练的，内行的，老练的，专家，行家，能手
    intelligence    [ɪn'telɪdʒ(ə)ns]    智力，情报工作，情报机关，智慧，智能，天分
    interaction [ɪntər'ækʃ(ə)n] 相互作用，交互作用，互动，交互
    research    [rɪ'sɜːtʃ; 'riːsɜːtʃ]   研究，调查，科研，产品研发
    practitioner    [præk'tɪʃ(ə)nə] 开业者，从业者，实践者，实际工作者
    impose  [ɪm'pəʊz]   利用，欺骗，施加影响，征税
    diversity   [daɪ'vɜːsɪtɪ; dɪ-]  多样性，差异，多元化
    present [prɪˈzent;(for n.)ˈpreznt]  提出，介绍，呈现，赠送，现在的，出席的，礼物，瞄准，目前的
    coherent    [kə(ʊ)'hɪər(ə)nt]   连贯的，一致的，明了的，清晰的，凝聚性的，互相耦合的，黏在一起的
    unified ['ju:nifaid]    统一的，一致标准的，统一，使一致，齐一
    concept ['kɒnsept]  观念，概念，思想，理念
    methodology [meθə'dɒlədʒɪ]  方法论，方法学，研究方法，方法
    trend   [trend] 趋势，倾向，走向，使…趋向
    challenge   ['tʃælɪn(d)ʒ]   挑战，怀疑，向…挑战，对…质疑，擂台
    comprehensive   [kɒmprɪ'hensɪv] 综合的，广泛的，有理解力的，综合学校，全面
    entirely    [ɪn'taɪəlɪ; en-]    完全地，彻底地，尽然
    informative [ɪn'fɔːmətɪv]   教育性的，有益的，情报的，见闻广博的
    factual ['fæktʃʊəl; -tjʊəl] 事实的，真实的，实际的，实事求是，实际频率
    concise [kən'saɪs]  简明的，简洁的，简练的
    convenient  [kən'viːnɪənt]  方便，便利的，便捷，方便快捷
    reference   ['ref(ə)r(ə)ns] 参考，参照，涉及，提及，参考书目，引用
    novel   ['nɒv(ə)l]  新奇的，异常的，小说，新颖的
    approach    [ə'prəʊtʃ]  方法，途径，接近，着手处理，靠近
    consist [kən'sɪst]  由…组成，在于，符合，组成存在
    evaluation  [ɪˌvæljuˈeɪʃn]  评价，评估，估价，求值，评测
    community   [kəˈmju:nətɪ]   社区，群落，共同体，团体
    fundamental [fʌndə'ment(ə)l]    基本的，根本的，基本原理，基本原则，根本性
    nowadays    ['naʊədeɪz] 时下，现今，当今，如今
    collaborative   [kə'læbəretɪv]  合作的，协作的，协同，协作型
    content-aware       情境感知，上下文感知
    survey  [ˈsəːveɪ; (for v.) səˈveɪ]  调查，测量，审视，纵览，勘测
    deal    [diːl]  处理，给予，分配，发牌，讨论，交易，做生意
    consideration   [kənsɪdə'reɪʃ(ə)n]  考虑，原因，关心，报仇，代价
    guideline   ['gaɪdlaɪn] 指导方针，参考，指南，准则
    aspect  ['æspekt]   方面，方向，形式，外貌
    pracical    ['præktɪk(ə)l]  实际的，实用性的，踏实，实事
    section ['sekʃ(ə)n] 截面，部分，部门，地区，章节，把…分段，将…切片
    discuss [dɪ'skʌs]   讨论，论述，辩论，商量
    relate  [rɪ'leɪt]   叙述，使…有联系，涉及，认同，有关，关联
    visualization   [,vɪzjʊəlaɪ'zeɪʃən] 形象化，清楚地呈现在心，视觉化
```

