# **一、虚拟化分类**

虚拟化的安装

https://blog.51cto.com/yangshufan/2130043

参考文档：

https://www.cnblogs.com/kevingrace/p/8377645.html

https://cloud.tencent.com/developer/article/1431274

https://www.cnblogs.com/kevingrace/p/5570504.html



1、虚拟化，是指通过虚拟化技术将一台计算机虚拟为多台逻辑计算机。在一台计算机上同时运行多个逻辑计算机，每个逻辑计算机可运行不同的操作系统，并且应用程序都   可以在相互独立的空间内运行而互相不影响，从而显著提高计算机的工作效率。虚拟化使用软件的方法重新定义划分 IT 资源，可以实现 IT 资源的动态分配、灵活调度、跨域共享，提高 IT 资源利用率，使 IT 资源能够真正成为社会基础设施，服务于各行各业中灵活多变的应用需求。

 

2、虚拟化层次种类：

 （1） 完全虚拟化 --- 最流行的虚拟化方法使用名为 hypervisor 的一种软件，在虚拟服务器和底层硬件之间建立一个抽象层。 VMware 和微软的VirtualPC 是代表该方法的两个商用产品，而基于核心的虚拟机 (KVM) 是面向 Linux 系统的开源产品hypervisor 可以捕获 CPU 指令，为指令访问硬件控制器和外设充当中介。因而，完全虚拟化技术几乎能让任何一款操作系统不用改动就能安装到虚拟服务器上，而它们不知道自己运行在虚拟化环境下。主要缺点是， hypervisor 给处理器带来开销

（2）准虚拟化 --- 完全虚拟化是处理器密集型技术，因为它要求 hypervisor管理各个虚拟服务器，并让它们彼此独立。减轻这种负担的一种方法就是，改动客户端操作系统，让它以为自己运行在虚拟环境下，能够与hypervisor 协同工作。这种方法就叫准虚拟化 (para-virtualization)Xen 是开源准虚拟化技术的一个例子。操作系统作为虚拟服务器在 Xen hypervisor 上运行之前，它必须在核心层面进行某些改变。因此， Xen 适用于 BSD 、 Linux 、 Solaris 及其他开源操作系统，但不适合对像Windows 这些专有的操作系统进行虚拟化处理，因为它们无法改动。准虚拟化技术的优点是性能高。经过准虚拟化处理的服务器可与hypervisor 协同工作，其响应能力几乎不亚于未经过虚拟化处理的服务器。准虚拟化与完全虚拟化相比优点明显，以至于微软和 VMware 都在开发这项技术，以完善各自的产品。

（3）系统虚拟化 --- 就操作系统层的虚拟化而言，没有独立的hypervisor 层。相反，主机操作系统本身就负责在多个虚拟服务器之间分配硬件资源，并且让这些服务器彼此独立。一个明显的区别是，如果使用操作系统层虚拟化，所有虚拟服务器必须运行同一操作系统 ( 不过每个实例有各自的应用程序和用户。

账户 ) 。虽然操作系统层虚拟化的灵活性比较差，但本机速度性能比较高。此外，由于架构在所有虚拟服务器上使用单一、标准的操作系统，管理起来比异构环境要容易。

（4）桌面虚拟化 --- 服务器虚拟化主要针对服务器而言，而虚拟化最接近用户的还是要算的上桌面虚拟化了，桌面虚拟化主要功能是将分散的桌面环境集中保存并管理起来，包括桌面环境的集中下发，集中更新，集中管理。桌面虚拟化使得桌面管理变得简单，不用每台终端单独进行维护，每台终端进行更新。终端数据可以集中存储在中心机房里，安全性相对传统桌面应用要高很多。桌面虚拟化可以使得一个人拥有多个桌面环境，也可以把一个桌面环境供多人使用。

 



 3、虚拟化架构分类
     （1）1型虚拟化

​       Hypervisor 直接安装在物理机上，多个虚拟机在 Hypervisor 上运行。Hypervisor 实现方式一般是一个特殊定制的 Linux 系统。Xen 和 VMWare 的 ESXi都属于这个类型。

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps1.jpg) 

 

​     （2）2型虚拟化

​      物理机上首先安装常规的操作系统，比如 Redhat、Ubuntu 和 Windows。Hypervisor 作为 OS 上的一个程序模块运行，并对管理虚拟机进行管理。KVM、VirtualBox 和 VMWare Workstation 都属于这个类型。

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps2.jpg) 

# 二、虚拟化 ---KVM

​    1、虚拟化kvm发展：

