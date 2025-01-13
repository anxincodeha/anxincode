> 本文收录于**公众号**「[**安心代码**](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和**github开源项目**「[**anxincode**](https://github.com/anxincodeha/anxincode)」：[https://github.com/anxincodeha/anxincode](https://github.com/anxincodeha/anxincode)，**公众号内回复**「**笔记**」或者**查看github项目README.md即可获取所有的编程学习笔记和资料**📝，欢迎大家关注👀和star⭐：
>
> ![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736051954989-61599409-7805-43cf-8b13-c18817460003.png)
>

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家分享下 VMware 中非常常用并且好用的一个操作：如何克隆一台虚拟机📝⚙️🛠️✅

# 一、为什么要克隆虚拟机
有时候我们经常需要准备多个虚拟机进行不同环境的搭建，安装不同的软件。传统的方法就是从零开始创建一个虚拟机然后按部就班的进行各种配置⚙️具体可以看我的这篇博客📝：[一次成功！最新VMWARE安装CentOS7教程!](https://mp.weixin.qq.com/s/cwJ7XpxNHXBVMTKVkS8qXw)。但是如果需要配置多台虚拟机，那么这种办法非常耗时并且重复工作很多😢😢😢如果我们可以像复制某个文件一样复制虚拟机的话，那么这项工作就轻松多了。我们可以复制出多个虚拟机，然后再为每个虚拟机进行特定的配置，这样就可以减少大量创建虚拟机并完成基础配置的重复工作了😊😊😊VMware 当然也为我们提供了这项功能，就是**虚拟机的克隆功能**

# 二、VMware 如何克隆虚拟机
## 1.准备需要克隆的虚拟机
VMware 中我提前装备好了一个待克隆的虚拟机，这台虚拟机**是一台安装好了各种常见软件并且完成各种基础配置后并且完成了快照备份的虚拟机，是一台纯净的虚拟机，专门用做克隆**📋**的，大家也可以准备这样一台虚拟机**

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606118491-72bd4226-e9e9-43ff-9897-c499b6458b4a.png)


>💡注意：如何为虚拟机生成快照，可以参考下我的这篇博客📝：[VMware虚拟机必会操作：为虚拟机生成快照](https://mp.weixin.qq.com/s/aTDoZqBH0ZICBrIy7Rd4pA)。关于 Linux 各种基础软件和基础配置,可以参考我的专栏：[玩转Linux](https://github.com/anxincodeha/anxincode/tree/main/%E7%8E%A9%E8%BD%ACLinux)



## 2.关闭需要克隆的虚拟机
首先在虚拟机中执行`shutdown -h now`

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606385789-fc6a0512-8a4c-4046-bd8c-300df06ab1e4.png)

确认虚拟机已经关机：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606432124-fe4b5fe9-eba4-4577-8081-ff26b7defe1e.png)

## 3.克隆虚拟机
右键要克隆的虚拟机，选择`管理`>`克隆`

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606520525-69ddf6a1-e33f-44b2-ab04-3398b399fc5f.png)

在弹出来的窗口中选择`下一页`：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606629979-5d26f182-9e02-472a-a610-6e2bb98e4fce.png)

然后按下图操作：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606695621-2b29106d-ec87-4093-ae67-442f41567f13.png)

选择`创建完成克隆`：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606762796-eeb348b3-78f5-4925-ac10-5edb0acf9499.png)

为虚拟机设置名字和存储路径，注意不要包含中文、空格或者其他奇怪的字符：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736606912194-30ca2a2a-2edb-4030-9f7e-633c80cc7451.png)

然后耐心等待克隆完成：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736607084345-31b075d8-3e09-44d8-b1e8-6d1e2d713b00.png)

完成了，点击`关闭`：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736607105590-f3aeeb93-33ca-46f9-a457-f4f581b38e68.png)

可以看到左侧多了一个虚拟机：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736607155683-03c76f35-267c-4e8e-9979-eb31161021b6.png)

到这一步还不算完成，我们需要对克隆获得的虚拟机进行一些设置。

## 4.设置克隆获得的虚拟机
因为这台新的虚拟机是克隆获得的🖥️，ip 和原先那台机器是一样的，所以我们需要改下新机器的 ip

首先，开启虚拟机：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736658223044-989dde04-94b7-48e9-92b4-c9321c643132.png)

然后，登录进入到虚拟机内，执行`vim /etc/sysconfig/network-scripts/ifcfg-ens33`，修改`IPADDR`，这个就是虚拟机的 ip 地址：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736658335215-19435893-988c-4aff-acc5-a012da603cf0.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736658426078-2749c598-c9c3-4c1f-a8b7-190b6edf6e0b.png)

然后通过`systemctl restart network`重启网络：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736658576033-360fabd0-4baf-4ca8-8ad5-7e7788f5616f.png)

重启完成后，`ip addr`查看新的 ip 地址：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736658771328-2fafd99d-9188-4377-8924-a391b49727c8.png)

发现 ip 地址的确改动成功了，至此，克隆操作就算完成了🌈🎉👏

# 三、参考
[https://docs.vmware.com/cn/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-C86E70AD-85A9-4D85-AEBB-135AA5648554.html](https://docs.vmware.com/cn/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-C86E70AD-85A9-4D85-AEBB-135AA5648554.html)

