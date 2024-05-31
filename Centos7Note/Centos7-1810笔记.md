# 1.Linux基础介绍

## 1.1Linux介绍

**在Linux的世界中一切皆是文件！！！**

 Linux内核最初只是由芬兰人林纳斯·本纳第克特·托瓦兹（Linus Benedict Torvalds）在赫尔辛基大学上学时出于个人爱好而编写的。

Linux是一套免费使用和自由传播的类Unix操作系统，是一个基于POSIX和UNIX的多用户、多任务、支持多线程和多CPU的操作系统。

Linux能运行主要的UNIX工具软件、应用程序和网络协议。它支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。

 Linux是开源的操作系统是一个支持多用户、多进程、多线程、实时性较好、功能强大而稳定的操作系统，也是目前运行硬件平台最多的操作系统。Linux最大的特点在于它是GNU的一员，遵循公共版权许可证(GPL)，秉承“自由的思想，开放的源码”的原则。	Linux内核是一个用。C语言写成，符合POSIX标准的类Unix操作系统。

 	内核版本号：major.minor.patchlevel（内核：https://www.kernel.org/）

​	主版本号：次版本号：修订次数  次版本号为奇数为测试版：为偶数稳定版

最新的内核发布时间  这是写本文档的时候内核版本号

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps1.jpg) 

 

DistroWatch（http://www.distrowatch.com）是一个专门收集Linux发行版信息的网站

### 1.1.1内核认识：

3.10.0-1062.1.2.el7.x86_64

3代表主版本号有结构的变化才改变

10次版本号  奇数表示测试版本  偶数表示开发版本

0此版本号的修订或补丁包数量  

957代表编译的次数

e17 表示版本的特殊信息

el 代表企业版本  

pp代表测试版本

fc代表fedora core核心

rc 代表候选版本

x86——64 表示64位数的版本 





##  1.2发行版本

Linux的发行版说简单点就是将Linux内核与应用软件做一个打包。

目前市面上较知名的发行版有：Ubuntu、RedHat、CentOS、Debian、Fedora、SuSE、OpenSUSE、Arch Linux、SolusOS 等。

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps2.jpg) 



Centos版本

![image-20211118222706427](Centos7-1810%E7%AC%94%E8%AE%B0.assets/image-20211118222706427.png)

![image-20211118222717613](Centos7-1810%E7%AC%94%E8%AE%B0.assets/image-20211118222717613.png)



![image-20211118222736479](Centos7-1810%E7%AC%94%E8%AE%B0.assets/image-20211118222736479.png)

**升级版本**

最新红帽考试课程

![image-20211118222804816](Centos7-1810%E7%AC%94%E8%AE%B0.assets/image-20211118222804816.png)



 

## 1.3系统组成

内核、Shell、文件系统一起构成了基本的操作系统结构。

linux系统包括：Linux内核  Linux软件  Linux文档就组成了一套完整的Linux开发套件

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps3.jpg) 

## 1.4shell

Shell负责将用户的命令解释为内核能够接受的低级语言，并将操作系统响应的信息以用户能理解的方式显示出来，它类似于Windows平台下的DOS提示窗口。

查看有哪些shell：

```shell
[root@xiaozhe0514 ~]# cat /etc/shells 
/bin/sh
/bin/bash
/usr/bin/sh
/usr/bin/bash
/bin/tcsh
/bin/csh
[root@xiaozhe0514 ~]# 
```

Linux中默认的shell是/bin/bash不同的shell都有自己的特点以及用途。

***\*bash\****：大多数Linux系统默认使用的shell，bash shell是Bourne shell 的一个免费版本，它是最早的Unix shell,bash还有一个特点，可以通过help命令来查看帮助。包含的功能几乎可以涵盖shell所具有的功能，所以一般的shell脚本都会指定它为执行路径。

***\*csh：\****C shell 使用的是“类C”语法，csh是具有C语言风格的一种shell，其内部命令有52个，较为庞大。目前使用的并不多，已经被/bin/tcsh所取代。

***tcsh\***：tcsh是csh的增强版，与C shell完全兼容。

ksh：Korn shell 的语法与Bourne shell相同，同时具备了C shell的易用特点。许多安装脚本都使用ksh,ksh 有42条内部命令，与bash相比有一定的限制性。

**sh：**是一个快捷方式，已经被/bin/bash所取代。

**nologin：**指用户不能登录

**\zsh：\**目前Linux里最庞大的一种shell：zsh。它有84个内部命令，使用起来也比较复杂。一般情况下，不会使用该shell。

 **Linux 内核**

Linux 内核诞生于 1991 年，目前已超过 1500 万行代码，价值达数百亿美元。以它为核心推出的操作系统发行版最为流行的有 RedHat、Suse、Ubuntu、[Android](http://c.biancheng.net/android/)、Centos、Debian 等，大概有上百种（具体可参考排行网站 [http：//distrowatch.com](http://distrowatch.com/)）。如果不特别指定，这些发行版统称为 Linux 操作系统。

Linux 操作系统开源免费、稳定可靠、病毒少、性能高，作为平台软件，被广泛应用在云端、数据中心。

目前除微软外，全部云中心都采用 Linux 操作系统。



**GNU  GPL 通过公共许可证**  

只要软件包中使用了遵守GNU 的软件必须遵守GPL的开源的协议  

最大的四个特点：复制自由  、传播自由  、收费传播、修改自由

BSD 伯克利软件发布版本

Apache许可证版本协议

 

## 1.5开源共享精神

1. 开源软件的特性有哪些  

2. 低风险

3. 高品质  

4. 低成本  

5. 更透明  




##  1.6文件系统

​	[ext2](https://baike.baidu.com/item/Ext2/822106?fr=aladdin)，[ext3](https://baike.baidu.com/item/Ext3)，[FAT](https://baike.baidu.com/item/FAT/267561)，[vfat](https://baike.baidu.com/item/虚拟文件分配表?fromtitle=vfat&fromid=99917)，[iso9660](https://baike.baidu.com/item/ISO 9660?fromtitle=iso9660&fromid=3127098)，[NFS](https://baike.baidu.com/item/网络文件系统/9719420?fromtitle=NFS&fromid=812203)，[SMB](https://baike.baidu.com/item/smb)

## 1.7应用程序

​	文本编辑器、编程语言、X-Window、办公套件、Internet工具、数据库等。

## 1.8应用领域

​	网络领域   嵌入式领域    桌面领域  服务器领域

## 1.9桌面环境

**1.9.1X Window：**

X Window系统是Linux的窗口系统，是一个基于网络的图形界面系统，它于1984年在麻省理工学院开发，有将近20多年的应用历史。X Window本身是一种基于网络协议的窗口，任何硬件只要遵守X Protocol，就可以进行相应的窗口显示工作。

**1.9.2组成原理：**

​	X Window是C/S架构，涵盖X Server、X 协议、X Client 三部分

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps5.jpg) 

 

XServer（X服务器）。位于最底层，主要处理输入、输出信息并维护相关资源。X Client（X客户端）。位于最外层，提供完整的GUI界面，负责与用户的直接交互（GNOME是X Client）。X Protocol(X通信协议)。用于X Server与X Client之间的链接，充当这两者的沟通管道。

 

##  1.10文本模式与图形化转换

```shell
startx   //启动 X Window
在centos7中采用的是:systemctl get-defaults     systemctl set-defaults 
[root@xiaozhe0514 ~]# systemctl isolate multi-user.target 
[root@xiaozhe0514 ~]# systemctl isolate graphical.target 
```

**GNOME桌面：**

​	GNOME是一套纯粹自由的计算机软件，运行在操作系统上，提供图形桌面环境。GNOME桌面环境是典型的Linux的桌面环境 3个部分：桌面快捷方式、面板图标和应用程序。GNOME默认将Nautilus图形化工具作为文件管理器。GNOME是Linux操作系统上最常用的图形桌面环境之一。Fedora就是采用Gnome的Linux系统

 

## 1.11系统下载

下载1：http://vault.centos.org/

下载2 : http://archive.kernel.org/centos-vault/

### 1.11.1系统安装：

实体机器的安装:注意硬件的网卡和显卡问题 一定注意驱动问题和使用操作  少使用root账户  

使用本地 PC 环境的 VMWare Workstation 软件进行实操练习，镜像使用提供的CentOS-7-x86_64-DVD-1810.iso

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps6.jpg) 

操作系统采用最小化安装，安装时请选择英文界面，然后单击右下角“Continue”按钮，

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps7.jpg) 

单击“INSTALLATION DESTINATION”按钮进行分区

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps8.jpg) 

选择磁盘并选中“I will configure partitioning”单选按钮，单击左上角“Done”按钮，

进行手动分区

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps9.jpg) 

单击“Click here to create them automatically”按钮自动创建分区，分区完成单击左上角“Done”按钮

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps10.jpg) 

选择自动分区

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps11.jpg) 

单击“Accept Changes”按钮保存修改

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps12.jpg) 

单击“Begin Installation”按钮开始安装

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps13.jpg) 

单击“ROOT PASSWORD”按钮设置root密码，设置密码为root。单击两次“Done”按钮保存退出

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps14.jpg) 

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps15.jpg) 

安装完成后单击右下角“Reboot”按钮重启系统：

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps16.jpg) 

 

输入用户名密码登录系统，操作系统安装完成：

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps17.jpg) 

 

 

注意：boot必须普通分区 ，swap可以放在lvm上 swap和其他分区都可以，但是除boot分区外。

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps18.jpg) 

### 1.11.2安装完成后简单配置

1.配置本地yum仓库  或者 网络的yum仓库

```shell
mkdir -p /opt/local-yum
cd /etc/yum.repos.d
mv * /opt
cat > /etc/yum.repos.d/local.repo << EOF
[local-yum]
name=local-yum
baseurl=file:///opt/local-yum
enabled=1
gpgcheck=0
EOF
mount /dev/cdrom /opt/local-yum
yum clean all; yum makecache 
```

**2.配置网卡信息**

```shell
vi /etc/sysconfig/network-scripts/ifcfg-eno16777728 
ONBOOT="yes"  //设置为yes	
systemctl restart network   重启网卡  或者使用nmtui进行设置
```

**3.学习使用关闭防火墙简单防火墙命令**

```shell
systemctl stop firewalld 
systemctl disable firewalld
setenforce 0    #关闭selinux
getenforce     #查看selinux的状态
sed -ie 's/SELINUX=.*/SELINUX=disabled/g' /etc/selinux/conf
```

**4.设置主机名   和  /etc/hosts文件**s

```shell
hostnamectl set-hostname  server    # 使用nmtui进行快速设置
vi /etc/hosts 或者使用echo进行追加
echo "192.168.100.10" >> /etc/hosts 
```

**5.查看系统的时区 ：**

```
设置时区的命令  tzselect  5911//简写的数字
```

**6.设置系统的时间 ：**

```shell
date -d "2004-02-29 16:21:42" //把指定日期和时间都按CST格式输出
-s参数就是设置时间和日期    

查看系统版本：cat /etc/centos-release  
uname -a  查看内核版本    #uname -r 显示内核版本
```

## 1.12vmware克隆系统网卡失效

解决方法：

```shell
# vi  /etc/sysconfig/network-scripts/ifcfg-eth0  #删除 MAC 地址行
# rm  -rf  /etc/udev/rules.d/70-persistent-net.rules  #删除 MaC 地址和 UUID 绑定文件此文件可以备份后删除
# reboot  #重启 最直接的方法就是不适用NetworkManager服务直接使用配置文件进行修改。
```

 ```
修改系统语言 :简体中文 
查看系当前语言包
locale
查看系统拥有语言包
locale -a
（zh_CN.UTF-8是简体中文，如果没有zh_CN.UTF-8,就安装语言包，如果存在可以直接设置)
安装简体中文语言包
yum install kde-l10n-Chinese
设置为中文
vi /etc/locale.conf
##加下面内容到第一行，设置中文
LANG="zh_CN.UTF-8"    #修改为中文
LANG="en_US.UTF-8"    #修改为英文
或者使用:
localectl  set-locale LANG=zh_CN.UTF8
echo "LANG=en_US.UTF-8"  >  /etc/locale.conf
修改时区为亚洲上海
ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
 ```



## 1.13正确关闭Linux机器

  	重启命令： reboot  init6  重新启动
  	关机命令：shutdown now   poweroff  init 0 关机
  	sync   先同步数据  发出关闭命令   输入关机命令。别忘记每次真实的物理linux服务器需要把内存的数据同步到磁盘中

```shell
shutdown 
 -t 几秒中后关机
 -k 发出关机命令但是不关机 
 -c 取消之前命令
 -h 在服务停止后关机
 -f 关闭并且开机后，强行掠过磁盘检查
 -c 取消已经在进行的shutdown 指令内容
shutdown +h 10 十分钟后关机
shutdown +h 12:00 十二点关机
shutdown -r  +10 ‘the system will reboot
```




## 1.14Xshell软件快捷键：

```shell
ctrl+a   命令开头
ctrl+e   命令结尾
ctrl+u   光标处到开头处删除
ctrl+k   光标处到结尾处删除
ctrl+r   历史记录搜索命令给
ctrl+l   清屏
```

# 2.云服务器介绍

**虚拟主机：**在一台服务器中划分一定的磁盘空间供用户放置网站信息、存放数据等；仅提供基础的网站访问、数据存放与传输功能；能够极大地降低用户费用，也几乎不需要用户来维护网站以外的服务；适合小型网站。

**VPS**（Virtual Private Server，虚拟专用服务器）：在一台服务器中利用 OpenVZ、Xen 或KVM 等虚拟化技术模拟出多台“主机”（即 VPS），每个主机都有独立的 IP 地址、操作系统；不同 VPS 之间的磁盘空间、内存、CPU、进程与系统配置完全隔离，用户可自由使用分配到的主机中的所有资源，为此需要具备一定的维护系统的能力；适合小型网站。

**ECS**（Elastic Compute Service，云服务器）：是一种整合了计算、存储、网络，能够做到弹性伸缩的计算服务；使用起来与 VPS 几乎一样，差别是云服务器是建立在一组集群服务器中，每个服务器都会保存一个主机的镜像（备份），从而大大提升了安全性和稳定性；另使用 LNMP 架构部署动态网站环境 外还具备灵活性与扩展性；用户只需按使用量付费即可；适合大中小型网站。

**独立服务器：**这台服务器仅提供给用户一个人使用，其使用方式分为租用方式与托管方式。租用方式是用户将服务器的硬件配置要求告知 IDC 服务商，按照月、季、年为单位来租用它们的硬件设备。这些硬件设备由 IDC 服务商的机房负责维护，用户一般需要自行安装相应的软件并部署网站服务，这减轻了用户在硬件设备上的投入，适合大中型网站。托管方式则是用户需要自行购置服务器硬件设备，并将其交给 IDC 服务    存放在IDC机房中

**1U就是4.445cm，2U则是1U的2倍为8.89cm。**

## 2.1开源操作系统

开源的意思是系统的源代码是面向用户开放的，可以遵循开源协议（GNU）进行使用、编译和再发布。在遵守 GNU 协议的前提下，任何人都可以免费使用，随意控制软件的运行方式。最著名的开源操作系统是 linux。

开源操作系统最大的特点就是**开放源代码和自由定制**，但也会因为使用者的技术水平等关系出现很多不可预知的情况及维护问题，并且由于多数硬件和软件厂商并不支持开源软件。所以在驱动和软件源方面有很大困难，这就要求个人用户在选择系统时需要注意根据自己的实际情况来选择

开源系统的分类：

- Unix-like 类：Linux（这一族开发者众多，发行版本以千计，覆盖所有平台，并支持所有文件格式和所有网络协议）、FreeBSD、OpenBSD、NetBSD（覆盖所有平台）、DrangonflyBSD、Darwin/OpenDarwin/PureDarwin、Minix、GNU Mach/GNU Hurd、L4/Fiasco/Pistachio、syllable、
- Unix 类：Opensolaris、AuroraUX、Plan9、Inferno-Plan 9。
- dos 类：Freedos
- windows-like 类：ReactOS