　　  2006 年 10 月由以色列的 Qumranet 组织开发的一种新的“虚拟机”方案，并将其贡献给开源世界

 　　 2007 年 2 月于 Linux Kernel-2.6.20 中第一次包含了 KVM

　　  2008 年 9 月，红帽收购了 Qumranet ，由此入手了 KVM 的虚拟化技术。在之前红帽决是将Xen 加入到自己的默认特性当中——那是 2006 年，因为当时Xen技术脱离了内核的维护方式，也许是因为采用 Xen 的 RHEL 在企业级虚拟化方面没有赢得太多的市场，也许是因为思杰跟微软走的太近了，种种原因，导致其萌生了放弃 Xen。而且在正式采用 KVM 一年后，就宣布在新的产品线中彻底放弃 Xen ，集中资源和精力进行 KVM 的工作。

　　  2009 年 9 月，红帽发布其企业级 Linux 的 5.4 版本（ RHEL5.4 ），在原先的 Xen 虚拟化机制之上，将 KVM 添加了进来
　 　  2010 年 11 月，红帽发布其企业级 Linux 的 6.0 版本（ RHEL6.0 ），这个版本将默认安装的 Xen 虚拟化机制彻底去除，仅提供 KVM 虚拟化机制

​    2011 年初，红帽的老搭档 IBM 找上红帽，表示 KVM 这个东西值得加大力度去做。于是到了 5 月， IBM 和红帽，联合惠普和英特尔一起，成立了开放虚拟化联盟（ Open Virtualization Alliance ），一起声明要提升 KVM 的形象，加速 KVM 投入市场的速度，由此避免 VMware 一家独大的情况出现。联盟成立之时，红帽的发言人表示， 大家都希望除 “ VMware 之外还有一种开源选择。未来的云基础设施一定会基于开源

　　  自 Linux 2.6.20 之后逐步取代 Xen 被集成在Linux 的各个主要发行版本中，使用 Linux 自身的调度器进行管理。

　　 2 、KVM --- 全称是基于内核的虚拟机（Kernel-based Virtual Machine）  是一个开源软件，基于内核的虚拟化技术，实际是嵌入系统的一个虚拟化模块，通过优化内核来使用虚拟技术，该内核模块使得 Linux 变成了一个Hypervisor，虚拟机使用 Linux 自身的调度器进行管理。 KVM 是基于虚拟化扩展（Intel VT 或者 AMD-V）的 X86 硬件的开源的 Linux 原生的全虚拟化解决方案。KVM 中，虚拟机被实现为常规的 Linux 进程，由标准 Linux 调度程序进行调度；虚机的每个虚拟 CPU 被实现为一个常规的 Linux 进程。这使得 KMV 能够使用 Linux 内核的已有功能。但是，KVM 本身不执行任何硬件模拟，需要客户空间程序通过 /dev/kvm 接口设置一个客户机虚拟服务器的地址空间，向它提供模拟的 I/O，并将它的视频显示映射回宿主的显示屏。目前这个应用程序是 QEMU。

　 　3、Linux 上的用户空间、内核空间、虚机：

　　  Guest：客户机系统，包括CPU（vCPU）、内存、驱动（Console、网卡、I/O 设备驱动等），被 KVM 置于一种受限制的 CPU 模式下运行。

　  KVM：运行在内核空间，提供CPU 和内存的虚级化，以及客户机的 I/O 拦截。Guest 的 I/O 被 KVM 拦截后，交给 QEMU 处理。

　　  QEMU：修改过的为 KVM 虚机使用的 QEMU 代码，运行在用户空间，提供硬件 I/O 虚拟化，通过IOCTL /dev/kvm 设备和 KVM 交互。
      

　　 4、KVM：

​       kvm.ko（内核模块），只用于管理虚拟 CPU 和内存。IO 的虚拟化，就交给 Linux 内核和qemu来实现。
　　    Libvirt：是 KVM 的管理工具。Libvirt 除了能管理 KVM 这种 Hypervisor，还能管理 Xen，VirtualBox 等。OpenStack 底层也使用 Libvirt。
　　    Libvirt 包含 3 个东西：后台 daemon 程序 libvirtd、API 库和命令行工具 virsh

​       （1）libvirtd是服务程序，接收和处理 API 请求；
​       （2）API 库使得其他人可以开发基于 Libvirt 的高级工具，比如virt-manager，这是个图形化的 KVM 管理工具，后面我们也会介绍；
​       （3）virsh 是我们经常要用的 KVM 命令行工具，后面会有使用的示例。作为 KVM 和 OpenStack 的实施人员，virsh 和 virt-manager 是一定要会用的。

 

# **三、虚拟化VT开启确认**

