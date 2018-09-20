---
title: 〆 linux 磁盘分区
date: 2018-01-18 20:08:31
categories: "Basic Knowledge"
tags:
    Linux
    Technology
  - Partition Disks
---

**<font color="#5A5AAD">⚠  应用卷机制安装debian系统，并进行分区    </font>**

## <font color="#FF5151">知识点: </font>linux系统的磁盘分区规则，以及逻辑卷的使用规则
<font style="color: #394F6A; font-size: 20px; font-family: '微软雅黑'">[例如] 不同的分区采用何种方式的文件格式--xfs、ext4(主流)</font>
<!--more-->

## 基本的linux系统路径挂载点

### 英文解释

> / - the root file system
> /boot - static files of the boot loader
> /home - user home directories
> /tmp - temporary files
> /usr - static data
> /var - variable data
> /srv - data for services provided by this system
> /opt - add-on application software packages
> /usr/local - local hierarchy
> swap area
> reserved bios boot area
> efi system partition
> pyysical volume
> ...

### 中文解释

> / - 根分区 200G
> /boot - 存放启动系统使用的静态文件 24G main
> /home - 用户宿主目录的父目录 80G
> /tmp - 临时文件 20G
> /var - 可变数据目录 100G
> /usr - 应用软件存放位置 100G
> /srv - 系统服务目录 40G
> /opt - 附加应用程序 100G
> /usr/local - local hierarchy
> swap area 交换分区 -- 物理内存的2倍 16G
> reserved bios boot area
> efi system partition 20G main
> pyysical volume
> ...

###解析：

#### /

所有未指定挂载点的目录都会放到这个挂载点下。

#### /home

一般每个用户100M左右，特殊用途，比如放大文件也可再加上G。分区大小取决于用户多少。对于多用户使用的电脑，建议把/home独立出来，而且还可以很好地控制普通用户权限等，比如对用户或者用户组实行磁盘配额限制、用户权限访问等。

#### /tmp

临时文件

一般设置1-5G，方便加载ISO镜像文件使用，对于多用户系统或者网络服务器来也有独立挂载的必要。临时文件目录，也是最常出现问题的目录之一。

#### /usr

文件系统

一般设置要3-15G，大部分的用户安装的软件程序都在这里。就像是Windows目录和Program Files目录。很多Linux家族系统有时还会把/usr/local单独作为挂载点使用。

#### /var

可变数据目录

包含系统运行时要改变的数据。通常这些数据所在的目录的大小是要经常变化的，系统日志记录也在/var/log下。一般多用户系统或者网络服务器要建立这个分区，设立这个分区，对系统日志的维护很有帮助。一般设置2-3G大小，也可以把硬盘余下空间全部分为var。

#### /srv

系统服务目录

用来存放service服务启动所需的文件资料目录，不常改变。

#### /opt

附加应用程序

存放可选的安装文件，个人一般把自己下载的软件资料存在里面，比如Office、QQ等等。

#### swap

交换分区

一般为内存2倍，最大指定2G即可


以下为其它常用的分区挂载点

#### /bin

二进制可执行目录

存放二进制可执行程序，里面的程序可以直接通过命令行调用，而不需要进入程序所在的文件夹。

#### /sbin

系统管理员命令存放目录

存放标准系统管理员文件

#### /dev

存放设备文件

驱动文件等