# 3.基本命令

## 3.1文件和目录的介绍：

| 目录介绍   |                         |
| ---------- | ----------------------- |
| /boot      | Linux启动时候需要的文件 |
| /dev/      | 设备文件                |
| /etc       | 配置文件                |
| /home      | 用户家目录              |
| /media     | 媒体文件                |
| /mnt       | 挂载文件                |
| /opt       | 第三方软件              |
| /proc      | 虚拟化文件              |
| /root      | 管理员家目录            |
| /run       | 进程文件                |
| /src       | 压缩文件                |
| /sys       | 系统文件                |
| /usr       | 用户安装的软件可以共享  |
| /var       | 可变的数据日志文件      |
| /tmp       | 临时文件                |
| /usr/bin   | 普通用户使用的命令      |
| /usr/sbin  | 管理员用户使用的命令    |
| /usr/lib32 | 库文件                  |
| /usr/lib64 | 库文件                  |

## 3.2**文件和目录的区分：**  

```shell
 d表示目录
 -表示文件
 l 链接文件  
 b 存储接口文件     /dev/cdrom 
 c串行接口设备
linux不同文件类型对应的颜色：
	白色：表示普通文件
 	蓝色：表示目录
	绿色：表示可执行文件
	红色：表示压缩文件
    浅蓝色：链接文件
	红色闪烁：表示软链接的文件有问题  出现文件的丢失问题
	黄色：表示设备文件
	灰色：表示其它文件
```



## 3.3目录操作

```shell
绝对路径绝对不可改变的路径     /etc/passwd
相对路径相对于某个路径可以改变的路径     cd network-script/
```

## **3.4字符的匹配的（通配符）**

```
{} ：集合操作符，依次匹配{}内的所有信息
*：任意字符
？：任意单个字符
[]：集合操作符，任意匹配[]内的所有信息
[abc… ] 匹配指定范围内的任意一个字符
{a,b} 或{a..c} 匹配括号中的连续字符
[!abc...] 或者 [^abc...] 不包含字符
[[:alpha:]] 任何字母字符
[[:lower:]] 任何小写字符
[[:upper:]] 任何大写字符
[[:alnum:]] 任何字母或数字
[[:punct:]] 除空格和字母、数字以外的任何可打印字符
[[:digit:]] 任何数字，即0-9 u[[:space:]] 任何空白字符
```



## **3.5文件和目录的操作** 

```shell
增、删、改、查、查看   没有完成
 /etc：绝对路径表示
 ./aa：相对路径表示"当前目录下的 aa"
 ../：相对路径表示"上级目录"
#命令
mkdir
rm
mv
ls
#yum install -y bash-completion 自动补全命令软件包
```

## 3.6ls列出目录

```shell
#ls -l 长格式显示
#ls -a 显示所有信息
#ls -d 显示目录本身信息
#ls -h 人性化显示目录信息
#ls -i 显示文件、目录的 inode 表
#ls -Z 显示 SELinux 信息
#ls -R 递归显示目录信息
```

## 3.7 mkdir 创建目录 

```
#mkdir dir1
#mkdir -p a/b/c
```

## 3.8 rmdir 删除目录

```
#rmdir 删除空目录（现在很少用常用rm）
#rmdir dir1
#rmdir -p a/b/c
```



## 3.9 cd 切换目录

```
#cd - 进入最后一次的工作目录    改变工作目录
#cd ~ 回用户家目录
cd ..    返回上一层目录
cd ../..  返回上两层目录
  
```



## 3.10 pwd 显示目录

```shell
#pwd 显示当前工作目录名
pwd -d   #光显示目录
```



## 3.11touch 创建文件

```
#touch :创建空文件或修改件的时间戳
#touch install.log
#touch file{1,2,3}    批量创建文件   123文件分别存在
```



## 3.12stat  显示文件

```
#stat install.log    显示文件时间戳
访问时间(access time)：文件被访问的时间，文本访问类命令会修改此时间
修改时间(modify time)：文件内容被修改的时间，使用 echo 命令会修改此时间
元数据改变时间(chage time)：文件属性的变化（名称、大小、权限、链接等），
mv、echo 命令会修改此时间    在服务器中时间戳是很重要的 主要收集日志和报错信息记录的时间    保证时间的同步
```



## 3.13cat  查看文件

```shell
#cat install.log 显示文件内容  正的显示
#tac install.log 反着显示
```



##  3.14 less 查看文件

```shell
#less install.log  支持滚屏显示，可以使用/或？进行查找，需要按 q 键退出
```



## 3.15 more 多行显示文件

```shell
#more install.log    支持滚屏显示，显示到文件末尾则退出
```



## 3.16 head 头 显示

```shell
#head install.log    显示文件首部   默认 10 行
#head -5 install.log
```



## 3.17 tail 尾显示

```shell
#tail install.log   显示文件尾部     默认 10 行
#tail -3 install.log
#tail -f install.log  （动态显示文件用于排错）   tailf   /var/message 
```



## 3.18file 查看文件类型

```shell
#file install.log   显示文件类型
#file /dev/sda1
file命令用来识别文件类型，也可用来辨别一些文件的编码格式
```

 

## 3.19 cp 复制

```shell
#cp install.log install.log.bak    
#cp /dev/scd0 /iso/centos7.iso
#cp -r ~/Desktop  /tmp    //复制目录
#cp -pr /media/cdrom/Server /tmp     //保留文件权限复制
#cp -a /media/cdrom/Server /tmp    //保留文件权限复制
```



## 3.20 mv 移动

```shell
#mv install.log /tmp/install.bak   移动、改名命令
#mv install.log.bak install.log
#mv /mnt/* /tmp
```



## 3.21rm 删除

```shell
#rm install.log.bak   删除命令
#rm -f /tmp/install.log.bak
#rm -fr /tmp/Server/  //删除目录
```



## 3.22 nl 列出行号

```shell
-ba无论是否有空行，都列出行号     
-bt  如果有空行，则不列出行号
-n  -nln  行号在屏幕左方  
- nrn  行号在屏幕右方 
-nrz  行号在屏幕右方
-w  文档缩进字符
```



## 3.23alias 设置别名

```shell
设置别名的alias 命令：
用户可利用alias，自定指令的别名。若仅输入alias，则可列出目前所有的别名设置。若要每次登入是即自动设好别名，可在.profile或.cshrc中设定指令的别名。
unalias为shell内建指令，可删除别名设置。
语法：unalias [-a][别名]   -a是删除全部的别名
[root@localhost ~]# alias lll=ls 
[root@localhost ~]# lll
1  nginx-1.16.0  nginx软件安装包.gz  php-7.2.12  php安装包.gz
[root@localhost ~]# unalias lll
[root@localhost ~]# lll
-bash: lll: command not found
[root@localhost ~]#
```



## 3.24wget 下载

```shell
wget
参数 作用
-b 后台下载模式
-P 下载到指定目录
-t 最大尝试次数
-c 断点续传
-p 下载页面内所有资源，包括图片、视频等
-r 递归下载


uptime 用于查看系统的负载信息，格式为 uptime。
[root@server01 ~]# uptime
 10:29:33 up 51 days, 20:26,  2 users,  load average: 0.15, 0.05, 0.06
[root@server01 ~]# 

```



## 3.25find查找文件

find 查找文件

1. 不根据数据库查找，速度慢，默认区分大小写

2. 当调用-exec ls -l {} \;参数时，会显示当前被查找目录下的所有对象信息，然后再显示目录下满足条件的对象信息。可以使用-ls 进行替代。

3. 在使用-or 参数时，如果-or 左边的参数满足条件，则不再检查-or 右边的参数

4. 如果需要联合使用-ls 和-or/-and 参数，需要在条件表达式的每一侧都使用-ls 参数

```shell
#find / -user root -ls -or -user kevin -ls 2> /dev/null
```

5. 可以省略-and 参数，默认多条件查找就是-and 操作

```
#find / -nouser      查找没有所有者组的文件(该所有者不存在于/etc/group 中)
#find / -nogroup     在/var/lib 目录下查找所有者是 games 的文件
#find /var/ -user games 2> /dev/null    在/var 目录下查找所有者是 root，所属组是 mail 的文件
#find /var/ -user root -group mail 2> /dev/null     查找所有者是 mandy 或者 kevin 的文件
#find /home -user mandy -or -user kevin 2> /dev/null   查找所有者不是 root、bin 和 student 的文件
#find / -not -user root -not -user bin -not -user student 2> /dev/null
```

查找文件大小在 1M 以上的文件并显示

```
#find / -size +1M -exec ls -l {} \; 2> /dev/null  {}指代 find 找到的文件
```

查找文件大小在 1M 以下的文件并显示

```
#find / -size -1M -exec ls -l {} \; 2> /dev/null
```

查找文件大小正好是 1M 的文件并显示

```
#find / -size 1M -exec ls -l {} \; 2> /dev/null
```

查找文件大小是 100 字节的文件

```
#find / -size 100c -ls 2> /dev/null
```

查找文件大小在 100K 以上的文件

```
#find / -size +100k -ls 2> /dev/null
```

查找修改时间在 120 分钟前的普通文件

```
#find / -mmin +120 -and -type f -ls 2> /dev/null
```

删除之前查到的文件

```
#find / -mmin +120 -and -type f -ok rm {} \; 2> /dev/null  //删除前询问
#find / -mmin +120 -and -type f -exec rm {} \; 2> /dev/null //删除前不询问
```

根据权限进行查找

```shell
#find / -perm 444  //查找权限严格匹配 444 的文件
#find / -perm +444 //查找任意位权限匹配 4 的文件
#find / -perm -444 //查找权限至少是 444 的文件
```



## 3.26 wc统计字符个数

```shell
统计字符的个数：
wc -l 文件名
wc -w 文件名
wc -c 文件名
```

 

## 3.27cut截取

```shell
[root@server01 ~]# cut --help 
Usage: cut OPTION... [FILE]...
Print selected parts of lines from each FILE to standard output.

cut -c 

```

## 3.28 grep 过滤

```shell
grep -v   进行反向选择
grep -i 
grep -v "^#"  选择不是#号的命令
```



## 3.29sort排序

```shell
sort进行排序
sort -t进行排序的操作
```



## 3.30uniq排除重复行

删除重复的行 

```shell
uniq -u 进行重复行的去掉
```

### 3.31tr  转换或删除文件中字符

 字符的转换的使用   删除文件中控制的字符 进行字符的转换  

```shell
[root@server ~]# ifconfig eth0 | grep 'inet' | tr -d 'a-zA-Z:' | tr ' ' '\n' | grep -v '^$'
		172.17.10.72
		255.255.240.0
		172.17.15.255
```



# 4. 文件的链接

```
	硬连接指通过索引节点来进行连接。在 Linux 的文件系统中，保存在磁盘分区中的文件不管是什么类型都给它分配一个编号，称为索引节点号(Inode Index)。删除其中一个不会影响另外一个
```

## 4.1  ln

实验理解软连接和硬链接：

```shell
[test @Linux]$ touch f1      #创建一个测试文件f1
[test @Linux]$ ln f1 f2      #创建f1的一个硬连接文件f2
[test @Linux]$ ln -s f1 f3    #创建f1的一个符号连接文件f3
[test@Linux]$ ls -li       # -i参数显示文件的inode节点信息
9797648 -rw-r--r--  2 oracle oinstall 0 Apr 21 08:11 f1
9797648 -rw-r--r--  2 oracle oinstall 0 Apr 21 08:11 f2
9797649 lrwxrwxrwx  1 oracle oinstall 2 Apr 21 08:11 f3 -> f1
依此您可以做一些相关的测试，可以得到以下全部结论：
 1).删除符号连接f3,对f1,f2无影响；
 2).删除硬连接f2，对f1,f3也无影响；
 3).删除原文件f1，对硬连接f2没有影响，导致符号连接f3失效；
 4).同时删除原文件f1,硬连接f2，整个文件会真正的被删除。
```



## 4.2man 查看帮助文档

```shell
man   帮助文档的使用更新数据库 mandb
man（manual pages）俗称手册页，提供命令的详细帮助信息
#man [n |<a>] <some-command>
n的取值为1-9  SA常用的是158 三类   
-a：在所有的man帮助手册中搜索不是所有命令都有man配置
#man -k 关键字 //按关键字查询 man，显示那些 man 页包含该关键字
#man -K 关键字 //按关键字查询，依次询问是否需要查看该 man 信息页
使用-k 查找需要重构 whatis 数据库，使用 makewhatis 手动重构该数据库，
whatis 数据库在每天晚上会自动重构。可参阅/etc/crontab
/usr/share/man  存放帮助文档的地方
```

**帮助文档内容的组成**

| NAME        | 名称及简要说明       |
| ----------- | -------------------- |
| SYNOPSYS    | 格式和使用方法说明   |
| DESCRIPTION | 详细说明             |
| OPTIONS     | 可用选项及其介绍说明 |
| EXAMPLES    | 示例（附带简单说明） |
| FILES       | 相关文件             |
| ENVIRONMENT | 环境变量             |
| SEE         | ALSO                 |

 

**查询命令在哪里**

```shell
which passwd
whoami 查看使用按个用户进行登录的账户
```



## 4.3Info 详细帮助信息

```shell
info(information)信息页，提供命令的详细帮助信息
info 中所有的节点链接都有前缀*，可以使用 tab 转移到下一个链接，使用 enter 转移到选中的链接，使用 n/p/u 在 info 的下一个节点/前一个节点/上一级节点间跳转。
#info useradd
```

 

## 4.4 pinfo 帮助文档

```
帮助文档
/usr/share/doc    Linux 下的所有文档   
```



## 4.5 history 查看历史命令

```shell
history  -c //清楚历史命令 
!2   //运行历史记录中的第二条命令，默认保存1000条，
历史命令的记录位于家目录的隐藏文件中 
last 命令用于显示用户最近登录信息   对应/var/log/wtmp 文件 
```

# 5.管道 vi vim使用

将一个程序的标准输出写道一个文件中去，再将这个文件的内容作为另一个命令的标准输入，等效于通过临时文件将两个命令结合起来。需要Linux系统提供一种功能：它不需要或不必使用临时文件，就能将两条命令结合在一起。这种功能就是管道。

```shell
>file 标准重定向
>>file 追加重定向
2>file  错误重定向
2>/dev/null  stderr 重定向/dev/null
&>file   结合stdout和stderr到一个文件
&>>file  结合stdout 和 stderr追加到当前内容后
```



## 5.1vi三种模式

```shell
		命令模式: 刚刚启动 vi/vim，便进入了命令模式
		输入模式: 就是普通的输入的模式简称编辑模式
		末行模式: 可以输入单个或多个字符的命令
	三种模式之间的切换过程：在输入vi或者vim时候便进入了命令模式，输入ioa 就进入了编辑模式，可是编辑文档， 按下Esc便进入了末行模式，进行一些文件的查找替换，保存和退出操作。输入:wq保存退出。

```

## 5.2键盘位置图：

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps1-1618040826685.jpg) 

 

## 5.3搜索和替换

```shell
/word 向下搜索word字符串
? word向上搜索word字符串  使用n向下查找  N向上查找
:n1,n2s/word1/word2/g 在n1行到n2行替换word1为word2（常用）
:n1,$s/word1/word2/g  从第一行到最后一行搜索word1替换为word2 等价:$s/word1/word2/g
:1,$/word1/word2/gc   从第一行到最后一行替换word1为word2 需要用户的确认等价于 :$s/word1/word2/gc
```

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps2-1618040826687.jpg) 

## 5.4删除和复制操作

```shell
x向后删除一个字符X向前删除一个字符  
nx删除连续的几个字符10n删除后是个字符  dd 删除坐在的一行 	ndd删除连续的几行
yy复制一行  nyy复制几行  y1G复制光标所在的行到第一行 
yG 复制光标所在的行到最后一行   y0复制光标所在行到行头  	y$ 复制光标所在的到行尾
p粘贴光标的上一行  P粘贴在光标的上一行
j将光标所在的行和下一行结合在一块
u恢复上一个动作  ctrl+r重复上一个动作
```



## 5.5一般模式切换到编辑模式

