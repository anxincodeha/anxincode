> 本文收录于**公众号**「[**安心代码**](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和**github开源项目**「[**anxincode**](https://github.com/anxincodeha/anxincode)」：[https://github.com/anxincodeha/anxincode](https://github.com/anxincodeha/anxincode)，**公众号内回复**「**笔记**」或者**查看github项目README.md即可获取所有的编程学习笔记和资料**📝，欢迎大家关注👀和star⭐：
> ![欢迎关注公众号“安心代码”](https://github.com/user-attachments/assets/3e13b08c-ddd1-4df1-be7e-b20cbde641f9)


安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家讨论下VMWARE中虚拟机ping不通vmnet8 的解决方式✅✅✅

# 目录

[toc]

# 问题现象:VMWARE中虚拟机ping不通vmnet8 了❗❗❗

今天遇到了一个问题💔💔💔，vmware 中新装的虚拟机能 ping 通百度，但是 ping 不通 vmnet8 这块网卡😢😢😢奇怪的是 windows 中居然能 ping 通新开的虚拟机😵‍💫  

如图所示，192.168.101.1 是我的 vmnet8 ip 地址，虚拟机中 ping 不通 vmnet8：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735565649563-5c1f7268-082a-4640-bff0-6b866fecb232.png)

windows 中 ping vmware 中的虚拟机（ip 地址为 192.168.101.6），居然能 ping 通：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735565983876-cc9525d9-e1b5-4182-a3b2-86c2351b3b5d.png)

# vmnet8 是什么？
大家可以注意下，安装完 vmware 之后，宿主机上会多出两个网卡 `vmnet1` 和 `vmnet8`:

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735566080876-16e5e2b5-6d5e-470d-8bfb-5613baf64af5.png)

<font style="color:rgb(25, 27, 31);">vmnet1表示的是用于仅主机模式下的虚拟交换机,vmnet8表示的是用于NAT模式下的虚拟交换机。也就是说，仅主机模式下，虚拟机和宿主机通信要通过vmnet1，NAT 模式下，虚拟机要通过 vmnet8 访问宿主机和外部网络。</font>





# <font style="color:rgb(25, 27, 31);">怎么解决？</font>
这个问题其实和 windows 的防火墙有关。

可以在搜索中搜防火墙打开win10 防火墙设置界面：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735566738591-b22f4578-cad2-4cca-83d9-40254cae2231.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735566763170-d9e90f21-2999-40e7-9250-b642a3c97fdd.png)

以关闭域网络为例讲下怎么关闭 windows 防火墙：

首先点击域网络：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735566837846-df8dfb1f-ab97-46a4-84af-ccaf1f63b576.png)

我的电脑上装了联想管家，防火墙被它接管了，点击打开应用，可以帮你确认是哪个应用接管了防火墙，需要关闭这个应用：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735566949678-743e04e3-4b80-4ed5-ab4f-96e06c6a8d0a.png)

关闭联想管家之后，再次进入域网络，现在界面是这样的：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735567010771-96dea413-91ac-4ca5-b019-dff2ccdc2877.png)

关闭域网络的防火墙：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735567031988-6b29abfd-a83a-4944-8321-6c1f7eaecf7a.png)

接下来再按关闭域网络的方法关闭专用网络和公用网络的防火墙，关闭之后大概这个样子：

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735567148117-17f9f3bf-7834-40e7-8f61-9902af16fca7.png)

这个时候再 ping vmnet8，就能 ping 通啦🌈🎉👏

![](https://cdn.nlark.com/yuque/0/2024/png/50835397/1735567255135-6020217e-e6d1-4cd0-abe5-0f71d5d1e5ba.png)

> ❗❗❗注意：ping 不同 vmnet8 不影响虚拟机的使用。所以还是要打开宿主机上关闭的防火墙❗❗❗ 

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1735739432009-bc97dee3-0b52-4cb9-92e9-a59061f0798f.png)



