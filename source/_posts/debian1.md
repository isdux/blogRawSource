---
title: 〆 debian系统搭配xfce4桌面 [linuxNetwork]
date: 2018-09-12 13:59:37
categories: "Basic Knowledge"
tags:
  - debian
  - xfce
  - Basic Knowledge
---

**<font color="#5A5AAD">You will always be able to make more money, but you can not make more time.</font>**

## <font color="#FF5151">How to configure your desktop in debian: </font>当你安装完debian系统之后的配置(网络，虚拟机，eclipse，svn等)
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[主要内容] linux初体验</font>

<!--more-->

## 系统
+ 系统选择上，我使用的debian stretch 分支（9.5.0）
+ 图形化桌面选择是 xfce4
+ 系统安装的启动盘制作有五个软件:

> Universal (推荐：作者使用)
> unetbootin (推荐)
> Rufus （群友风铃木推荐）
> poweriso （群友原道推荐）
> 软通碟 (不推荐: 网上有人说会出现各种问题)

安装时候我选择的是dd刻录整个U盘

安装时候我选择的是Universal里面step1的最后一个选项，dd刻录整个U盘，因为其他形式下，我有时候安装会报错。

具体安装不多做介绍，网上有大量的详细教程(搜索教程时候请带上你选择的软件名)

其中安装linux系统的分区介绍，[点击这里：](http://isdux.com/2018/01/18/linuxSetup/)

## 配置

### 安装 aptitude

debian下我个人比较常用的包管理工具，安装某个软件的时候，将会自动安装所有的依赖。删除也是会同样删除相关依赖。

**注意：别的版本系统不清楚，针对debian9.5.0系统(我的hp笔记本)，安装aptitude共需要三个文件，分别如下所示：**

> [libcwidget3v5](https://packages.debian.org/stretch/libcwidget3v5)
> [aptitude-common](https://packages.debian.org/stretch/aptitude-common)
> [aptitude](https://packages.debian.org/stretch/aptitude)

下载完成后的安装顺序如列表所示，从上到下，安装命令为：

```
dpkg -i **************.deb
```

#### aptitude 常用命令
* aptitude search 文件名
* aptitude install 文件名
* aptitude update
* aptitude upgrade

## 换源

### 更换国内源

更换的是国内的stretch源，喜欢保持系统时刻更新的发烧友使用

```
/**
 * 备份原有的源配置文件
 */
$ cp /etc/apt/sources.list /etc/apt/sources.listbak

/**
 * 删除该源配置文件
 */
$ rm -f /etc/apt/sources.list

 /**
 * 生成国内的源配置文件
 */
$ echo "deb http://ftp.cn.debian.org/debian/ stretch main" > /etc/apt/sources.list
$ echo "deb http://ftp.cn.debian.org/debian/ stretch-updates main" >> /etc/apt/sources.list 
$ echo "deb http://ftp.cn.debian.org/debian-security stretch/updates main" >> /etc/apt/sources.list

 /**
 * 更新源
 */
$ apt-get update  或者 $ aptitude update
```

### 修改源(扩展更多软件包)

**本版本debian默认自带nano文本编辑器**

> $ nano /etc/apt/sources.list （打开源配置文件）
> 将每一个 deb xxxxx 最后增加 non-free（aptitude search 将会发现新增很多模块）

### 安装无线网络驱动

**device not ready(firmware missing)**

刚刚安装好的debian系统，没有无线网络的模块，所以需要安装对应网卡驱动，网上有很多教程，下载对应网卡的驱动，但是，我比较懒，就直接用aptitude安装通用网卡驱动解决
(感觉本方法像windows下安装万能网卡驱动，哈哈哈)

+ aptitude search firmware- (搜索固件的名字)
+ aptitude install firmware-realtek
+ aptitude install firmware-ralink
+（单独安装ralink这个也可以，不过安装会有warn提示，强迫症患者还是两个都安装吧）

## linux 更新

**aptitude update & aptitude upgrade**

这一步操作可以每个星期进行一次(非强迫症可以不进行)

查看系统内核版本

```
$ uname -a
```

修改系统时间
参考链接里面的步骤，我们只进行前半部分即可。

[只需要1-1,2,3然后重启电脑就设置成功](https://www.cnblogs.com/royfans/p/8056270.html)

### 常用软件安装

#### vmware

[vm安装参考](https://www.howtoing.com/install-vmware-workstation-in-linux)

安装谷歌中文输入法

```
aptitude install fcitx
aptitude install fcitx-googlepinyin
```

重启电脑后配置fcitx，在configure里新增googlepinyin输入法

#### google 浏览器

[debian安装chrome浏览器](https://blog.csdn.net/demorngel/article/details/72571153)

注意：这里安装chrome浏览器必须翻墙。因为源为google提供。我用的自己搭建的vps,有时间了给大家分享干货。

#### 安装vim编辑器以及tilda(雷神之锤下拉框–替代自带的命令行-美化用)
aptitude install vim & aptitude install tilda

### 安装eclipse
[文件下载地址](https://www.eclipse.org/downloads/packages/)

其中，有多个版本的eclipse ide供你选择，由于个人原因，我选择:
Eclipse IDE for Java and DSL Developers