```shell
i光标处输入  I光标所在行第一个空字符输入
a 光标的下一个字符开始输入 A光标所在行的最后一个字符输入
o下一行开始输入O上一行开始输入
R一直取代光标所在的文件  r取代光标所在字符一次
在vi左下角显示insert或者replace  一定要特别注意 重要的模式标志 可以判断命令模式还是插入模式
esc退出编辑模式
文件的保存:
	:w 直接保存
	:w! 强制保存
	:q离开
	:q!强制离开
	:wq保存然后离开
	:w [filename] 另存为的意思
	:r [filename] 读入另外一个文档的数据
	:n1,n2 w [filename] 将n1到n2行存储为新的文档
	:! command  离开该文件去执行command结果
	:!ls /home 离开当前文档查看/home的结构
	:set nu  设置行号	
	:set nonu  取消行号
	按下esc执行50dd 则向下删除50行的内容。 向下移动50行50j
```

 



## 5.6vim批量添加注释

vi没有批量添加注释的功能

```shell
方法一 ：块选择模式
批量注释：
Ctrl + v 进入块选择模式，然后移动光标选中你要注释的行，再按大写的 I 进入行首插入模式输入注释符号如 // 或 #，输入完毕之后，按两下 ESC，Vim 会自动将你选中的所有行首都加上注释，保存退出完成注释。
取消注释：
Ctrl + v 进入块选择模式，选中你要删除的行首的注释符号，注意 // 要选中两个，选好之后按 d 即可删除注释，ESC 保存退出。
方法二: 替换命令
1、在 10 - 20 行添加 // 注释
:10,20s#^#//#g
2、在 10 - 20 行删除 // 注释
:10,20s#^//##g
3、在 10 - 20 行添加 # 注释
:10,20s/^/#/g
4、在 10 - 20 行删除 # 注释
:10,20s/#//g
```

 

# 6.文件和文件夹权限

## 6.1权限的介绍

**主要组：**

每个用户只能隶属于一个主要组，主要组（私有组）是用户创建文件时默认的所有组

**附加组：**

用户可以同时隶属于多个附加组（31 个，连主要组一共 32 个组），附加组主要用于权限管理。

**其他人：**

不论用户属于哪个组，用户都能拥有组的权限

权限分三等级：用户、组、其它人。每个权限位分为读、写、执行三种。

```shell
#ls -l
-rw-r--r-- 1 root root 3341 Apr 24 18:25 install.log.syslog
drwx-r-xr-x 2 root root 4096 Apr 25 10:07 dir1
```

```shell
权限表示方法：
		字母表示方法：r（读）w（写）x（执行）-没有权限
		数字表示方法：4 r（读）2 w（写）1 x（执行）
文件最大权限666   目录最大权限777 
```

 

## 6.2特殊权限



计算方法：使用最大权限减去umask值就是创建文件或目录的权限

umask权限就是创建文件或者目录的默认权限

root用户创建的目录权限是755 普通用户创建的目录权限是775

root用户创建的文件权限是644 普通用户创建文件的权限是664

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps1-1618041013145.jpg) 

**课本说法：** 如果umask出现奇数上边没问题，但是出现奇数用奇数位减1 然后在进行运算。

```shell
注意：设置umask值：
umask 230
文件：666-230=436
目录：777-230=547
root的umask：0022
普通用户的umask：0002
如果umask中没有出现奇则上面是没有问题ide  但是如果出现奇数  把umask的奇数位-1  然后用666减去运算过后的umask值
```

## 修改文件和目录权限

​	**修改文件的权限：**

```shell
chmod  权限   文件
chmod  777   file1
```

​	 **修改文件的属主(文件的拥有者)**

```shell
chown  root  file1  chown  root:root file1
```

​	**修改文件的属组（文件的所属组）**

```shell
chgrp  root file1
```



## 特殊权限Suid和Sgid和Sbit权限

suid（t表示）：用户执行这个文件时***将以文件所有者的身份执行***。passwd 命令具有 SetUID 权限，所有者为 root（Linux 中的命令默认所有者都是 root），也就是说当普通用户使用 passwd 更改自己密码的时候，那一瞬间突然 “灵魂附体” 了，实际在以 passwd 命令所有者 root 的身份在执行，root 当然可以将密码写入 /etc/shadow 文件（root 是一个 bug 的存在，在 Linux 中就没有它不能干的事），命令执行完成后该身份也随之消失。

设置suid和设置sgid的条件：

```shell
	拥有者必须有执行权限  必须事二进制可以执行的文件    
```

**案例**

```shell
设置 SetUID:
chmod 4xxx < file-name >chmod u+s < file-name >
取消 SetUID:
chmod xxx < file-name >chmod u-s < file-name >
设置sgid（t）	
设置 SetGID:
chmod 2xxx < file-name >chmod g+s < file-name >
取消 SetGID:
chmod xxx < file-name >chmod g-s < file-name >
注意：
普通用户对目录具备 r 和 x 权限，才可以进入到该目录
普通用户在此目录中的有效组会变成此目录的所属组
如普通用户对该目录具备w权限，新建文件的所属组为该目录的所属
```

Sbit权限：若没有粘滞位，则普通用户可以对目录下的文件/子目录进行删除操作。若赋了 SBIT,则普通用户只能删除自己创建的文件目录，而不能删除不属于自己的文件目录！

```shell
设置 SBIT
chmod 1xxx < dir-name > chmod o+t < dir-name >
取消 SBIT
chmod xxx < dir-name > chmod o-t < dir-name >
查看文件md5值：
root@VM-12-10-ubuntu:~# touch 1 
root@VM-12-10-ubuntu:~# md5sum 1 
d41d8cd98f00b204e9800998ecf8427e  1
root@VM-12-10-ubuntu:~# vim 1 
aroot@VM-12-10-ubuntu:~# md5sum 1 
bac96c3138b80e3e494d9a042b3596b5  1
root@VM-12-10-ubuntu:~#  只要文件有修改   MD5数值就会发生变化。

特殊权限acl访问控制列表:先分配大权限 然后在细分小的权限 
setfacl  设置acl权限
getfacl  查看acl权限
```

**隐藏权限的使用：设置了隐藏权限root都没有权力进行删除文件**

```shell
[root@xiaozhe0514 123]# touch 1
[root@xiaozhe0514 123]# chattr +i 1 
[root@xiaozhe0514 123]# lsattr 1
----i--------e-- 1
[root@xiaozhe0514 123]# rm -rf 1
rm: cannot remove ‘1’: Operation not permitted
[root@xiaozhe0514 123]# chattr -i 1
[root@xiaozhe0514 123]# lsattr 1
-------------e-- 1
[root@xiaozhe0514 123]# rm -rf 1 
[root@xiaozhe0514 123]# ls
```

 

Linux lsattr命令用于显示文件属性。

可以有效防止文件的重要文件被破坏

**chattr：**

```shell
用chattr执行改变文件或目录的属性，可执行lsattr指令查询其属性。
-a 　显示所有文件和目录，包括以"."为名称开头字符的额外内建，现行目录"."与上层目录".."。
-d 　显示，目录名称，而非其内容。
-l 　此参数目前没有任何作用。
-R 　递归处理，将指定目录下的所有文件及子目录一并处理。
-v 　显示文件或目录版本。
-V 　显示版本信息。
案例 :
[root@master ~]# chattr +i 123.sh 
[root@master ~]# lsattr 123.sh 
----i--------e-- 123.sh
[root@master ~]# chattr -i 123.sh 
[root@master ~]# lsattr 123.sh 
-------------e-- 123.sh
[root@master ~]# 

[root@master ~]# chattr +a 123.sh 
实现的效果只能进行追加数据  而不能进行删除    

```



**lsattr：**

用于查看特殊权限

```shell
-a 　显示所有文件和目录，包括以"."为名称开头字符的额外内建，现行目录"."与上层目录".."。
-d 　显示，目录名称，而非其内容。
-l 　此参数目前没有任何作用。
-R 　递归处理，将指定目录下的所有文件及子目录一并处理。
-v 　显示文件或目录版本。
-V 　显示版本信息。
[root@master ~]# lsattr 123.sh 
-------------e-- 123.sh
[root@master ~]# 
```





# 7.用户管理：

 linux是一个多用户多任务的操作系统   可以创建多个用户 批量执行任务的操作 

## 创建用户  

```shell
-c 用户说明 
-u (指定用户 uid 
-o 强制 uid 相同) 
-e 账号过期日期 
-f 密码到期宽限期 
-s 用户登录 shell
-g 用户主要组 
-G 用户附加组 
-d (用户家目录) 
-m (不存在则强制创建) 
-r 系统用户 用户名
root的用户uid是0     只要用户的id为0 那么就是root用户 可以进行创建多个  

案例：
#useradd -c "test user" -u 510 -d /rhome/mandy mandy
#useradd -s /sbin/nologin todd
#useradd -G teacher,student kevin
#useradd -e 2010/05/29 joshua
#useradd -f 0 ed
```



## 修改用户

```shell
#usermod -L kevin //锁定账号
#usermod -U kevin //解锁账号
#usermod -l mandy kevin //修改用户登录名为 mandy
#usermod -d /rhome/kevin -m kevin  //修改用户家目录
```



## 删除用户

```shell
#userdel kevin
#userdel -r levin  //将用户家目录及邮箱一起删除
```

## 修改用户口令passwd

```shell
#passwd kevin
#echo 'redhat' | passwd --stdin kevin  //设置用户口令
以下命令只能由 root 用户执行
#passwd -d kevin  //删除用户密码，用户可以空口令登录
#passwd -l kevin  //锁定用户
#passwd -u kevin  //解锁用户
#passwd -S kevin  //查看用户的密码信息
kevin LK 2010-11-01 0 99999 7 -1 （Password locked.）  //用户被锁定
kevin NP 2010-11-01 0 99999 7 -1 （Empty password） //用户口令为空
kevin PS 2010-11-01 0 99999 7 -1 （Password set，MD5 crypt.）  //用户口令已设
```

**口令加密算法：**

```shell
1. DES
早期 Linux 系统使用的加密算法，只能支持 8 位明文口令的加密。如果口令长度大于 8 位，则忽略8 位以后的字符。安全性较差。
2. MD5
RedHat 建议使用的加密算法，支持 256 位长度明文口令加密。
3. RedHat 系统在处理口令时，使用“加料”HASH 算法，即建立用户口令时，随机生成 2 位(DES)或 8位(MD5)长度明文字符串，然后用该字符串和用户口令一起进行 HASH，得到的结果保存在/etc/shadow 文件的第 2 个字段上。其中：XXKEYS 是 DES 算法得到的结果，$1$XXXXXXXX$KEYS 是MD5 得到的结果。
4. 如果需要和其它 UNIX/Linux 系统混合使用，可以使用 system-config-authentication 改变加密算法类型。
```



## 显示用户信息

```
$id kevin
whoami：显示用户登录名
who：显示用户登录信息
w可以详细查看用户登录
[root@localhost ~]# w
    21:52:39 up 40 min,  1 user,  load average: 0.00, 0.01, 0.05
    USER   TTY    FROM       LOGIN@  IDLE  JCPU  PCPU WHAT
    root   pts/0   192.168.6.58   21:15   7.00s  0.34s  0.00s w
[root@localhost ~]#
屏幕显示不全就会出现w: 66 column window is too narrow  然后扩大窗口就没事了 
```

**chage用户密码期限设置**

```shell
-l  查看用户信息
-E  账号过期时间（时间表示：2010/05/03）
-I  密码过期锁定账号宽限期（0：立即、>=1：宽限天数、-1：永不）
-M  密码最长使用期
-m  密码最短使用期
-W  密码到期前通知天数

以用户letuknowit为例（15400对应的日期为2012年3月1日），其保护如下信息：
   letuknowit:$1$cPf/cIvr$sCws95uSip2ljTK052DDB.:15400:5:60:7:2:15490:
　　用户letuknowit最近一次修改密码的日期是2012年3月1日， 
　　在2012年3月6日之前不能再改动密码了， 
　　在2012-3-1到2012-4-29期间letuknowit需要更改密码， 
　　在2012-4-29之前的7天，letuknowit登陆系统的时候，系统会提示letuknowit其密码即将过期， 
　　如果letuknowit一直到2012-4-29都没有修改密码，则其仍然可以继续使用该账户2天，2天后该账户将不可用 
　  无论如何，到了2012年5月29日，该账号都将失效
```

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps5-1618041013147.jpg) 

## 切换登录用户

```shell
su：更改为指定用户，不切换用户环境变量
su root   切换到root用户    不要层数嵌套的太多  
$su - root   切换到root的家目录中
```



## 用户相关配置文件

```shell
/etc/passwd：用户名、说明、登录 shell 
用户名  密码  UID  GID  用户说明  家目录  登录 shell
Root  X  0  0  root  /root  /bin/shell
/etc/shadow：用户密码、账号过期时间、密码过期宽限期等
Kevin  用户名
$1$NtH2oDq0$wOKX4yUwR)JXZehB9RagT.  加密密码
14109  自 1970.1.1 起密码使用天数
0  密码最短使用期
99999  密码最长使用期
7  密码到期前通知天数
0  密码失效宽限期（0：立即锁定账号，-1：永不锁定，>=1：宽限多少天）
14129  账号到期日期保留
/etc/login.defs：创建新用户的模版信息
/etc/skel/：用户家目录的登录文件(.bashrc，.bashprofile，.bash_logout)
```

 

# 8.磁盘管理

## 8.1 Dell服务器的硬件

 

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps6-1618041189241.jpg) 

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps7-1618041189242.jpg) 

## 8.2磁盘的阵列和分区

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps8-1618041189242.jpg) 

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps9-1618041189242.jpg) 

## 8.3 SAS-SATA-SSD-SCSI-IDE

常见的磁盘的接口在磁盘中的显示方式：

```shell
hd 表示 IDE 接口设备，每个 IDE 设备可以拥有 63 个分区
sd 表示 SCSI/SATA 接口设备，每个非 IDE 设备只能拥有 15 个分区
sda 表示第 1 个 SCSI/SATA 设备
sdad 表示第 30 个 SCSI/SATA 设备
vda虚拟机的磁盘文件  kvm虚拟化识别的文件
```

常见磁盘类型：SAS硬盘、SAS硬盘、SATA硬盘、SSD硬盘、SCSI硬盘、IDE硬盘你的服务器使用什么磁盘？

```shell
SAS硬盘：
SAS（串行连接SCSI接口）
SAS（Serial Attached SCSI），串行连接SCSI接口，串行连接小型计算机系统接口。
SAS是新一代的SCSI技术，和现在流行的Serial ATA(SATA)硬盘相同，都是采用串行技术以获得更高的传输速度，并通过缩短连结线改善内部空间等。
```

SAS的接口技术可以向下兼容SATA，SAS接口如图一、图二所示。

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps10-1618041189242.jpg) 

**图一 SAS接口**

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps11-1618041189242.jpg) 

**图二 SAS接口**

SAS和SATA接口对比，如图三所示

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps12.png) 

**图三 SAS和SATA接口对比图**

SAS 磁盘线，如图四所示

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps13-1618041189243.jpg) 

**图四 SAS磁盘线**

## 8.4磁盘尺寸

**3.5英寸设计**       **2.5英寸设计** 

此前主流的桌面磁盘和服务器磁盘都是采用3.5英寸设计，而SAS硬盘除了具有传统的3.5英寸规格之外，还采用了2.5英寸的缩小版，这样可以在机架式服务器有限的空间内安装更多的磁盘以扩充存储系统的容量，也能够为其他配件腾出更大的空间，以便通风散热，在2U高度内使用8个2.5英寸的SAS硬盘位已经成为大多数服务器厂商的选择。

已经被淘汰的硬盘：1.SCSI硬盘，如图五所示。2.IDE硬盘，如图六所示。

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps14-1618041189243.jpg) 

**图五SCSI硬盘**

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps15-1618041189243.jpg) 

**图六 IDE 硬盘**

数据线和电源接口，串型和并型 哪个快，如图七所示。

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps16-1618041189243.jpg) 

