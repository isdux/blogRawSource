---
title: 〆 编程规范
date: 2018-01-18 18:08:31
categories: "Basic Knowledge"
tags:
    Technology
  - Coding Style
---

**<font color="#5A5AAD">⚠ Coding Style   </font>**

## <font color="#FF5151">约定: </font>本约定只是一种自我的约束，一些特定的附加约定随着项目的阶段而改变
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[例如] PEP8规则</font>
<!--more-->

> 用例的名字采用单词的首字母大写的形式，多个单词中使用空格。For: Withdraw Funds.
> 类名单词首字母大写，在图中/代码中 多单词的名字间没有空格，For: CheckingAccount.但是在文本中，为了提升可读性，单词之间引入空格。
> 属性的类型使用首字母大写的单词表示，For: Boolean，Integer.
>> 一个单独的命名对象，采取首字母小写的驼峰命名法
>> 一个单独的未命名对象，采取冒号加类名，For: :CheckingAccount,有时候冒号会被省略
> 消息的命名总是首字母大写并且多单词组成(图、文本)全部必须具有空格。
> 文件名字全部采用小写字母，并且多单词之间用下划线，For: checking_account.js.
> 静态变量名称采取全部大写的字母，普通变量采取首字母小写的驼峰式
> html元素，class的命名全部采用小写字母，多单词之间用-，For: checking-account
> html元素，id的命名采用首字母小写的驼峰式
> 每个方法之间换2行，一行方法不能超过80个字符，js或者html等前端代码，可以稍微超出。
> 命名必须采用贱命合一的英文表示法
> 方法的命名采用首字母小写的驼峰式，并且必须为动词。For: updateByPrimaryKey.