KVM 本身也有一些弱点，那就是相比裸金属虚拟化架构的 Xen 、 VMware ESX 和 HyperV ， KVM 是运行在 Linux 内核之上的寄居式虚拟化架构，会消耗比较多的计算资源；不过针对这一点， Intel 、 AMD 已经在处理器设计上有专门的VT-x 和 AMD-V 扩展，这种特性在每次硬件更新的时候也会更新，往往每次更新后都对虚拟化性能和速度上有明显的提升，所以长远来看，也不是什么大问题。
KVM 的虚拟化需要硬件支持（需要处理器支持虚拟化：如 Intel 厂商的 Intel-VT （vmx ）技术&&AMD 厂商的 AMD-V （ svm ）技术。是基于硬件的完全虚拟化。而 Xen 早期则是基于软件模拟的半虚拟化（ Para-Virtualization ），新版本则是基于硬件支持的完全虚拟化。但 Xen 本身有自己的进程调度器，存储管理模块等，所以代码较为庞大。

你当前的 CPU 是否支持 VT 技术？当不确定你当前 CPU 是否支持 VT 技术时
\1. 可以在 windows 下使用 cpu-z 软件来进行测试
\2. 可以在 Linux 下查看 CPU 的相信信息来确定

CPU 虚拟化给我们带来了哪些好处？


CPU 的虚拟化技术可以将单 CPU 模拟多 CPU 并行，允许一个平台同时运行多个操作系统，并且应用程序都可以在相互独立的空间内运行而互不影响，从而显著提高计算机的工作效率。

 虚拟化技术与多任务超线程的技术的区别？（操作系统多对一）


虚拟化技术与多任务以及超线程技术是完全不同的。多任务是指在一个操作系统中多个程序同时并行运行，而在虚拟化技术中，则可以同时运行多个操作系统，而且每一个操作系统中都有多个程序运行，彼此独立。每一个操作系统都运行在一个虚拟的 CPU 或者是虚拟主机上；而超线程技术只是单 CPU 模拟双 CPU 来平衡程序运行性能，这两个模拟出来的 CPU 是不能分离的，只能协同工作

实验一：将命令行界面改为图形化界面

之前我们在创建虚拟机的时候，可以根据需求选择图形化界面（带gui的图形工具）或者直接安装命令行界面。

但是如果在选择安装命令行界面后又想改为图形化呢。以下步骤：

 

1. 确定处理器有 VT

支持vmx或者svm建立在图形化界面的前提下，按照上面的设置为图形化界面后，

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps3.jpg) 

再勾选处理器的虚拟化引擎，如果出现不支持虚拟化性能计数器，可以选择不勾选。

命令行： grep vmx /proc/cpuinfo (INTEL 芯片 )

```
grep svm /proc/cpuinfo (AMD 芯片 )
cat /proc/cpuinfo | grep -e vmx -e nx -e svm
```

执行以上命令：

 

```
[root@localhost haha]# egrep '(vmx|svm)' /proc/cpuinfo | wc -l
```

1#处理器个数大于0就是支持虚拟化，就可以放心做kvm虚拟化安装了

 

 不知道芯片的生产厂商则输入：egrep '(vmx|svm)' /proc/cpuinfo
如果 flags: 里有 vmx 或者 svm 就说明支持 VT ；如果没有任何的输出，说明你的 cpu 不支持，将无法成功安装 KVM 虚拟机。

\2. 当你硬件本身支持虚拟化，但查询相应参数无果时，请检查 BIOS 设定，确认你的 BIOS 中开启了硬件支持虚拟化的功能！

将如下选项设为Enabled
Intel(R) Virtualization Tech [Enabled]

# 四、KVM虚拟化安装

\1. 安装 KVM 要求

```
（1）***\*64bitCPU( 支持虚拟化 VT-x or AMD-V\****)
（2）2G 以上空闲内存，确认内存大小
    grep -e MemTotal /proc/meminfo
    free -m
（3）6GB 空闲存储空间
```

\2. 安装 KVM 并检测
（1）YUM 安装 KVM

```
yum install kvm virt-manager libvirt libvirt-python python-virtinst libvirt-client qemu-kvm qemu-img
```

（2）YUM 安装 KVM( 简单版 )

```
yum install kvm virt-manager libvirt*
```

（3）如果无法连入互联网 , 可自行建立源来完成安装并避免各种关联。建立一个本地的 YUM 源：

kvm虚拟化所需组件介绍

\3. kvm: 核心套件 ***