**图七 串型和并型**

```shell
并口为什么没有串口快？  
串口形容一下就是 一条车道，而并口就是有8个车道。同一时刻能传送8位（一个字节）数据。
但是并不是并口快，由于8位通道之间的互相干扰。传输受速度就受到了限制。当传输出错时，要同时重新传8个位的数据，而且传输速度越快，干扰越严重。这是硬伤，这样速度就无法提升上来。
串口没有干扰，传输出错后重发一位就可以了。而且串口传输的时钟频率要比并口高。
1956年，一台5mb的IBM硬盘被装上飞机，重量超过一吨
```

**当下流行的磁盘种类**

常见硬盘品牌：希捷  西数  日立   HP  DELL  EMC  IBM

```shell
硬盘分几种？
从工作原理来说：
固态：价格相对贵，寿命长，读取速度
机械：怕摔、怕磁，（单位换下来的坏盘会做消磁处理），读取速度---》磁道寻址时间，潜伏时间
从硬盘的接口来说
  STAT：用在低端服务器多
  SAS、SCSI：用在中高服务器
  PCIE M.2  接口硬盘
```

对LINUX来说，在内核中，不同的接口对应有不同的命名方式如图八所示

| 操作系统 | IDE      | STAT\|SCSI | SAS      |
| -------- | -------- | ---------- | -------- |
| RHEL5    | /dev/hda | /dev/sda   | /dev/sda |
| RHEL6    | /dev/sda | /dev/sda   | /dev/sda |
| KVM      | /dev/vda |            |          |

## 8.5磁盘分区工具 挂载分区

硬盘分区符认识

MBR概述：全称为Master Boot Record，即硬盘的主引导记录。

```shell
硬盘的0柱面、0磁头、1扇区称为主引导扇区（也叫主引导记录MBR）。它由三个部分组成，主引导程序、硬盘分区表DPT（Disk Partition table）和分区有效标志（55AA）。在总共512字节的主引导扇区里主引导程序（boot loader）占446个字节，第二部分是Partition table区（分区表），即DPT，占64个字节，硬盘中分区有多少以及每一分区的大小都记在其中。第三部分是magic number，占2个字节，固定为55AA结束的标志。
```

```shell
分区编号：主分区1-4 ，逻辑分区5
规定：逻辑分区必须建立在扩展分区之上，而不是建立在主分区上
分区作用：主分区：主要是用来启动操作系统的，它主要放的是操作系统的启动或引导程序，/boot分区最好放在主分区上
扩展分区不能使用的，它只是做为逻辑分区的容器存在的；我们真正存放数据的是主分区和逻辑分区，大量数据都放在逻辑分区中
如果你用的是GPT的分区方式，那么它没有限制主分区个数
```

注意：使用分区工具fdisk对磁盘进行操作，分区，格式化

```shell
[root@node1 ~]# ls /dev/sda*
/dev/sda  /dev/sda1  /dev/sda2
命名方式： /dev/sd[a-z]n  n  表示每块磁盘上划分的磁盘分区编号
其中：a-z 表示设备的序号，如sda表示第一块scsi硬盘，sdb就是第二块......如图九。
```

​	![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps17-1618041189243.jpg)

## 8.6fdisk管理分区

```shell
fdisk：磁盘分区,是Linux发行版本中最常用的分区工具
用法：fdisk [选项] device 	 
案例：在sdb盘上建一个分区，大小为100M
在虚拟机上添加一块硬盘，如图十所示。
```

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps18-1618041189256.jpg) 

**对sdb这块盘划分一个100M的分区出来**

```shell
[root@node1 ~]# fdisk  /dev/sdb
Command (m for help): m
Command action
  a  toggle a bootable flag
  b  edit bsd disklabel
  c  toggle the dos compatibility flag
  d  delete a partition  删除分区
  g  create a new empty GPT partition table
  G  create an IRIX (SGI) partition table
  l  list known partition types  显示分区类型
  m  print this menu  打印帮助菜单
  n  add a new partition  添加新的分区
  o  create a new empty DOS partition table
  p  print the partition table  显示分区表
  q  quit without saving changes  不保存，退出
  s  create a new empty Sun disklabel
  t  change a partition's system id  改变分区类型
  u  change display/entry units
  v  verify the partition table
  w  write table to disk and exit  写分区表信息到硬盘，保存操作并退出
  x  extra functionality (experts only)
Command (m for help): p  -----打印分区表
Command (m for help): n  ----新建一个分区
Partition type:
  p  primary (2 primary, 0 extended, 2 free)   p:主分区
  e  extended             e:扩展分区
Select (default p):   --直接默认
Using default response p
Partition number (1,4, default 1):  ---直接默认
First sector (1230848-41943039, default 1230848):  ---直接默认 
Using default value 1230848
Last sector, +sectors or +size{K,M,G} (1230848-41943039, default 41943039): +1G  输入分区大小
Partition 3 of type Linux and of size 1 GiB is set
Command (m for help): w  保存退出
[root@node1 ~]# ls /dev/sdb*
/dev/sdb  /dev/sdb1
```



**对已经在使用的磁盘进行分区，分区让新生成的分区生效。如果对sda再做一个sda4主分区**

**（1）进行分区**

```shell
[root@node1 ~]# fdisk  /dev/sda
命令(输入 m 获取帮助)：p
磁盘标识符：0x0005c80e
  设备 Boot    Start     End    Blocks  Id  System
/dev/sda1  *     2048    411647    204800  83  Linux
/dev/sda2      411648   2508799   1048576  82  Linux swap / Solaris
/dev/sda3     2508800   23480319   10485760  83  Linux 
命令(输入 m 获取帮助)：n
Partition type:
  p  primary (3 primary, 0 extended, 1 free)
  e  extended
Select (default e): p
已选择分区 4
起始 扇区 (23480320-41943039，默认为 23480320)：
将使用默认值 23480320
Last 扇区, +扇区 or +size{K,M,G} (23480320-41943039，默认为 41943039)：+1G
分区 4 已设置为 Linux 类型，大小设为 1 GiB
命令(输入 m 获取帮助)：w
The partition table has been altered!
Calling ioctl() to re-read partition table.
WARNING: Re-reading the partition table failed with error 16: 设备或资源忙.
The kernel still uses the old table. The new table will be used at
the next reboot or after you run partprobe(8) or kpartx(8)
```

**让新生成的分区生效**

 ```shell
[root@node1 ~]# reboot  #这个是最好的方法
[root@node1 ~]# partx -a  /dev/sda  #获得新分区表  推荐使用
[root@node1 ~]# mkfs.ext4  /dev/sdb1 
[root@node1 ~]# mkfs.xfs  /dev/sdb1  #格式化，-f 对已经存在文件系统的分区，强制格式化
[root@node1~]#  mkdir /sdb1  #创建挂载点
[root@node1 ~]# mount  /dev/sdb1  /sdb1/   #挂载
[root@node1 ~]# df -h   #查看
文件系统     容量  已用  可用 已用% 挂载点
/dev/sda3     10G  4.3G  5.8G  43% /
devtmpfs     982M   0  982M   0% /dev
tmpfs      997M   0  997M   0% /dev/shm
tmpfs      997M  9.0M  988M   1% /run
tmpfs      997M   0  997M   0% /sys/fs/cgroup
/dev/sr0     4.3G  4.3G   0  100% /mnt
/dev/sda1    197M  172M  25M  88% /boot
tmpfs      200M  24K  200M   1% /run/user/0
/dev/sdb1    1014M  33M  982M   4% /sdb1
[root@node1 ~]# cd /sdb1/  #使用新分区
[root@node1 sdb1]# ls
[root@node1 sdb1]# cp -rvf /etc/passwd /sdb1/
 ```



**（3）解决卸载不了的问题**

```shell
root@node1 ~]# cd /sdb1/
[root@node1 sdb1]# umount /sdb1
umount: /sdb1：目标忙。 有用户占用该文件夹   cd ..
(有些情况下通过 lsof(8) 或 fuser(1) 可以找到有关使用该设备的进程的有用信息)
[root@node1 sdb1]# lsof /sdb1    
COMMAND  PID USER  FD  TYPE DEVICE SIZE/OFF NODE NAME
bash   2823 root  cwd   DIR  8,17    20  64 /sdb1
lsof   2952 root  cwd   DIR  8,17    20  64 /sdb1
lsof   2953 root  cwd   DIR  8,17    20  64 /sdb1
方法1：[root@node1 sdb1]# kill -9 2823
方法2：[root@node1 sdb1]# cd   #退出目录，这个最合适
 [root@node1 ~]# umount  /dev/sdb1
注：umount 挂载点  //卸载方式1   或 umount 设备路径  //卸载方式2
[root@node1 /]# echo "/dev/sdb1 /sdb1 xfs defaults 0 0" >> /etc/fstab    只是用追加方式进行写入
[root@node1 ~]# mount -a  #自动挂载/etc/fstab中没有挂载上的文件
[root@node1 ~]# df -h
文件系统     容量  已用  可用 已用% 挂载点
/dev/sda3     10G  4.3G  5.8G  43% /
devtmpfs     982M   0  982M   0% /dev
tmpfs      997M   0  997M   0% /dev/shm
tmpfs      997M  9.0M  988M   1% /run
tmpfs      997M   0  997M   0% /sys/fs/cgroup
/dev/sr0     4.3G  4.3G   0  100% /mnt
/dev/sda1    197M  172M  25M  88% /boot
tmpfs      200M  24K  200M   1% /run/user/0
/dev/sdb1    1014M  33M  982M   4% /sdb1  
发现已经挂载上，说明配置没有问题。 然后再重启，看看挂载
使用uuid进行永久的挂载   建立使用的方式
[root@node1 ~]# blkid
/dev/sda1: UUID="a635d4d2-a21e-4d9b-b199-4c8d5cfed808" TYPE="xfs" 
/dev/sda2: UUID="46f139f8-fd5c-4e51-8d5c-b33f6c7aa38e" TYPE="swap" 
/dev/sda3: UUID="4bcb433e-10e6-464d-a40b-00d018950149" TYPE="xfs" 
/dev/sdb1: UUID="5e3a580a-e5b4-448c-88bf-d22fb3d1d9e2" TYPE="xfs"
[root@node1 /]# echo "UUID=5e3a580a-e5b4-448c-88bf-d22fb3d1d9e2  /sdb1  xfs defaults 0 0" >> /etc/fstab
[root@node1 /]# mount -a 
```



**扩展：/etc/fstab/如何配置**

| **/dev/sdb1**        | **/sdb1**  | **xfs**          | **defaults** | **0**        | **0**        |
| -------------------- | ---------- | ---------------- | ------------ | ------------ | ------------ |
| **要挂载的分区设备** | **挂载点** | **文件系统类型** | **挂载选项** | **是否备份** | **是否检测** |

第四列：parameters-文件系统的参数

| **Async/sync**  | **设置是否为同步方式运行，默认为async**                      |
| --------------- | ------------------------------------------------------------ |
| **auto/noauto** | **当执行mount -a 的命令时，此文件系统是否被主动挂载。默认为auto** |
| **rw/ro**       | **是否以以只读或者读写模式挂载**                             |
| **exec/noexe**  | **限制此文件系统内是否能够进行"执行"的操作**                 |
| **user/nouser** | **是否允许用户使用mount命令挂载**                            |
| **suid/nosuid** | **是否允许SUID的存在**                                       |
| **Usrquota**    | **启动文件系统支持磁盘配额模式**                             |
| **Grpquota**    | **启动文件系统对群组磁盘配额模式的支持**                     |
| **Defaults**    | **同时具有rw,suid,dev,exec,auto,nouser,async等默认参数的设置 samba nfs** |

第五列：是否进行备份。通常这个参数的值为0或者1

| **0** | **代表不要做备份**         |
| ----- | -------------------------- |
| **1** | **代表要每天进行操作**     |
| **2** | **代表不定日期的进行操作** |

第六列：是否检验扇区：开机的过程中，系统默认会以fsck检验我们系统是否为完整

| **0** | **不要检验**                     |
| ----- | -------------------------------- |
| **1** | **最早检验（一般根目录会选择）** |
| **2** | **1级别检验完成之后进行检验**    |

## 8.7gdisk 磁盘分区工具

gdisk主要是用来划分容量大于4T的硬盘,大于4T fdisk搞不定

两种类型的分区表：GPT和MBR  ； MBR不支持4T以上。

GPT分区：GPT，全局唯一标识分区表(GUID Partition Table)，它使用128位GUID来唯一标识每个磁盘和分区，与MBR存在单一故障点不同，GPT提供分区表信息的冗余，一个在磁盘头部一个在磁盘尾部；它通过CRC校验和来检测GPT头和分区表中的错误与损坏；默认一个硬盘支持**128**个分区

**（1）对sdb做gpt分区，创建一个sdb1**

```shell
[root@node1 ~]# parted /dev/sdb
GNU Parted 3.1
使用 /dev/sdb
Welcome to GNU Parted! Type 'help' to view a list of commands.
(parted) mklabel gpt    #选择gpt模式                        
(parted) print                               
Model: VMware, VMware Virtual S (scsi)
Disk /dev/sdb: 3299GB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 
Number  Start  End  Size  File system  Name  标志
(parted) mkpart primary 0% 100%     #设置分区大小（全部）                  
(parted) print                               
Model: VMware, VMware Virtual S (scsi)
Disk /dev/sdb: 3299GB
Sector size (logical/physical): 512B/512B
Partition Table: gpt
Disk Flags: 
Number  Start  End   Size   File system  Name   标志
 1    1049kB  3299GB  3299GB        primary
(parted) quit                               
信息: You may need to update /etc/fstab.
[root@node1 ~]# fdisk -l
磁盘 /dev/sdb：3298.5 GB, 3298534883328 字节，6442450944 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
磁盘标签类型：dos
磁盘标识符：0x00000000 
  设备 Boot    Start     End    Blocks  Id  System
/dev/sdb1        1  4294967295  2147483647+  ee  GPT
磁盘 /dev/sda：53.7 GB, 53687091200 字节，104857600 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
磁盘标签类型：dos
磁盘标识符：0x000734bf
  设备 Boot    Start     End    Blocks  Id  System
/dev/sda1  *     2048   1026047    512000  83  Linux
/dev/sda2     1026048  104857599   51915776  8e  Linux LVM 
磁盘 /dev/mapper/centos-root：49.0 GB, 48951721984 字节，95608832 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
磁盘 /dev/mapper/centos-swap：4160 MB, 4160749568 字节，8126464 个扇区
Units = 扇区 of 1 * 512 = 512 bytes
扇区大小(逻辑/物理)：512 字节 / 512 字节
I/O 大小(最小/最佳)：512 字节 / 512 字节
[root@node1 ~]# mkfs.ext4 /dev/sdb1 #格式化
mke2fs 1.42.9 (28-Dec-2013)
文件系统标签=
OS type: Linux
块大小=4096 (log=2)
分块大小=4096 (log=2)
Stride=0 blocks, Stripe width=0 blocks
201326592 inodes, 805305856 blocks
40265292 blocks (5.00%) reserved for the super user
第一个数据块=0
Maximum filesystem blocks=2952790016
24576 block groups
32768 blocks per group, 32768 fragments per group
8192 inodes per group
Superblock backups stored on blocks: 
​    32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
​    4096000, 7962624, 11239424, 20480000, 23887872, 71663616, 78675968, 
​    102400000, 214990848, 512000000, 550731776, 644972544
Allocating group tables:             
正在写入inode表:          
Creating journal (32768 blocks): 
Writing superblocks and filesystem accounting information:   
```



**（2）修改/etc/fstab文件后重启系统后系统报错：**

重启后报错如图十一所示：

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps19.jpg) 

```
修复方法
输入root密码
[root@node1 ~]# vi /etc/fstab 
在fstab中把新添加的磁盘直接删除，最后reboot
```



## 8.8swap分区

### 8.8.1创建交换分区

Swap介绍：

