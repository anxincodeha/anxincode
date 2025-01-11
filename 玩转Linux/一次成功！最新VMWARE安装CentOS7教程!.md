> 本文收录于**公众号**「[**安心代码**](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和**github开源项目**「[**anxincode**](https://github.com/anxincodeha/anxincode)」：[https://github.com/anxincodeha/anxincode](https://github.com/anxincodeha/anxincode)，**公众号内回复**「**笔记**」或者**查看github项目README.md即可获取所有的编程学习笔记和资料**📝，欢迎大家关注👀和star⭐：

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~在这篇文章中介绍下如何在 VMWARE 中一次安装成功 CentOS7📝⚙️🛠️✅

# 目录




[TOC]

# （一）下载 CentOS7 镜像
官网下载地址：

[https://vault.centos.org/7.9.2009/isos/x86_64/](https://vault.centos.org/7.9.2009/isos/x86_64/)

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735455157386-f68a7e16-7325-4a2e-9411-defd7bc44103.png)

官网打不开或者官网下载速度慢的话，可以试下从阿里云下载：

[centos-7-isos-x86_64安装包下载_开源镜像站-阿里云](https://mirrors.aliyun.com/centos/7/isos/x86_64/)

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735455264124-5c6339e4-1bd9-4edb-8350-5e665cb45a40.png)

# （二）虚拟机安装下载好的镜像
## 1.打开 vmware ,选择`文件`>>`新建虚拟机`
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735464874860-330c3192-e60a-4b82-824f-75e6283cc31d.png)

## 2.按如下截图依步骤操作：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735464939612-fc3898c5-821a-4ba1-b378-0306337f3186.png)

## 3.按如下截图依步骤操作：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465025582-a7f92061-efbf-4383-a35f-7e0790263a45.png)

## 4.按如下截图依步骤操作：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465092394-e8a7f258-fb71-4606-907f-442f3ca0cb31.png)

## 5.设置虚拟机的名字和位置，这两者都是可以自己设置的,注意名字和路径都不要包含中文
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465396815-f513c3d3-2341-4bb2-9a41-e7039ae8f81b.png)

## 6.设置虚拟机的磁盘大小，一般 30 个 G 就够用了：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465498693-b8469734-0a46-4792-9178-d1db7e83bb65.png)

## 7.点击完成：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465603036-2b41b6bb-e74a-4085-b6d2-8100531b9a0d.png)

然后左侧`我的计算机`会出现创建的虚拟机：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465658511-1432edb5-c9b7-4695-a760-c15fc9acb571.png)

## 8.选择刚才创建的虚拟机，然后点击`CD/DVD(IDE)`
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465772039-0d2bf56e-a7cc-4fa8-8d7e-f5155fcbe724.png)

## 9.选择提前下载好的 ISO 文件：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735465975941-54dd08f1-b19e-4302-88af-60f05236209c.png)

## 10.开启此虚拟机：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466024087-4e471e04-61bd-4258-a3ee-160d028058c5.png)

## 11.在这个界面等待一段时间：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466084645-1e1da53d-4c81-4b5f-b434-d015631c7280.png)

后面会弹出很多文字，继续等待：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466137439-0bdfac4c-21e7-429b-aa24-742b6a3c58f4.png)

最终来到这个界面：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466156033-491f65ca-9be4-4bbb-8929-474090844b39.png)

## 12.选择英文：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466218464-cd54c9d6-bc95-4660-9fba-1d6ba75ca671.png)



> 💡注意：有很多人在安装软件的时候都会选择中文界面，其实中文界面和英文界面只是个习惯问题，还是推荐大家使用英文界面，因为有些软件的中文界面的汉化并不到位，翻译模糊，翻译不完全，这样在遇到问题搜索🔍的时候很难找到确切的解决方案

## 13.设置时区和时间
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466497625-95262faa-540b-48b2-8c4f-4c30201b9a56.png)

一般选择上海，然后设置下时间，AM 表示上午，PM 表示下午

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466689295-f4e68fb7-c407-4bf6-9d03-eff309cd293d.png)

## 14.设置下硬盘分区，一般选择自动配置分区即可
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466776639-0ffaa657-0a12-414a-865e-8274c6de1431.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466907774-6c3a4805-8b52-4416-ad21-310a718a0300.png)

## 15.选择配套软件，一般最小化安装，最小化安装是没有图形化桌面的，通过命令行与操作系统交互：
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735466963414-9f11e937-0bb6-45ff-a4d7-aea53d433dbf.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735467068859-a5c21a81-751b-483b-8878-c2b6714e2a9a.png)