```
virt-manager: 图形化 KVM 管理软件
libvirt: 提供虚拟机与宿主相互通信的机制
libvirt-python: 允许使用 libvirt API
python-virtinst:CLI 下创建 KVM 的工具
libvirt-client: 提供 client 访问 kvm 服务器的机制 ,并包含 virsh 命令进行          
          管理和控制 VMs
qemu-kvm: 提供用户级 KVM 环境
qemu-img:VMs 磁盘管理
```

 

3.启动 KVM

```
（1）modprobe kvm   　　　　#加载 kvm 模块
（2）lsmod | grep kvm 　　　　#查看加载成功
（3）systemctl start libvirtd
（4）systemctl status libvirtd
```

\4. 启动并检测 KVM
virsh list --all
如出现
Id Name State
\-------------------------------------------------------
则安装成功
\5. 在 GUI 模式下安装虚拟机，启动虚拟系统管理器

# 五、KVM网络模式设置

\1. NAT ( 默认上网 ) :虚拟机利用 host 机器的 ip 进行上网 . 对外显示一个 ip,
virbr0 是 KVM 默认创建的一个 Bridge，其作用是为连接其上的虚机网卡提供 NAT 访问外网的功能，默认ip为192.168.122.1
\2. 自带的Bridge : 将虚拟机桥接到 host 机器的网卡上 ,vm和 host 机器都通过 bridge 上网 . 对外有同网段的不通 ip，此种方式host却不能和vm联通
\3. Linux Bridge : 基本原理就是创建一个桥接接口 br0 ，在物理网卡和虚拟网络接口之间传递数据。此种方式host却可以和vm联通
Linux Bridge 是 Linux 上用来做 TCP/IP 二层协议交换的设备，其功能大家可以简单的理解为是一个二层交换机或者 Hub。多个网络设备可以连接到同一个 Linux

Bridge，当某个设备收到数据包时，Linux Bridge 会将数据转发给其他设备

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps4.jpg) 

 

 

添加 br0 网卡的配置文件

```shell
cd /etc/sysconfig/network-scripts
cp ifcfg-ens33ifcfg-br0
```

（2）修改网卡配置文件

1.====vim ifcfg-eth0

```shell
TYPE=Ethernet
NAME=ens33
DEVICE=ens33
ONBOOT=yes
BRIDGE=br0
```

 

2.vim ifcfg-br0

```shell
TYPE=Bridge
NAME=br0
DEVICE=br0
ONBOOT=yes
BOOTPROTO=static(或者dhcp)
```

（3）重启host：reboot或者重启网卡

（4）检查

```shell
ethtool br0
brctl show
ifconfig br0
```

 

```shell
[root@localhost ~]# brctl show
bridge name   bridge id     STP enabled   interfaces
br0     8000.000c29e7d62c   no     ens33
virbr0     8000.5254001b9b1c   yes     virbr0-nic

[root@localhost ~]# ethtool br0
Settings for br0:
  Link detected: yes
```

 

可以看到bro端口为连接状态。

 如果br0上并没有ip地址转换，试试以下方法：

1）重新应用下nat

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps5.jpg) 

2）再windows上搜索服务，将dhcp改为启动。

 

# 六、生成虚拟机流程

点击系统工具——虚拟系统管理器——生成新虚拟机（本地介质）——浏览镜像文件——选择内存——自定义配置——完成

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps6.jpg) 

 

'生成新虚拟机（本地介质）

 ![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps7.jpg)

 

 浏览镜像文件

 ![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps8.jpg)

 

 

这就需要上传镜像文件到/var/lib/libvir/images/，此目录也是磁盘文件和镜像文件的目录。

 ![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps9.jpg)

 

 ![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps10.jpg)

 

选择内存

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps11.jpg) 

 

自定义配置

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps12.jpg) 

 

勾选自定义配置后就进入此页面，选择引导选项，箭头所指意思是增加启动时的引导，可不选。

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps13.jpg) 

 

上面勾选了virtio磁盘的选项，这里的原路径默认为上传镜像的同一级目录。

所以在创建完虚拟机后，再次浏览镜像文件会发现多出一个磁盘文件

 ![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps14.jpg)

 

IDE选项的原路径默认为上传镜像文件的目录。

 ![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps15.jpg)

 

错误解决

这是因为libvirt负责虚拟机与宿主机的通信

如果网卡配置错误或者建立通信的环节出现错误的话。

libvit就会运行libvirtd守护进程，这也是一种保护方式。

如果网卡都没有配置错误的话关闭防火墙试试。

![img](kvm%E8%99%9A%E6%8B%9F%E5%8C%96.assets/wps16.jpg) 

 