Linux 将物理内存分为内存段，叫做页面。交换是指内存页面被复制到预先设定好的硬盘空间(叫做交换空间)的过程，目的是释放对于页面的内存。物理内存和交换空间的总大小是可用的虚拟内存的总量。Swap即：交换分区，类似于Windows的虚拟内存，但物理内存不足时，把部分硬盘空间当成虚拟内存使用，从而解决了物理内存容量不足。

优点：节省成本。

缺点：性能不足。

如果系统的物理内存用光了，系统就会跑得很慢，但仍能运行;如果Swap空间用光了，那么系统就会发生错误。例如，Swap空间用完，则服务进程无法启动，通常会出现“application is out of memory”的错误，严重时会造成服务进程的死锁。因此Swap空间的分配是很重要的,通常Swap空间的大小应是物理内存的2-2.5倍.		

删除/etc/fstab文件  然后再执行swapon -a Swap分区在系统的物理内存不够用的时候，把硬盘空间中的一部分空间释放出来，以供当前运行的程序使用。

**使用分区作为swap：**

```shell
先划分swap需要的分区空间
[root@node1 ~]# fdisk  /dev/sdb
Command (? for help): n  #新建分区
Partition number (2-128, default 2):   #回车
First sector (34-41943006, default = 2099200) or {+-}size{KMGTP}:  #回车
Last sector (2099200-41943006, default = 41943006) or {+-}size{KMGTP}: +1G  #给1G
Current type is 'Linux filesystem'
命令(输入 m 获取帮助)：t
已选择分区 1
Hex 代码(输入 L 列出所有代码)：82
已将分区“Linux”的类型更改为“Linux swap / Solaris”
命令(输入 m 获取帮助)：quit
格式化swap
[root@node1 ~]# mkswap /dev/sdb1
正在设置交换空间版本 1，大小 = 2147483640 KiB
无标签，UUID=cb368b8d-98cd-465c-8ce7-6d5e4a2b059c
验证：
[root@node1 ~]# free -m
​       total     used     free    shared  buff/cache  available
Mem:      3776     110     3412      8     253     3453
Swap:      3967      0     3967
[root@node1 ~]# swapon /dev/sdb1  ---开启
[root@node1 ~]# free -m
​       total     used     free    shared  buff/cache  available
Mem:      3776     1714     1808      8     253     1849
Swap:    2101119      0   2101119
[root@node1 ~]# swapoff /dev/sdb1  ---关闭
[root@node1 ~]# free -m
​       total     used     free    shared  buff/cache  available
Mem:      3776     111     3410      8     253     3451
Swap:      3967      0     3967
[root@node1 ~]# swapon -s
文件名              类型       大小   已用   权限
/dev/dm-1                partition    4063228 0    -1
[root@node1 ~]# swapon /dev/sdb1
[root@node1 ~]# swapon -s  #查看
文件名              类型       大小   已用   权限
/dev/dm-1                partition    4063228 0    -1
/dev/sdb1                partition    2147483640    0    -2



12.3.2  通过文件增加SWAP空间
[root@node1 ~]# dd if=/dev/zero of=swap_file bs=1M count=500
记录了500+0 的读入
记录了500+0 的写出
524288000字节(524 MB)已复制，3.08029 秒，170 MB/秒
[root@node1 ~]# ll /root/swap_file
-rw-r--r-- 1 root root 524288000 10月  2 22:47 /root/swap_file
[root@node1 ~]# chmod 0600 /root/swap_file
[root@node1 ~]# mkswap -f /root/swap_file 
正在设置交换空间版本 1，大小 = 511996 KiB
无标签，UUID=3af7b41d-9745-4df1-a394-5a5c8e1f49f1
[root@node1 ~]# swapon /root/swap_file
[root@node1 ~]# free -m
​       total     used     free    shared  buff/cache  available
Mem:      3776     1715     1294      8     766     1842
Swap:    2101619      0   2101619
```

### 8.8.2使用磁盘文件创建分区：

```shell
1.在磁盘上创建一个文件：
[root@localhost ~]# dd if=/dev/zero of=/mnt/p1 bs=1M count=20
20+0 records in
20+0 records out
20971520 bytes (21 MB) copied, 0.0215119 s, 975 MB/s
[root@localhost ~]# fdisk /mnt/p1 
Welcome to fdisk (util-linux 2.23.2).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.
Device does not contain a recognized partition table
Building a new DOS disklabel with disk identifier 0xebbd45c9.
Command (m for help): p
Disk /mnt/p1: 20 MB, 20971520 bytes, 40960 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0xebbd45c9
  Device Boot    Start     End    Blocks  Id  System
Command (m for help): n
Partition type:
  p  primary (0 primary, 0 extended, 4 free)
  e  extended
Select (default p): p
Partition number (1-4, default 1): 
First sector (2048-40959, default 2048): 
Using default value 2048
Last sector, +sectors or +size{K,M,G} (2048-40959, default 40959): //默认的使用全部的大小
Using default value 40959
Partition 1 of type Linux and of size 19 MiB is set
Command (m for help): p
Disk /mnt/p1: 20 MB, 20971520 bytes, 40960 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0xebbd45c9
  Device Boot    Start     End    Blocks  Id  System
/mnt/p1p1       2048    40959    19456  83  Linux
Command (m for help): w
The partition table has been altered!
Syncing disks.
[root@localhost ~]#mkfs.ext4 /mnt/p1  // 格式化分区
[root@localhost ~]#mkdir /p1  // 创建挂载点
[root@localhost ~]#mount -o loop /mnt/p1 /p1  //挂载
[root@localhost ~]#echo "/mnt/p1 /p1 ext4 defaults 0 0" >> /etc/fstab  //永久挂载
[root@localhost ~] mount -a 
```



**不关机刷新磁盘**

```shell
echo "- - -" > /sys/class/scsi_host/host0/scan
echo "- - -" > /sys/class/scsi_host/host1/scan
echo "- - -" > /sys/class/scsi_host/host2/scan
```

 



## 8.9LVM管理

LVM（Logical Volume Manager）：首先是基于实际的物理磁盘创建LVM分区，并创建物理卷PV。一个或多个物理卷可以用来创建卷组VG。然后基于卷组可以创建逻辑卷LV。只要在卷组中有可用空间，就可以随心所欲的创建逻辑卷。文件系统就是在逻辑卷上创建的，然后可以在操作系统中挂载和使用。

**物理长度PE**（PhysicalExtent）：物理长度是将物理卷组合为卷组后，所划分的最小存储单位，即逻辑意义上磁盘的最小存储单位。LVM默认PE大小为4MB。   手动可以指定pe的大小

**物理卷PV**（PhysicalVolume）：物理卷是LVM的最底层概念，是LVM的逻辑存储块，物理卷与磁盘分区是逻辑的对应关系。

**卷组VG**（VolumeGroup）：卷组是LVM逻辑概念上的磁盘设备，通过将单个或多个物理卷组合后生成卷组。卷组的大小取决于物理卷的容量以及个数。

**逻辑卷LV**（LogicalVolume）：逻辑卷就是LVM逻辑意义上的分区，可以指定从卷组中提取多少容量来创建逻辑卷，最后对逻辑卷格式化并挂载使用。

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps20.jpg) 



**常用命令的使用：**

```shell
pvcreate 设备名
vgcreate 卷组名  物理卷1  物理卷2 
lvcreate -L 大小  -n 逻辑名  卷组名
lvextend -L +大小  /dev/卷组名/逻辑卷名
```

```shell
create  建立   pvcreate   vgcreate   lvcreate 
display 显示   pvdisplay  vgdisplay  lvdisplay
remove 删除    pvremove   vgremove   lvremove 
extend 扩展				vgextend   lvexted 
```

**创建LVM逻辑卷：**

​	环境：添加一块硬盘，划分4个分区分别sdb1-----sdb4  然后创建lvm卷。7以上的系统可以使用普通分区创建逻辑卷，建议转换成8e（lvm）。

```shell
============================================================================================
创建PV
[root@test ~]# pvcreate /dev/sdb{1,2,3,4}
 Physical volume "/dev/sdb1" successfully created.
 Physical volume "/dev/sdb2" successfully created.
 Physical volume "/dev/sdb3" successfully created.
 Physical volume "/dev/sdb4" successfully created.
[root@test ~]# pvs
 PV     VG Fmt  Attr PSize  PFree
 /dev/sda2  cl lvm2 a--  39.00g 4.00m
 /dev/sdb1   lvm2 ---  1.00g 1.00g
 /dev/sdb2   lvm2 ---  1.00g 1.00g
 /dev/sdb3   lvm2 ---  1.00g 1.00g
 /dev/sdb4   lvm2 ---  1.00g 1.00g
[root@test ~]#
=============================================================================================
创建VG
[root@test ~]# vgcreate vg01 /dev/sdb{1,2,3,4}
 Volume group "vg01" successfully created
[root@test ~]# vgs 
 VG  #PV #LV #SN Attr  VSize  VFree
 cl   1  2  0 wz--n- 39.00g 4.00m
 vg01  4  0  0 wz--n-  3.98g 3.98g
[root@test ~]#
创建LV
[root@test ~]# lvcreate -n lv01 -L 2G vg01
 Logical volume "lv01" created.
[root@test ~]# lvs
 LV  VG  Attr    LSize  Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
 root cl  -wi-ao---- 36.99g                           
 swap cl  -wi-ao----  2.00g                           
 lv01 vg01 -wi-a-----  2.00g                           
[root@test ~]#
====================================================================================
格式化和创建挂载点
[root@test ~]# mkdir /lvm01
[root@test ~]# mkfs.ext4 /dev/vg01/lv01
挂载lv到挂载点
[root@test ~]# mount /dev/vg01/lv01 /lvm01/
[root@test ~]# df -Th /lvm01/
文件系统        类型  容量  已用  可用 已用% 挂载点
/dev/mapper/vg01-lv01 ext4  2.0G  6.0M  1.8G   1% /lvm01
[root@test ~]#
设置永久挂载：
[root@test ~]# echo '/dev/vg01/lv01 /lvm01 ext4 defaults 0 0 ' >> /etc/fstab LVM在线扩容
[root@test ~]# mount -a
```

 **扩大逻辑卷LVM**

先查看vg是否有容量可以增加如果容量不够先增加vg然后再增加lvm，因为lvm需要在vg中增加

```shell
[root@test ~]# vgs
 VG  #PV #LV #SN Attr  VSize  VFree
 cl   1  2  0 wz--n- 39.00g 4.00m
vg01  4  1  0 wz--n-  3.98g 1.98g
[root@test ~]#
```

```shell
说明：在指定大小的时候，扩容30m和扩容到30m是不一样的写法
扩容30m ====> -L +30M
扩容到30m =====> -L 30M

[root@test ~]#  lvextend -L +30m /dev/vg01/lv01  
 Rounding size to boundary between physical extents: 32.00 MiB.
 Size of logical volume vg01/lv01 changed from 2.00 GiB (512 extents) to 2.03 GiB (520 extents).
 Logical volume vg01/lv01 successfully resized.
[root@test ~]# lvs 
 LV  VG  Attr    LSize  Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
 root cl  -wi-ao---- 36.99g                           
 swap cl  -wi-ao----  2.00g                           
 lv01 vg01 -wi-ao----  2.03g                           
[root@test ~]#
[root@test ~]# df -Th /lvm01/
文件系统        类型  容量  已用  可用 已用% 挂载点
/dev/mapper/vg01-lv01 ext4  2.0G  6.0M  1.8G   1% /lvm01
[root@test ~]#
容量已经扩容了，但是文件系统还没有扩容
[root@test ~]#  resize2fs /dev/vg01/lv01
resize2fs 1.42.9 (28-Dec-2013)
Filesystem at /dev/vg01/lv01 is mounted on /lvm01; on-line resizing required
old_desc_blocks = 1, new_desc_blocks = 1
The filesystem on /dev/vg01/lv01 is now 532480 blocks long. 
[root@test ~]# df -Th /lvm01/
文件系统        类型  容量  已用  可用 已用% 挂载点
/dev/mapper/vg01-lv01 ext4  2.0G  6.0M  1.9G   1% /lvm01
[root@test ~]#
```

```shell
ext4文件系统扩容使用命令语法： resize2fs  逻辑卷名称
xfs文件系统扩容使用命令语法：  xfs_growfs  挂载点
resize2fs和xfs_growfs 两者的区别是传递的参数不一样的，xfs_growfs是采用的挂载点；resize2fs是逻辑卷名称，而且resize2fs命令不能对xfs类型文件系统使用
```

**逻辑卷的缩小LVM**

LVM可以动态增加，也可以动态缩小，但是XFS不支持动态缩小，所以我们无法实现基于xfs的动态缩小。btrfs文件系统支持在线缩小。

```shell
步骤描述：
1、缩小前，先卸载/dev/vg/home【扩容不需要卸载】 
2、强制检查/dev/vg/home文件系统的正确性 
3、先缩小/dev/vg/home文件系统的大小 
4、再缩小LVM大小 
5、挂载所有分区	
```

**LVM snapshot应用**

```shell
创建快照卷：
lvcreate [选项] [参数]
选项： 
-L：指定大小
-l：指定大小（LE数）
-n：指定名称
-s：创建快照
-p r：设置为只读
```

```shell
例如 lvcreate -s -L 512M -n mylv_snap -p r /dev/myvg/mylv # 针对逻辑卷mylv创建大小为512M的只读快照
注：创建快照前需将针对的逻辑卷临时改为只读，创建完毕后再改为读写，例如
创建快照前：mount -o remount,ro /dev/myvg/mylv /data
创建快照后：mount -o remount,rw /dev/myvg/mylv /data
```



###  8.9.1分区生效

```shell
# partx -a /dev/sdb
# cat /proc/partitions   //查看分区的信息 
刷新分区表命令：
partprobe在不重启的情况下重读分区。
partx命令告用来诉内核当前磁盘的分区情况
partprobe /dev/sdb
  当磁盘分区信息完整时，手动删除/dev/disk/by-id目录下对应的wwn链接文件，执行partprobe操作，系统会自己创建删除的链接文件。
```

###  8.9.2madam创建硬盘软件阵列