## 16.点击 Begin Installation 开始安装
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469285321-37a930ad-cf51-480c-a4e4-be91eaf99763.png)

## 17.设置下 root 的密码
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469395479-adfe4879-e815-41c7-890a-53a659e3c132.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469375115-12b82f7c-24e5-4008-aecc-6cd0242c417f.png)

## 18.等待安装
在这个界面等待安装

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469418834-73ba9bcc-1ebe-4f97-8a31-362f9e991ada.png)



## 19.安装完成后点击重启
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469725301-aeca52a7-d54c-4db6-b1a2-23b66ac96090.png)

## 20.输入账号名，密码登录
输入密码时，并没有任何提示符显示，这是正常现象

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469802245-47194d74-fc34-4620-8db2-b739daec02eb.png)

## 21.配置内存&网络
右键虚拟机，选择设置：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735469997252-f6af6199-6098-458c-908e-2e4fcfa80d23.png)

设置一下内存，2G 一般就够用了

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735470088818-642450fc-fcd7-493b-aca9-517c77988801.png)

网络选择 NAT 模式：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735470192088-53246241-d9ef-423d-b7f5-73683330c753.png)

## 22.选择虚拟网络编辑器
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735470487440-eab655ef-dcab-483d-b238-c0172dedc74b.png)

## 23.更改设置
![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735470556886-99fe00f2-6129-457f-8a30-23edafbc6d30.png)

选择 `VMnet8`，然后`NAT 设置`

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735470613260-7b6a9742-103d-4d08-96e3-214775225a7e.png)

网关 ip 的网段要和子网 IP 的网段（在这里网段是 ip 地址的就是前三部分，我的是 192.168.101）一致，网关 IP 一般就是`.2`，点确定

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735470853278-31adde6d-43c7-4c86-9cbe-bf0368b67f2b.png)

## 24.设置静态 ip
执行命令`cd /etc/sysconfig/network-scripts/`，查看这个目录下有没有一个`ifcfg-XXX`的配置文件，我的是`ifcfg-ens33`:

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735471089187-248c62af-e7f0-4e3c-a6dc-bc757904af8c.png)

执行`vi ifcfg-ens33`,然后对这个文件进行修改：

+ `ONBOOT`设置为 `yes`
+ `BOOTPROTO`设置为`static`
+ 添加`IPADDR=192.168.101.6`，IP 地址的网络部分要和前面设置的 NAT 的子网的网络部分一致：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735480322334-1f50e8ee-63b7-41b2-8648-05687cf65fad.png)

一般要避开`.1`,`.2`的主机号地址。（`.1`是 windows 中 VMNET8 的 ip 地址，`.2`是网关地址）

+ 添加`NETMASK=255.255.255.0`
+ 添加`GATEWAY=192.168.101.2`，这个 GATEWAY 地址眼熟吗？就是前面 NAT 设置中的网关地址：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735480609743-04de852b-b938-49a6-8f50-8ed7e36b2afd.png)

+ 添加 `DNS1=192.168.101.2`,DNS1 一般用 GATEWAY 的值就行。

最终我的`ifcfg-ens33`的配置如下：

```plain
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=ens33
UUID=1866a703-5afb-48ef-9dea-5b52972ab86e
DEVICE=ens33
ONBOOT=yes
IPADDR=192.168.101.6
GATEWAY=192.168.101.2
NETMASK=255.255.255.0
DNS1=192.168.101.2
```



> ❗❗❗注意：配置 ip 地址相关的内容时，一定要保证 ip 地址的网段和自己配置的 NAT 模式的子网的网段相同，千万不要直接根据我的配置复制粘贴❗❗❗

## 25.重启网络
执行`service network restart`，重启网络

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735476559895-39e4bfae-2ac8-44aa-81dd-7c0b5e521427.png)

执行`ip addr`命令查看 ip 地址：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735476638422-549b0494-4415-495e-9477-5ae29e4f35d2.png)

ip 地址就是我们之前配置的值。

这个时候，已经可以用 ssh 客户端连接这台虚拟机了。

## 26.验证网络是否通
先把防火墙关了：

`systemctl stop firewalld`

`systemctl disable firewalld`

观察下防火墙状态：

`systemctl status firewalld`

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735481186676-52085808-e394-48ad-9e14-763865a2fb74.png)

观察到`Active: inactive (dead)`说明防火墙关闭成功。

可以 ping 下百度：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735481278218-35ec0418-1681-42c1-85d2-081171a39277.png)

到这里说明虚拟机大体就算安装成功了👏🎉🌈！

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1735739432009-bc97dee3-0b52-4cb9-92e9-a59061f0798f.png)