确认以上无误后就可以开始点击创建虚拟机了！！

 

 

 

# 解决1000M网卡问题

1、当我们安装完虚拟机， 发现虚拟机竟然是 100M 网络， 传输速率很低，前提物理网卡不是100M的   

需要我们修改/etc/libvirt/qemuvm01.xml 配置文件网卡段,改为 e1000，千兆以太网卡：

```shell
<model type='e1000'/>
```

添加完毕， 然后重新定义 virsh define vm01.xml， 重启虚拟机即可

reboot

 

 

 

 

# KVM虚拟机在使用vnc连接时鼠标不同步的问题

在VNC界面中感觉virt-manager管理的虚拟机界面总是鼠标跟不上，指到哪儿也看不出来，界面上一直显示press control_l+a/t_l来移动鼠标!十分郁闷！

配置方法

```shell
[root@openstack ~]# cd /etc/libvirt/qemu
[root@openstack qemu]# ls
networks test-win2008.xml
[root@openstack qemu]# cp test-win2008.xml /opt/
[root@openstack qemu]# vim test-win2008.xml        //在<devices>标签中添加下面这段配置
<devices>  
......                   
 <input type='tablet' bus='usb'/>            //即添加这句话即可！
......  
</devices>
[root@openstack qemu]# virsh define /etc/libvirt/qemu/test-win2008.xml
```

定义域 test-win2008（从 /etc/libvirt/qemu/test-win2008.xml）

 

然后重启虚拟机后，发现虚拟机中的鼠标就会好事了，打开VNC查看虚拟机界面后默认情况下虚拟机中的鼠标指针和实体机的鼠标指针就是重合的，且两者运动速度也是同步的，

这下就彻底解决了鼠标指针漂移/不同步的情况了！

 

使用virt命令管理虚拟机

```
[root@kvm-server ~]# virsh --help                                     #查看命令帮忙
[root@kvm-server ~]# virsh list                                       #显示正在运行的虚拟机
[root@kvm-server ~]# virsh list --all                                 #显示所有的虚拟机
[root@kvm-server ~]# virsh start vm-node1                             #启动vm-node1虚拟机
[root@kvm-server ~]# virsh shutdown vm-node1                          #关闭vm-node1虚拟机
[root@kvm-server ~]# virsh destroy vm-node1                           #虚拟机vm-node1强制断电
[root@kvm-server ~]# virsh suspend vm-node1                           #挂起vm-node1虚拟机
[root@kvm-server ~]# virsh resume vm-node1                            #恢复挂起的虚拟机
[root@kvm-server ~]# virsh undefine vm-node1                          #删除虚拟机，慎用
[root@kvm-server ~]# virsh dominfo vm-node1                           #查看虚拟机的配置信息
[root@kvm-server ~]# virsh domiflist                                  #查看网卡配置信息
[root@kvm-server ~]# virsh domblklist vm-node1                        #查看该虚拟机的磁盘位置
[root@kvm-server ~]# virsh edit vm-node1                              #修改vm-node1的xml配置文件
[root@kvm-server ~]# virsh dumpxml vm-node1                           #查看KVM虚拟机当前配置
[root@kvm-server ~]# virsh dumpxml vm-node1 > vm-node1.bak.xml        #备份vm-node1虚拟机的xml文件，原文件默认路径/etc/libvirt/qemu/vm-node1.xml
[root@kvm-server ~]# virsh autostart vm-node1                         #KVM物理机开机自启动虚拟机，配置后会在此目录生成配置文件/etc/libvirt/qemu/autostart/vm-node1.xml
[root@kvm-server ~]# virsh autostart --disable vm-node1               #取消开机自启动
```

删除uuid删除网卡的mac地址和源文件的路径修改

```
virsh list --all 
virsh undefine centos
virsh define centos
virsh destry centos
```

 

 

#  虚拟化中的快照

快照（Snapshot）是指数据集合的一个完全可用拷贝，该拷贝包括相应数据在某个时间点（拷贝开始的时间点）的映像。
快照可以是其所表示的数据的一个副本，也可以是数据的一个复制品；从技术细节讲，快照是指向保存在存储设备中的数据的引用标记或指针；快照有点像是详细的目录表，但它被计算机作为完整的数据备份来对待。
快照有三种基本形式：基于文件系统、基于子系统、基于卷管理器。

 

 

 

# 安装vnc  

https://www.cnblogs.com/kevingrace/p/5821450.html   参考连接  

 

 

 

# 命令转换qcow2文件：

```shell
qemu-img convert -f qcow2 myimage.qcow2 -O vmdk my.vmdk
```

转换完成后直接使用

 

 