```shell
1.配置yum文件和检查是否安装了mdadm软件
创建raid0 磁盘文件  
[root@localhost yum.repos.d]# yum install madam 
[root@localhost ~]# fdisk /dev/sdb 
Welcome to fdisk (util-linux 2.23.2).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command. 
Device does not contain a recognized partition table
Building a new DOS disklabel with disk identifier 0xd58fa7d6. 
Command (m for help): p 
Disk /dev/sdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0xd58fa7d6
  Device Boot    Start     End    Blocks  Id  System
Command (m for help): n
Partition type:
  p  primary (0 primary, 0 extended, 4 free)
  e  extended
  Select (default p): p
Partition number (1-4, default 1): 
First sector (2048-83886079, default 2048): 
Using default value 2048
Last sector, +sectors or +size{K,M,G} (2048-83886079, default 83886079): +20G
Partition 1 of type Linux and of size 20 GiB is set 
Command (m for help): n
Partition type:
  p  primary (1 primary, 0 extended, 3 free)
  e  extended
Select (default p): p
Partition number (2-4, default 2): 
First sector (41945088-83886079, default 41945088): 
Using default value 41945088
Last sector, +sectors or +size{K,M,G} (41945088-83886079, default 83886079): 
Using default value 83886079
Partition 2 of type Linux and of size 20 GiB is set 
Command (m for help): p 
Disk /dev/sdb: 42.9 GB, 42949672960 bytes, 83886080 sectors
Units = sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk label type: dos
Disk identifier: 0xd58fa7d6
  Device Boot    Start     End    Blocks  Id  System
/dev/sdb1       2048   41945087   20971520  83  Linux
/dev/sdb2     41945088   83886079   20970496  83  Linux
Command (m for help): w
The partition table has been altered! 
Calling ioctl() to re-read partition table.
Syncing disks.
[root@localhost ~]# partx /dev/sdb 
NR   START    END  SECTORS SIZE NAME UUID
 1   2048 41945087 41943040  20G    
 2 41945088 83886079 41940992  20G    
[root@localhost ~]# mdadm -Cv /dev/md0 -l 0 -n 2 /dev/sdb1 /dev/sdb2 //创建raid0
mdadm: chunk size defaults to 512K
mdadm: Defaulting to version 1.2 metadata
mdadm: array /dev/md0 started.
[root@localhost ~]# cat /proc/mdstat    查看状态
Personalities : [raid0] 
md0 : active raid0 sdb2[1] sdb1[0]
   41909248 blocks super 1.2 512k chunks
unused devices: <none>
[root@localhost ~]# mdadm -Ds  
ARRAY /dev/md0 metadata=1.2 name=localhost.localdomain:0 UUID=9ebcd5bb:e2286ea1:84e18c5e:122be3c0
[root@localhost ~]# mdadm -D /dev/md0 
/dev/md0:
​    Version : 1.2
 Creation Time : Mon Feb 17 23:32:05 2020
   Raid Level : raid0
   Array Size : 41909248 (39.97 GiB 42.92 GB)
  Raid Devices : 2
 Total Devices : 2
  Persistence : Superblock is persistent 
  Update Time : Mon Feb 17 23:32:05 2020
​     State : clean 
 Active Devices : 2
Working Devices : 2
 Failed Devices : 0
 Spare Devices : 0 
   Chunk Size : 512K
​      Name : localhost.localdomain:0  (local to host localhost.localdomain)
​      UUID : 9ebcd5bb:e2286ea1:84e18c5e:122be3c0
​     Events : 0
  Number  Major  Minor  RaidDevice State
​    0    8    17     0    active sync  /dev/sdb1
​    1    8    18     1    active sync  /dev/sdb2
[root@localhost ~]# mdadm -Ds > /etc/mdadm.conf   写入配置文件
[root@localhost ~]# mkfs.xfs /dev/md0      格式化分区 
meta-data=/dev/md0        isize=256   agcount=16, agsize=654720 blks
​     =            sectsz=512  attr=2, projid32bit=1
​     =            crc=0     finobt=0
data   =            bsize=4096  blocks=10475520, imaxpct=25
​     =            sunit=128   swidth=256 blks
naming  =version 2        bsize=4096  ascii-ci=0 ftype=0
log    =internal log      bsize=4096  blocks=5120, version=2
​     =            sectsz=512  sunit=8 blks, lazy-count=1
realtime =none          extsz=4096  blocks=0, rtextents=0
[root@localhost ~]# mkdir /raid0   创建挂载点
[root@localhost ~]# mount /dev/md0 /raid0/   进行挂载
[root@localhost ~]# df -TH   显示挂载情况
Filesystem        Type    Size  Used Avail Use% Mounted on
/dev/mapper/centos-root xfs     42G  1.2G  41G  3% /
devtmpfs         devtmpfs  1.1G   0  1.1G  0% /dev
tmpfs          tmpfs   1.1G   0  1.1G  0% /dev/shm
tmpfs          tmpfs   1.1G  9.0M  1.1G  1% /run
tmpfs          tmpfs   1.1G   0  1.1G  0% /sys/fs/cgroup
/dev/mapper/centos-home xfs     21G  34M  21G  1% /home
/dev/sda1        xfs    521M  113M  409M  22% /boot
tmpfs          tmpfs   209M   0  209M  0% /run/user/0
/dev/sr0         iso9660  4.4G  4.4G   0 100% /opt/centos
/dev/md0         xfs     43G  35M  43G  1% /raid0
[root@localhost ~]# blkid /dev/md0 
/dev/md0: UUID="bc8d1c82-9597-4cd4-8520-febeb56b857c" TYPE="xfs" 
[root@localhost ~]# echo "UUID="bc8d1c82-9597-4cd4-8520-febeb56b857c" /raid0 xfs defaults 0 0 " >> /etc/fstab 
[root@localhost ~]# mount -a 
```

**使用文件创建Raid0**

```shell
[root@localhost ~]# dd if=/dev/zero of=/raid0/dd bs=1M count=10
10+0 records in
10+0 records out
10485760 bytes (10 MB) copied, 0.0178424 s, 588 MB/s
[root@localhost ~]# du -sh /raid0/dd 
[root@localhost /]# reboot
卸载raid0
[root@localhost ~]# umount /raid0/
[root@localhost ~]# mdadm -S /dev/md0
[root@localhost ~]# rm -rf /etc/mdadm.conf
[root@localhost ~]# rm -rf /raid0/
[root@localhost ~]# mdadm --zero-superblock /dev/sdb1   //删除superblock文件
[root@localhost ~]# mdadm --zero-superblock /dev/sdb2   //删除superblock文件
使用vim删除/etc/fstab文件中UUID=8eafdcb6-d46a-430a-8004-d58a68dc0751 /raid0 xfs defaults 0 0 内容  最后保存退出
```

创建raid5和创建raid0类似  加上一个热备盘  ，虚拟机添加3快20G盘做成raid5  一块制作热备盘  模拟模拟故障出现  

```shell
[root@localhost ~]# mdadm -Cv /dev/md5 -l5 -n3 /dev/sdb1 /dev/sdb2 /dev/sdb3 --spare-devices=1 /dev/sdb4
mdadm: layout defaults to left-symmetric
mdadm: layout defaults to left-symmetric
mdadm: chunk size defaults to 512K
mdadm: size set to 20954112K
mdadm: Defaulting to version 1.2 metadata
mdadm: array /dev/md5 started.
[root@localhost ~]# mdadm -D /dev/md5 
/dev/md5:
​    Version : 1.2
 Creation Time : Tue Feb 18 00:35:54 2020
   Raid Level : raid5
   Array Size : 41908224 (39.97 GiB 42.91 GB)
 Used Dev Size : 20954112 (19.98 GiB 21.46 GB)
  Raid Devices : 3
 Total Devices : 4
  Persistence : Superblock is persistent
  Update Time : Tue Feb 18 00:36:14 2020
​     State : clean, degraded, recovering 
 Active Devices : 2
Working Devices : 4
 Failed Devices : 0
 Spare Devices : 2
​     Layout : left-symmetric
   Chunk Size : 512K 
 Rebuild Status : 23% complete 
​      Name : localhost.localdomain:5  (local to host localhost.localdomain)
​      UUID : c0b13a49:1518f9fe:c70f302b:c943ffa2
​     Events : 4 
  Number  Major  Minor  RaidDevice State
​    0    8    17     0    active sync  /dev/sdb1
​    1    8    18     1    active sync  /dev/sdb2
​    4    8    19     2    spare rebuilding  /dev/sdb3
​    3    8    20     -    spare  /dev/sdb4
[root@localhost ~]#  
```



**企业级riad0**

**1、搭建及使用**

**Raid0** 

```shell
mdadm –C –v /dev/md0 –l 0 –n 2 /dev/sdb /dev/sdc
-C参数代表创建一个RAID阵列卡；
-v参数显示创建的过程，同时在后面追加一个设备名称/dev/md0， 
-a yes参数代表自动创建设备文件；
-n 2参数代表使用2块硬盘来部署这个RAID磁盘阵列；
-l 0参数则代表RAID 0


mdadm –C –v /dev/md0 –l 0 –n 2 /dev/sdb /dev/sdc
mdadm –Dvs /dev/md0 #查看阵列的信息
mdadm –Dvs /dev/md0 >/etc/mdadm.conf#将阵列的详细信息写成配置文件
cat /proc/mdstat
mkfs.xfs /dev/md0#把制作好的RAID磁盘阵列格式化为ext4格式
mkdir /radi0
mount /dev/md0 /mdstat#挂载
```

**Raid1**

```shell
mdadm –C –v /dev/md1 –l 1 –n 2 –x 1 /dev/sdd /dev/sde /dev sdf
mdadm –Dvs /dev/md1 >/etc/mdadm.conf
mkfs.xfs /dev/md1
mkdir /radi1
mount /dev/md1 /mdstat
mdadm  /dev/md1 –f /dev/sde
mdadm –r /dev/sde
mdadm –a /dev/sde /dev/md1
```

**RIAD5、10，配置讲解**

```shell
mdadm –C –v /dev/md5 –l 5 –n 3 –x 1 –c 32 /dev/sd{g,h,I,j}
mdadm –Dvs /dev/md5 #查看RAID5的信息
mdadm –Dvs /dev/md5 > /etc/mdadm.conf #将阵列信息写入配置文件
#cat /proc/mdstat 可以查看
mkfs.xfs /dev/md5 #格式化阵列后方可使用
mkdir /radi5#创建挂载目录
mount /dev/md5 /mdstat#挂载使用
```

 

**停止和启动**

```shell
mdadm –Dvs > /etc/mdadm.conf #停止前一定要保存好配置文件
mdadm –D /dev/md5 #确认数据同步完成
mdadm –S /dev/md5 #停止阵列
mdadm –As #启动阵列 
```

**在线扩容**

```shell
mdadm –G /dev/md5 –n 4 –c 32#将热备盘加入到阵列中
mdadm –Dvs /dev/md5 #查看详细信息 此时热备盘被加入到阵列中
```

**RAID10**

```shell
mdadm –C –v /dev/md10 –l 0 –n 4 /dev/sdk /dev/sdm /dev/sdn /dev/sdo
mdadm –C –v /dev/md10 –l 0 –n 4 /dev/sdk[1-4] #用sdk的四个分区做阵列
mdadm –Dvs /dev/md10
mdadm –Dvs /dev/md10 >/etc/mdadm.conf
cat /proc/mdstat
mkfs.xfs /dev/md10
mkdir /radi10
mount /dev/md10 /mdstat
```

**删除RAID**

```shell
umount /dev/md0 /radi0 #如果挂载需要卸载
mdadm –Ss #暂停阵列
rm –rf /etc/mdadm.conf#删除配置文件
mdadm --zero-surperblock /dev/sdb#清除raid标识
mdadm –zero-surperblock /dev/sdc#清除raid标识
```

### 8.9.3自动挂载

```
安装服务
yum install -y autofs 
启动服务
systemctl start autofs
systemctl enable autofs 
主配置文件
vi /etc/auto.master 
/opt/share   /etc/share.nfs
用户自定义的配置文件
vi /etc/share.nfs
key -rw,sync,sec=method server./path
挂在点  挂载选项  源位置
systemctl restart  autofs   重新启动服务 
```



## 8.10mount和umount

**挂载文件和挂载光盘文件**

将 /dev/是sda1 挂在 /mnt 之下。

```shell
#mount /dev/sda1 /mnt
```

将 /dev/hda1 用唯读模式挂在 /mnt 之下。

```shell
#mount -o ro /dev/sda1 /mnt
```

将 /tmp/image.iso 这个光碟的 image 档使用 loop 模式挂在 /mnt/cdrom之下。用这种方法可以将一般网络上可以找到的 Linux 光 碟 ISO 档在不烧录成光碟的情况下检视其内容。

```shell
#mount -o loop /tmp/image.iso /mnt/cdrom
```

umount卸载挂载的光盘文件  

```shell
umount /mnt
umount /mnt/cdrom 
```



 

# 9.软件安装

## 9.1 Yum安装软件

　　Yum需要一个仓库，也就是yum源。默认情况下，CentOS就有一个yum源。在/etc/yum.repos.d/目录下有一些默认的配置文件（可以将这些文件移到/opt下，或者直接在yum.repos.d/下重命名）。首先要找一个yum库（源），然后确保本地有一个客户端（yum这个命令就是客户端），由yum程序去连接服务器。



### Yum工作原理

**A.服务端**

​	将所有需要用到的rpm包存放于某个目录之下，该目录可以是远程的（采用ftp和http协议），也可以是本地的（采用file协议）。目录建立好了之后，使用createrpo命令来提取目录下所有rpm包的元数据和依赖关系，生成一些xml格式的文件，这些xml文件会存放在repodata目录下，至此，服务器端的repository就建立好了。注意repodata所在的位置，就是yum仓库的位置

**B. 客户端**

  客户端的配置非常简单，只需要使用yum及其子命令install、reinstall或remove即可。不过使用yum及其子命令之前，需要编辑配置文件，以告知yum命令仓库repository在什么地方。这个配置文件为：/etc/yum.conf。此外/etc/yum.repos.d/*.repo都被视为/etc/yum/conf的组成部分。

**C清除本地仓库的缓存创建缓存文件**

```shell
yum cleanall; yum makecache 
```

## 9.2 配置本地的Yum仓库

配置本地的yum文件：移除CentOS-Base.repo文件，并编辑CentOS-Media.repo文件。

```shell
从CentOS的官网下载CentOS的完整版iso文件，并上传到Linux文件系统中，例如/opt/tools/。
mkdir /mnt/vcdrom  //创建挂载的目录
mount -o loop -t iso9660 /opt/tools/CentOS-6.7-x86_64-bin-DVD1.iso /mnt/vcdrom
cd /etc/yum.repos.d/    ///切换到目录  
mv Centos-Base.repo Centos-Base.repo.back  // 重命名文件 
vi /etc/yum.repos.d/Centos-Media.repo     //编辑Centos-Media.repo文件
    [CentOS-$releasever - Media]  // Yum软件仓库唯一标识符，避免与其他仓库冲突。
    name=CentOS-Media // Yum软件仓库的名称描述，易于识别仓库用处。
    baseurl=file:///mnt/vcdrom/  
    enabled=1   #开启本地更新模式1为可用，0为禁用。
    gpgcheck=1  #设置此源是否校验文件；1为校验，0为不校验。
    :wq  保存退出或者使用esc shift+zz
yum clean all;yum makecache   //先清理缓存后生成缓存
```

## 9.3配置网络Yum

```shell
yum install -y wget  #先配置本地yum 安装wget才能使用yum install -y wget 
cd /etc/yum.repos.d/
mv * /opt
wget -O CentOS-Base.repo http://mirrors.163.com/.help/CentOS7-Base-163.repo 
yum clean all ; yum makecache
```

## 9.4脚本配置Yum

```shell
#!/bin/bash
#自动化配置yum的脚本
#关闭防火墙和selinux关闭 
#配置简单的ftp共享yum
#install yum stop firewalld 
mkdir -p /opt/local-yum
cd /etc/yum.repos.d
mv * /opt/
cat > /etc/yum.repos.d/local.repo << EOF
[local-yum]
name=local-yum
baseurl=file:///opt/local-yum
enabled=1
gpgcheck=0
EOF
mount /dev/cdrom /opt/local-yum    #需要挂载好光盘文件
yum clean all; yum makecache 
yum install -y vsftpd && 
echo "anon_root=/opt/local-yum" >> /etc/vsftpd/vsftpd.conf && 
systemctl start vsftpd && systemctl enable vsftpd 
#stop firewall 
systemctl stop firewalld &&systemctl disable firewalld 
sed -i 's/SELINUX=.*/SELINUX=disabled/g' /etc/selinux/config
setenforce 0 
echo "/dev/cdrom /opt/local-yum iso9660 defaults 0 0 " >> /etc/fstab 
mount -a 
echo "install success!!"
```



## 9.5搭建自己的Yum仓库

```shell
1.安装createrepo软件生成数据库的依赖文件 
yum install -y createrepo
mkdir /yum/repo
createrepo /yum /repo   
注意事项：在yum/repo文件夹下生成repodata文件夹,要是使用的是createrepo /yum ，将在yum文件夹下生成repodata 
```



## 9.6yum常用命令的使用

```shell
check      检查 RPM 数据库问题
check-update  检查是否有可用的软件包更新
clean      删除缓存数据
deplist     列出软件包的依赖关系
distribution-synchronization 已同步软件包到最新可用版本
downgrade    降级软件包
erase      从系统中移除一个或多个软件包
groups     显示或使用、组信息
help      显示用法提示
info      显示关于软件包或组的详细信息
install     向系统中安装一个或多个软件包
list      列出一个或一组软件包
makecache    创建元数据缓存
provides    查找提供指定内容的软件包
reinstall    覆盖安装软件包
repo-pkgs    将一个源当作一个软件包组，这样我们就可以一次性安装/移除全部软件包。
repolist    显示已配置的源
search     在软件包详细信息中搜索指定字符串
swap      Simple way to swap packages, instead of using shell
update     更新系统中的一个或多个软件包
upgrade     更新软件包同时考虑软件包取代关系
version     显示机器和/或可用的源版本。
```

```shell
lrzsz软件（为共享上传软件 最大为4G  ）
yum install -y lrzsz   使用rz -y进行传输 文件到linux操作系统上  
该软件超过4G就不让上传就建议使用ftp进行传输
```



## 9.7安装软件三种方式

### 9.7.1源码安装

make install，编译并安装（比如安装到/usr/bin目录下，然后可以直接使用。因为/usr/bin只有管理员才能向里面添加文件，所以通常要加sudo）

这个要看你的Makefile的,约定俗成的而已 一般"潜规则" make就是make all,编译用的,具体编译了那些文件要看你的Makefile make install就是把编译出来的二进制文件,库,配置文件等等放到相应目录下 

make clean清除编译结果 具体的东西都在Makefile里面,只不过大部分应用程序的Makefile都是由configure脚本自动生成的,所以Makefile内容都差不多

安装步骤：

源码的安装一般由有这三个步骤：配置(configure)、编译(make)、安装(make install)其中–prefix选项就是配置安装的路径，如果不配置该选项，安装后可执行文件默认放在/usr/local/bin，库文件默认放在/usr/local/lib，配置文件默认放在/usr/local/etc，其它的资源文件放在/usr/local/share。

为了便于集中管理某个软件的各种文件，可以配置–prefix，如：

```shell
./configure –prefix=/usr/local
可以把所有资源文件放在/usr/local的路径中，就不会分散了。
--prefix  --bindir // 命令的目录 
--etcdir 配置文件的目录 
--mandir 文档的路径  
--locale  语言的编码  
```

 

## 9.8RPM安装

安装 升级  删除 查询  验证 

rpm软件包的介绍：

```shell
软件名-主版本号-次版本号.软件运行的平台.rpm
httpd-2.4.6-45.el7.centosx86_64.rpm
```

软件版本的兼容问题：

```shell
高版本兼容低版本 根据架构选择    大版本之间差别很大  比如6和7之间区别就很大
选择适合当前版本的安装 找不到适合版本的就尝试源码安装 el6兼容el5
选择对应平台的软件包去安装  x86_x64 安装在64平台上  noarch  与硬件的架构无关32位不能安装64位数  建议不要版本的跨度太大  
man文档不是所有文件都有的    mandb数据库
```

RPM的安装软件不会修复依赖问题:

```shell
rpm安装：注意rpm会检查依赖和包的签名一个不过就不能安装软件
-i 安装软件
-v 显示详细的安装过程
-h 用#来显示安装进度

