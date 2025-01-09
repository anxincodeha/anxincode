> 本文收录于公众号「[安心代码](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和github开源项目「[anxincode](https://github.com/anxincodeha/anxincode)」：https://github.com/anxincodeha/anxincode，公众号内回复「笔记」或者查看github项目README.md即可获取所有的编程学习笔记和资料📝，欢迎大家关注👀和star⭐️
>![](https://raw.githubusercontent.com/anxincodeha/anxincode/refs/heads/main/%E6%AC%A2%E8%BF%8E%E5%85%B3%E6%B3%A8%E5%85%AC%E4%BC%97%E5%8F%B7%E2%80%9C%E5%AE%89%E5%BF%83%E4%BB%A3%E7%A0%81%E2%80%9D.png)

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家介绍下 linux 修改主机名重启后失效的解决方式

事情是这样的：我在 VMware 中创建了一台虚拟机，重启后忽然发现虚拟机的主机名变成了 ip 地址，就想修改下主机名，网上修改主机名的方式有两种：

1. 通过`hostnamectl set-hostname 主机名`修改（这种应该是临时方式，重启后就会失效）
2. `vim /etc/hostname`这种是持久化的方式，理论上重启主机后也有作用，**但是，但是！我重启主机后修改的主机名居然失效了！**😵‍💫😢



在网上搜了很久，才找到一个解决方式，那就是修改`/etc/sysctl.conf`文件，加这么一行：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736343275897-58446304-0d50-46a1-90c2-11deb8d5d0eb.png)

```java
// localhost就是设置的主机名
kernel.hostname=localhost
```

居然就起作用了🌈🎉👏修改的主机名即使在重启后也会生效。

至于原理吗，暂时不知道😭😭😭不过看这个配置，应该是和内核（kernel）相关的设置~

相关参考：

https://serverfault.com/questions/348863/setting-new-hostname-on-centos-it-changes-back-after-restart

