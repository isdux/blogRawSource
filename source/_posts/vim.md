---
title: 〆 vim tutorial [Step One]
date: 2018-07-23 10:55:26
categories: "Api Notes"
tags:
  - Technology
  - vim
  - shortcut key
---

**<font color="#5A5AAD">Nothing is impossible when you believe yourself.</font>**

## <font color="#FF5151">How to use vim: </font>vim文本编辑器的初次体验以及基础命令的使用。
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[全键盘] jerry 87 键盘我的最爱。</font>

<!--more-->

## vim introduction

### tools menu

linux 系统的安装暂且不提，如果是windows(比如我，家用台式机有时候因为家人使用所以安装了中文版本的windows系统)，安装的时候由于系统默认的中文语言，导致vim的工具栏导航栏都是中文版本。强迫症患者的我，只好去修改替换了。

potoofly
如何将windows版的vim界面语言（默认为中文）设置成英文
用安装包安装windows版本的vim(下载地址：http://www.vim.org/download.php)，vim会自动根据windows的语言设置vim的界面语言。如何将其改为英文呢？

在vim的安装根目录下（一般的默认安装路径为C:\Program Files (x86)\Vim）找到名为“_vimrc”的文件并且打开

在文件中找到 “ source $VIMRUNTIME/vimrc_example.vim ” 这一行
(老版本可能是第三行，新版本可能是第一行，因为没有了set nocompatible)

在这一行代码之前，加上
let $LANG = 'en'
set langmenu=en   "set menu's language of gvim. no spaces beside '=' 

其中双引号内的内容是注释部分。

这样，vim及gvim的界面均为英文的了。

关于语言的设置，可以参考vim的命令":help lan"

#### 注：很多时候在设置时候提示该文件为只读

这个情况下，我们只需要点开vim文件夹，然后右键管理，给自己添加上修改的权限，之后再进行操作修改即可。

接下来，就是我们开始享受vim的时刻。

### basic shell

#### help
vim有着友好的自带的help帮助文档，通常的我们有两种方式随时进入并且进行查询：
> press the button 'F1'
> press the string ':help'
>> 其中，输入：help 命令还可以更快更直接的进入我们想看到的部分：for: ':help lan'，直接进入help文档的语言设置部分，查看如何设置语言，在这里，我们也可以看到上面提到的 set langmenu

#### Move around
Use the cursor keys, or "h" to go left, "j" to down, "k" to go up, "l" to go right.

":q<Enter>" for close this window.
":qa!<Enter>" for get out of vim(careful, all changes are lost!)

ctrl + ], ctrl + T, ctrl + O 和 ":set mouse=a" 暂时不太理解这里面的含义。

#### mode
vim通常存在着三种模式
* normal mode 一般的新打开vim的时候会自动进入normal mode ，按esc会从任何 mode 切换为normal mode 
* visual mode 一般的按下字母键v进入visual mode
* insert mode 一般的按下字母键i进入insert mode

##### normal mode
在normal mode里可以使用的快捷键依次为：

**x/X:**
按下小写字母键x,将会删除光标所在位置字符，x是针对光标所在位置字符，而不是面向行。这个操作也可以用字母组合"dl"或者del键实现。
单独的x/del/"dl"组合并不包含计数，但是如果我们想依次删除多个字符，可以在指令前加数字。例如：2x。删除将从当前光标位置向后依次删除，直到数量个数个光标为止。
注意：如果x/del/"dl"操作不能实现删除效果，我们可以通过命令":fixdel"来恢复删除功能。

按下大写字母键X,将会删除光标所在位置前一个的字符，大写字母X是针对光标所在位置的前一个字符，而不是面向行。这个操作也可以用字母组合"dh"实现。
单独的X/"dh"组合并不包含计数，但是如果我们想依次删除多个字符，可以在指令前加数字。例如：2X。删除将从当前光标前一个光标的位置向前依次删除，直到数量个数个光标为止。

**d**
字母键d按下后，文件进入删除状态，然后可以配合动作完成定制化数量的删除。
例如： dw,db,d4j(删除5行)

dd 删除整行， D删除当前光标到line-end(也可以用"d$"), d#相当于db(这里有一个特殊的cpoptions，并会产生高亮，暂时不理解) 

在visual模式下，点击x删除，这个光标所在位置如果有高亮且他在高亮部分第一个位置，将删除全部高亮内容，或者删除该字符并移出高亮。

自己看官方帮助文档之后发现遇到了混乱，发现从上往下看不是很友好。于是，先看vim user manual

**CTRL - ]/CTRL - O**
超链接跳转和回退

## 特点
* 文章界面很清晰，很适合阅读~
* Google Search Console
* Google Analytics
* [LiveRe](https://livere.com/) (我去掉了disqus, 国内不翻墙压根连不上)
* 打赏
*   页面滚动快捷键 (j, k, t, b, n, m 具体功能自己尝试, console 有提示~)


```yml
# theme: landscape
theme: ochuunn
```