rpm -ivh httpd-2.4.6-45.el7.centosx86_64.rpm
rpm软件包的升级:升级后的文件会已软件包名.rpmsave
rpm -Uvh httpd-2.4.6-45.el7.centosx86_64.rpm
```

```shell
rpm 软件包查询：结合管道符号一起使用rpm -qa | grep 软件包名
rpm -qa | more // 查询系统中安装的所有软件包
rpm -qa | grep httpd  // 查询特定关键字的软件包是否安装
rpm -q  httpd-2.4.6-45.el7.centosx86_64.rpm //查看rpm是否已经安装
rpm -qi httpd-2.4.6-45.el7.centosx86_64.rpm //查看软件包的说明信息
rpm -ql httpd-2.4.6-45.el7.centosx86_64.rpm //查看软件包内所有包含文件名的
rpm -qf /etc/httpd //查询文件属于那个软件包
rpm -e httpd-2.4.6-45.el7.centosx86_64.rpm     //软件包的删除
rpm -V httpd-2.4.6-45.el7.centosx86_64.rpm //包的验证
@符号含义表示软件已经安装了
```

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps1-1618041347077.jpg) 

 

**使用md5sum检查rpm包的是否完整**

```shell
[root@localhost opt]# rpm --checksig zziplib-0.13.62-5.el7.x86_64.rpm 
zziplib-0.13.62-5.el7.x86_64.rpm: rsa sha1 (md5) pgp md5 OK
[root@localhost opt]#mud5sum  zziplib-0.13.62-5.el7.x86_64.rpm 
```

## 9.9rpm和apt 比较

```shell

yum (rpm) 和 apt-get的对应关系

说明   	  		     Redhat系	           Debian系
更新缓存				yum makecache	       apt-get update
更新包	      			yum update	           apt-get upgrade
检索包	      			yum search	           apt-cache search
检索包内文件			  yum provides	         apt-file search
安装指定的包			  yum install	         apt-get install
删除指定的包			  yum remove	         apt-get remove
显示指定包的信息	     yum info	            apt-cache show
显示包所在组的一览	    yum grouplist	           -
显示指定包所在组的信息	   yum groupinfo	          -
安装指定的包组	          yum groupinstall           -
删除指定的包组	          yum groupremove	         -
参考库的设定文件	     /etc/yum.repos.d/*	     /etc/apt/sources.list
安装完的包的列表	      rpm -qa	             dpkg-query -l
显示安装完的指定包的信息	rpm -qi	               apt-cache show
安装完的指定包内的文件列表	rpm -ql               dpkg-query -L
安装完的包的信赖包的列表	rpm -qR	               apt-cache depends
安装完的文件信赖的包	     rpm -qf	             dpkg -S
```



## 9.10解压和压缩



```shell
注意压缩之后的大小 
.tar
-c   创建tar
-Z   调用gzip 压缩
-j   调用bzip2压缩
-J   调用xz 压缩
-v   显示详细参数
-f   指定包名
-x   解压
-C   指定解压路径
-t   列出查看tar包中的内容
-r   往tar包里追加文件  
解包：tar xvf FileName.tar
打包：tar cvf FileName.tar DirName
（注：tar是打包，不是压缩！）
.gz

解压1：gunzip FileName.gz
解压2：gzip -d FileName.gz
压缩：gzip FileName 

.tar.gz
解压：tar -zxvf FileName.tar.gz
压缩：tar -zcvf FileName.tar.gz -C /mnt/


.bz2
解压1：bzip2 -d FileName.bz2
解压2：bunzip2 FileName.bz2
压缩： bzip2 -z FileName

.tar.bz2
解压：tar -jxvf FileName.tar.bz2 
压缩：tar -jcvf FileName.tar.bz2 DirName
.bz
解压1：bzip2 -d FileName.bz 
解压2：bunzip2 FileName.bz


.tar.bz 
解压：tar -jxvf FileName.tar.bz  
.Z
解压：uncompress FileName.Z
压缩：compress FileName
.tar.Z
解压：tar -Zxvf FileName.tar.Z
压缩：tar -Zcvf FileName.tar.Z /etc/

.tgz
解压：tar zxvf FileName.tgz
.tar.tgz
解压：tar -zxvf FileName.tar.tgz
压缩：tar -zcvf FileName.tar.tgz 123.sh
.zip
解压：unzip FileName.zip
压缩：zip FileName.zip DirName
```



# 10.服务进程的管理

## 10.1Linux中的进程

进程：已经运行的一个实例

PID：每个进程唯一值

PPID: 父进程号

任何一个进程都可以创建一个子进程   shell的扩展

注意杀死父进程子进程也就对应给杀死了  不然就出现了精灵进程

**查看进程命令：**

```shell
ps命令：查看当前进程状态
​	-aux列出所有进程    配置grep使用
​	-ef列出所有进程·
​	-u 查看用户的进程
​	-l 列出进程信息

top命令：动态显示进程
[root@localhost system]# top
top - 00:20:10 up 5 days,  2:24,  1 user,  load average: 0.05, 0.04, 0.00
Tasks: 179 total,   1 running, 124 sleeping,   0 stopped,   1 zombie
%Cpu(s):  1.2 us,  0.4 sy,  0.0 ni, 98.4 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem :  3874896 total,   586816 free,   827644 used,  2460436 buff/cache
KiB Swap:        0 total,        0 free,        0 used.  2745872 avail Mem 

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND                                                                        
 1670 root      20   0   21736   3704   3376 S   0.3  0.1   0:12.88 watchdog.sh                                                                    
 3513 root      20   0  511428  15416   4508 S   0.3  0.4  26:22.10 barad_agent                                                                    
 8389 root      20   0   42180   3792   3204 R   0.3  0.1   0:00.01 top                                                                            
26919 root      20   0  905684  41264  12740 S   0.3  1.1   0:03.75 BT-Task                                                                        
    1 root      20   0   79088   9000   6484 S   0.0  0.2   0:04.66 systemd                                                                        
    2 root      20   0       0      0      0 S   0.0  0.0   0:00.03 kthreadd    
```

**运行状态解释：**

```shell
[root@localhost system]# ps -aux 
USER     PID %CPU %MEM   VSZ  RSS TTY    STAT START  TIME COMMAND
root      1  0.1  0.3  50776  7208 ?     Ss  16:08  0:01 /usr/lib/systemd/systemd --switched
root      2  0.0  0.0    0   0 ?     S   16:08  0:00 [kthreadd]
```

 进程信息：

```shell
USER: 行程拥有者
PID: pid
%CPU: 占用的 CPU 使用率
%MEM: 占用内存使用率
VSZ: 占用的虚拟内存大小
RSS 驻留中页的数量；
TTY: 终端的次要装置号码 (minor device number of tty)
STAT: 该行程的状态:
D: 不可中断的静止 R: 正在执行中 S: 静止状态T: 暂停执行 Z: 不存在但暂时无法消除
W: 没有足够的内存分页可分配 <: 高优先序的行程 N: 低优先序的行程
L: 有内存分页分配并锁在内存内
START: 行程开始时间
TIME: 执行的时间
```

**运行的状态：**

```shell
	运行中的：
​		R正在运行或者等待运行
​	休眠：
​		S 正在休眠但是可以被唤醒
​		D 正在休眠 不可唤醒 不可中断，中断会出错
​		K 正在休眠 不可唤醒 可以中断，但是不会出错
​	已经停止：
​		T进程被停止，但是可以通过其他进程来恢复
​		T 正在被调试的进程
​	僵停：
​		Z子进程在退出时向父进程发出信号 除PID 外所有资源全部释放
​		X父进程获取子进程的结构，子进程可以完全释放
```

```shell
	Linux的优先级：
			<高优先级
			n优先级
			s包含子进程
			+位于后台进程组
	nice命令进行优先级的切换
```



## 10.2 free查看内存使用

```shell
查看内存使用 静态数值  看到的就是某个时间的显示的状态
[root@xiaozhe0514 ~]# free -m 
              total        used        free      shared  buff/cache   available
Mem:           1837         824          72           1         940         819
Swap:             0           0           0
[root@xiaozhe0514 ~]# 

第一行 Mem 行:
total 内存总数: 1002M
used 已经使用的内存数: 769M
free 空闲的内存数: 232M
shared 当前已经废弃不用，总是 0
buffers Buffer 缓存内存数: 
cached Page 缓存内存数:421M
关系：total(1002M) = used(769M) + free(232M)
第二行(-/+ buffers/cache):
(-buffers/cache) used 内存数：286M (指的第一部分 Mem 行中的 used - buffers - cached)
(+buffers/cache) free 内存数: 715M (指的第一部分 Mem 行中的 free + buffers + cached)可见-buffers/cache 反映的是被程序实实在在吃掉的内存，而+buffers/cache 反映的是可以用的内存总数。(从这里我们可以看出，实际上 ：可用内存＝第一部分 Mem 行中的 free + buffers + cached,并不是只有 free 部分)
第三行  是指交换分区
```

 

## 10.3服务的分类

```shell
Service ：扩展名为.service，代表系统服务
Socket：扩展名为.socket，表述进程间通信(IPC)
Path：扩展名为.path，通常用于假脱机的目录服务，如打印机系统
graphical.target 带图形及字符终端的多用户模式
multi-user.target 仅带字符终端的多用户模式
rescue.target 仅初始化基本系统，需要root账户登录
emergency.target 加载内存文件系统，只读挂载根文件系统，
# systemctl start httpd.service  启动
# systemctl restart httpd.service   重启
# systemctl stop httpd.service  停止
# systemctl reload httpd.service  重新载入配置文件
# systemctl status httpd.service   服务运行状态
# systemctl list-unit-files   //列出所有可用单元
# systemctl list-units   //列出所有运行中单元 
# systemctl is-enabled crond.service   //检查某个单元是否启用 
# systemctl is-active mysql.service  查看是不是开机启动的状态
# systemctl enable mysql.service  开机启动
# systemctl disable mysql.service  开机不启动
# systemctl mask ntpdate.service屏蔽服务 
# systemctl unmask ntpdate.service 显示服务
# systemctl kill  crond   //使用systemctl命令杀死服务 
# systemctl list-unit-files –type=mount   //列出所有系统挂载点
# systemctl list-unit-files –type=socket  //列出所有可用系统套接口 
# systemctl show  mysql   //检查某个服务的所有配置细节 
# systemctl list-dependencies httpd.service  //获取某个服务的依赖性列表
# systemctl rescue   /启动救援模式 
# systemctl emergency   //进入紧急模式 
# systemctl get-default   //列出当前使用的运行等级
# systemctl isolate graphical.target  //启动运行等级5，即图形模式
# systemctl isolate runlevel3.target
# systemctl isolate multiuser.target  //启动运行等级3，即多用户模式
# systemctl set-default runlevel3.target  //设置多用户模式 	
# systemctl set-default runlevel5.target //设置多用户模式或图形模式为默认运行等级
# startx  //进入图形界面：
# systemctl set-defaults graphical.target  // 直接启动到图形界面
# systemctl get-defaults   //查看默认的启动方式
# systemctl halt 停止
# systemctl suspend 挂起
# systemctl hibernate 休眠系统
# systemctl hybrid-sleep使系统进入混合睡眠
```

 

## 10.4系统的运行等级

```shell
运行级别依赖于：/etc/inittab 进程   早期的centos6 或者是红帽6 都是使用的这个进程
Runlevel 0 : 关闭系统
Runlevel 1 : 救援，维护模式
Runlevel 3 : 多用户，无图形系统
Runlevel 4 : 多用户，无图形系统
Runlevel 5 : 多用户，图形化系统
Runlevel 6 : 关闭并重启机器
```

 

 

## 10.5日志分析重点掌握

```shell
systemctl -journaled
日志文件是记录 Linux 中系统消息的文件
不同的日志文件记载不同类型的信息，包括内核、服务以及在系统中运行的应用程序的信息
日志文件有助于诊断和解决系统中的问题
systemd-journald
从内核收集消息,包括启动进程、标准输出及错误、进程运行启动等记录.重启不保存
rsyslog
根据类别(facility)及优先级别(severity)筛选系统记录,将信息写入 /var/log 下对应的日志文件，统一管理日志文件
```

## 10.6 会话 作业

```shell
进程  线程  程序之间的区别？     建议去看计算机操作系统
	进程：一个运行的程序
	交互进程：前台运行，或者后台运行
    守护进程：
	批处理进程： 是一个进程序列 和终端没有练习
```




## 	10.6.1 作业

```shell
作业包含多个进程   批量成组的进行通信  
作业控制：控制正在运行的进程行为
& ：在命令后边使用，该进程进入后台
```

## 	10.6.2jobs 

```shell
查看正在后台运行的作业
-l 除了作业号外，还显示PID
-r列出仅在后台运行的作业
-s 列出在后台运行的作业
```

```shell
中断ctral+c  ctral+Z 挂起
根据特定进程查询命令
  pgrep "init"
  pgrep -l "init"
  pgrep -l -U xiaowang -t tty1 
以树状形式构造进程的关系：
 pstree -aup 
```

**进程的调度：**

```shell
 at   运行一个计划任务
 jobs   jobs -l //查看进程
 fg 处于后台的进程恢复到前台来工作 需要制定任务序号
 bg 
 
```

 

## 10.6.3kill 

```shell
杀死进程：
kill  kill  -9   //杀死指定pid的进程 
killall   // 用于终止制定名称的所有进程
Killuser   //杀死正在登录的进程
```

 

## 10.6.4crontab

```shell
周期性计划和任务：
cat /etc/crontab 
crontab -e [-u 用户名]   //编辑计划和任务
crontab -l [-u 用户名]   //查看计划和人物
crontab -r [-u 用户名]   // 删除计划和任务
/etc/crontab 配置文件
/etc/cron.d   配置文件
/etc/cron.hourly 
/etc/cron.daily   
/etc/cron.weekly  
/etc/cron.monthly 
```

小案例：

```shell
crontab -e 
*/30 * * * * /usr/bin/ntpdate ntp.aliyun.com &> /dev/null
最后直接保存退出   使用国内的时间同步服务器最好使用阿里的
[root@server01 cron.daily]# cat /etc/crontab 
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin
MAILTO=root

# For details see man 4 crontabs

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed

[root@server01 cron.daily]# 
在实际的生产环境中关于东八区和东十二区之间时差   时间戳的形式   * /10  每10分钟执行一次  

关于linux的时间同步问题：
主板时间  时间同步服务器的时间   直接把时间同步服务器的时间写入到主板上    金融行业对时间的同步要求的很严格
```



## 10.6.5 at

```shell
at有白名单和黑名单
语法：at [option] TIME
常用选项：
-V  显示版本信息
-t time 时间格式   使用时间戳的形式
-l 列出指定队列中等待运行的作业  相当于atq
-d  删除指定的作业    等价于atm
-c  查看具体作业任务 
-f  指定文件中读取任务 
-m  当任务完成之后  将给用户发送有有机胺 
作业执行命令的结果中的标准输出和错误以邮件通知给相关用户
[root@server01 cron.daily]# at -h 
Usage: at [-V] [-q x] [-f file] [-mMlbv] timespec ...
       at [-V] [-q x] [-f file] [-mMlbv] -t time
       at -c job ...
       atq [-V] [-q x]
       at [ -rd ] job ...
       atrm [-V] job ...
       batch
[root@server01 cron.daily]# 
```

```shell
有时候at发出的邮件root不会收到  可能出现在垃圾邮件中 

systemctl status atd  进程状态
[root@localhost ~]# systemctl status atd 
● atd.service - Job spooling tools
   Loaded: loaded (/usr/lib/systemd/system/atd.service; enabled; vendor preset: enabled)
   Active: active (running) since Wed 2022-07-06 10:35:08 CST; 13h ago
 Main PID: 1089 (atd)
    Tasks: 1
   CGroup: /system.slice/atd.service
           └─1089 /usr/sbin/atd -f

Jul 06 10:35:08 localhost.localdomain systemd[1]: Started Job spooling tools.
[root@localhost ~]# 

at 10:45  这是交互的命令 下次重启后at命令还执行不执行 
wall  发送广播任务执行后的操作   
```



# 11网络管理

Centos7采用配置文件的关联：          服务器领域很少见              桌面领域多见 比如Ubuntu

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps1-1618041399423.jpg) 

一个网卡可以与多个文件建立关系，同一时刻只能有一张网卡建立关系  生效的只能是一个配置文件

```shell
1. 接口状态
2. 硬件mac地址
3. IP v4地址和前缀
4. 广播地址，作用域和设备名称
5. IP v6地址和信息
```



## 11.1网卡配置命令：

```shell
nmcli connection modify eno16777736 ipv4.addresses 192.168.168.2/24   添加ipv4地址
nmcli connection modify eno16777736 ipv4.gateway 192.168.168.1   添加网关
nmcli connection modify eno16777736 ipv4.method manual   设置手动方式上网
nmcli connection modify eno16777736 connection.autoconnect yes    自动激活状态
nmcli connection up eno16777736  查看接口状态
nmcli connection show eth0       // 显示具体的网络接口信息
nmcli device status             // 显示所有设配状态
nmcli connection show --active  //显示所有活动连接
nmcli connection delete eth0    //删除一个网卡连接
nmcli connection add type ethernet con-name eth0 ifname eno33554992       //添加一个网卡连接
nmcli connection add type ethernet con-name eth0         //添加网卡
nmcli connection down eth0	  //网络接口的停用
nmcli connection up  eth0       //网络接口的启用
1.关闭会话的自动连接（autoconnect）。
[root@rhel7 ~]# nmcli con mod “static” connection.autoconnect no
2.指定一个DNS服务器地址
[root@rhel7 ~]# nmcli con mod “static” ipv4.dns 8.8.8.8
3.有一些配置参数，是可以添加和删除的，比如使用+ 或 - 号在参数前面。比如添加第二个DNS服务器地址
[root@rhel7 ~]# nmcli con mod “static” +ipv4.dns 8.8.4.4
4.更换静态IP地址和默认网关。
[root@rhel7 ~]# nmcli con mod “static” ipv4.addresses “192.168.0.120/24 192.168.0.1”
5.添加第二个ip
[root@rhel7 ~]# nmcli con mod “static” +ipv4.addresses 192.168.0.130/24
```

 

### 11.2.1桥接模式

```shell
使用nmcli配置网卡桥接
1.创建桥接接口
nmcli con add type bridge con-name br1 ifname br1
2.指定成员接口
nmcli con add type bridge-slave con-name br1-port1 ifname eth1 
master br1
3.查看桥接信息
brctl show
4.NetworkManager只能为网桥连接以太网接口  
```

 

**桥接**

```shell
yum install -y bridge-utils    centos8 已经没有了
brctl show
Teaming将多块网卡绑定同一IP地址对外提供服务，以实现高可用或者负载均衡功能
Centos7使用内核驱动处理网络数据包并使用teamd进行逻辑与接口进程控制
teamd轮转(runner)方式：
1. broadcast 广播
2. roundrobin 轮询
3. activebackup 主备
4. loadbalance 负载均衡
5. lacp 负载均衡
使用NetworkManager控制team接口时，特别是在故障时，注意以下几点：
启动team接口不会自动启动成员接口
启动成员接口时将启动team接口
停用team接口时成员接口也被停用
无成员的team接口可配置静态ip连接
启用DHCP连接时team接口将等待成员接口
team接口启用DHCP连接时，当成员接口有承载网络接口时，将等待成员接口配置完
team接口启用DHCP连接时，当成员接口没有承载网络接口时，将持续等待
```

使用命令创建网桥

```shell
brctl show
brctl addbr br0 
brctl addif br0 ens33
brctl addif br0 ens24
ifconfig ens33 0.0.0.0
ifconfig ens34 0.0.0.0
```



###  11.2.2 ip a

```shell
端口号表示
[2002:310:0:1::45dd]:80
始终对十六进制数使用小写字母a到f
查看IPv6网络信息
l查看IPv6地址
ip addr show [interface]
l查看IPv6路由信息
ip -6 route show
验证连接
ping6 address   //ping ipv6地址
```

# 12.防火墙

定义：是一种防护内网不被外部网络入侵的设备或软件。

## 12.1firewalld-cmd

```shell
#firewall-cmd --state      查看firewall的状态
查看防火墙规则（只显示/etc/firewalld/zones/public.xml中防火墙策略）
#firewall-cmd --list-all 
查看所有的防火墙策略（即显示/etc/firewalld/zones/下的所有策略）
#firewall-cmd --list-all-zones 
firewall-cmd --version   查看版本：
firewall-cmd --help    查看帮助
firewall-cmd --zone=public --list-ports 查看所有打开的端口
firewall-cmd --get-active-zones    查看区域信息
firewall-cmd --get-zone-of-interface=eth0   查看指定接口所属区域
firewall-cmd --panic-on   拒绝所有包
firewall-cmd --panic-off   取消拒绝状态
firewall-cmd --query-panic   查看是否拒绝
firewall-cmd --zone=public --add-port=80/tcp --permanent #（--permanent永久生效，没有此参数重启后失效）   添加端口
firewall-cmd --reload   重新载入
firewall-cmd --zone=public --query-port=80/tcp   查看
firewall-cmd --zone=public --remove-port=80/tcp --permanent     删除

允许apache服务通过
firewall-cmd --permanent --add-service=https
firewall-cmd --relo
添加vnc端口
firewall-cmd --permanent --add-service vnc-server 
systemctl restart firewalld.service 
firewall-cmd --permanent --zone=public --add-port=5903/tcp firewall-cmd --reload
```

 

##  12.2iptables

iptables的结构：

![img](Centos7-1810%E7%AC%94%E8%AE%B0.assets/wps2-1618041399424.jpg) 



```shell
iptables的启动关闭和保存：
service iptables stop start | status reload |restart
设置开机自动启动：
chkconfig iptables off | on
永久保存规则：
vi /etc/sysconfig/iptables  添加规则就行
```

```shell
iptables的常用的命令的选项：
-L  查看  
-A 追加放到最后一条  
-I 插入一条  
-D 删除  
-F 清空flush
-P 设置默认的策略
```

```shell
处理动作:
-j ACCERT  允许
-j DROP  丢弃
-j REJECT 决绝
-j LOG 写日志  /var/log/message 
iptables 的基本语法：
	iptables [-t 表名] 命令选项  [链名] [规则号码] [条件匹配] [-j 目标动作]
			小写    大写   大写       小写    大写
```

```shell
表名和链名  用于指定iptables 命令需要操作的表和链
命令选项：指定iptbales的管理方式  
规则编号：指定规则编号
条件匹配：符合什么样条件的数据包进行匹配 
目标动作：指定数据包的处理方式
```

```shell
常用的命令：
	iptables -t filter -A  OUTPUT -j DROP 添加规则，丢弃所有出去的数据包
	iptables -t filter -I INPUT 3 -j REJECT 
	iptables -t filter -L –line-numbers //查看规则编号
	iptables -t filter -R INPUT 1 -j ACCEPT  //覆盖已有规则
	iptables -t filter -D INPUT 3  // 删除INPUT 链的第三台条规则
	iptables -t filter -F //清空filter表中的所有规则
	iptables -A  INPUT -j DROP  增加规则  先写日志然后在增加规则s
	iptables -I INPUT  2 -j DROP  
	iptables -t filter -P INPUT DROP  //设置链上的默认规则 
	iptables -D INPUT 
	iptables -t filter -L
	iptables -t nat -L
	iptables -t raw -L
    iptables -L 查看规则
    iptables -V  查看iptables版本
    iptables -nL   查看nat表
    iptables -F   清空规则 
    iptables -X 清空用户自定义的链
    iptables -Z  清空链的计数器
    lsmod | egrep "nat|filter "  查看表的模块
    iptables -D INPUT 3 
    iptables -L -n --line-numbers    使用-D删除  
    注意如果不指定表名  默认操作的是filter表
    注意端口号：
        1-255 一般知名端口号  
        256-1023 特定服务的端口号
        1024-5000 客户端的端口号 一般随机产生的
        大于5000 为互联网上的其他服务预
```

# 14.安全问题

 linux的服务器的安装：
**1.删除特殊的账户和安全组** 
可删除的用户，如 adm,lp,sync,shutdown,halt,news,uucp,operator,games,gopher 等。
可删除的组，如 adm,lp,news,uucp,games,dip,pppusers,popusers,slipusers 等。
**2.关闭系统不需要的服务  服务越多越不安全**  
可以选择关闭的服务  
anacron、auditd、autofs、avahi-daemon、avahi-dnsconfd、bluetooth、cpuspeed、firstboot、
gpm、haldaemon、hidd、ip6tables、ipsec、isdn、lpd、mcstrans、messagebus、netfs、nfs、nfslock、
nscd、pcscd portmap、readahead_early、restorecond、rpcgssd、rpcidmapd、rstatd、sendmail、
setroubleshoot、yppasswdd ypserv

**3.密码的安全的策略**
linux中两种认证的方式  密码认证和密钥的认证   大写  小写   字母 数字  下划线 
使用公钥和私钥进行登录
修改.ssh 使用的权限 chmod 700 /root/.ssh 
在 Linux 服务器上的操作步骤如下：
[root@localhost ~]#vi /etc/ssh/sshd_config
修改如下几个配置：
Protocol 2 #仅允许使用 SSH2
PubkeyAuthentication yes #启用 PublicKey 认证
AuthorizedKeysFile .ssh/authorized_keys2 #PublicKey 文件路径
PasswordAuthentication no #不使用口令认证
最后重启 sshd 服务，执行如下命令：
[root@localhost ~]#/etc/rc.d/init.d/sshd restart
sshd 服务启动完毕，就可以利用 SecureCRT 通过 PublicKey 认证远程登录 Linux 系统了

**4.合理使用su  sudo命令 sudo 默认的时间5分钟 5分钟后就得重新输入密码**

**5.删除系统登录欢迎信息**  

需要修改或删除的文件有 4 个，分别是/etc/issue、/etc/issue.net、/etc/redhat-release
和/etc/motd

**6.禁用ctrl+alt+delete 进行重启**  
Centos5.x 以下的系统，只需修改/etc/inittab 文件即可，操作如下：
[root@localhost ~]#vi /etc/inittab 
找到此行：
ca::ctrlaltdel:/sbin/shutdown -t3 -r now
在之前加上“#”，然后执行：
[root@localhost ~]#telinit q
在 Centos6.x 以上版本中，需要修改/etc/init/control-alt-delete.conf 文件，找到如下内容：
exec /sbin/shutdown -r now "Control-Alt-Delete pressed"
在之前加上“#”，注释掉即可。

**7.取消使用telnet进行登录使用ssh进行登录** 

8.合理使用shell历史命令记录功能
默认保存在.bash_history 文件中默认保存了1000条信息    可以通过此文件进行排查是不是被入侵了


9.启动tcp——wrapper防火墙
使用方法：Tcp_Wrappers 的使用很简单，仅仅只有两个配置文件：/etc/hosts.allow 和/etc/hosts.deny。
软件是不是可以使用该防火墙   查看方法; 取决于该服务是不是使用libwrapped 库文件


10.文件系统的安全  锁定系统重要的文件
方法：似乎用隐藏权限 

```shell
文件权限检查和修改
    查找文件
    find / -type f -perm -2 -o -perm -20 | xargs ls -al 
    查找没有属主的文件
    find / -nouser -o -nogroup 
./tmp  /var/tmp /dev/shm 安全设定
```



# 16.升级内核：

注意： 在3.0以上的内核引入了签名机制，需要导入签名的key,参考步骤如下：

```shell
rpm -Uvh https://elrepo.org/elrepo-release-7.0-3.el7.elrepo.noarch.rpm
yum --enablerepo=elrepo-kernel install -y kernel-lt
cat /boot/grub/grub.conf
grub2-set-default 'CentOS Linux (5.4.152-1.el7.elrepo.x86_64) 7 (Core)'
[root@localhost ~]# yum provides brctl 
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
elrepo: mirrors.tuna.tsinghua.edu.cn
elrepo/filelists_db        |  37 kB  00:00:00     
bridge-utils-1.5-9.el7.x86_64 : Utilities for configuring the linux ethernet bridge
Repo        : base
Matched from:
Filename    : /usr/sbin/brctl
[root@localhost ~]# yum install bridge-utils  
```

## 关于服务器的密码的爆破：

```shell
chfn命令
上边脚本都是得需要使用反复进行编写的
使用lastb输出登录错误的信息  猜测账号失败
编写一个脚本文件爆破root密码   
python脚本进行密码的爆破和破解 
```

```shell
收集主机信息
echo "`ifconfig eth0 | awk 'NR==2{print $2}'`"  >> list
找出主机名     hostnamectl set-hostname server-test
列出核心信息    uname -a 
列出内存使用情况   free -h 
列出磁盘种类    df -Th 
列出主机系统的平均负载    top 
列出系统的中隐藏文件  特殊权限的文件    ls -alh 
列出磁盘用量   df -Th    du -sh * 
```

## 显示外网的链接数目：

```shell
netstat -pantu | egrep -v '0.0.0.0|:::' | awk '{print $5} ' | egrep -v 'and | Address'
```



## 日志文件

```shell
3.删除日志记录
#!/bin/bash
echo >/var/log/secure
echo > /var/log/messages
echo > /var/log/httpd/access_log
echo > /var/log/httpd/error_log
echo > /var/log/xferlog
echo >/var/log/secure
echo > /var/log/auth.log
echo > /var/log/user.log
echo > /var/log/wtmp
echo > /var/log/lastlog
echo > /var/log/btmp
echo > /var/run/utmp
history 

```
