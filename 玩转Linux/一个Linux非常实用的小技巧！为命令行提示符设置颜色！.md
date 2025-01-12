> 本文收录于公众号「[安心代码](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和github开源项目「[anxincode](https://github.com/anxincodeha/anxincode)」：[https://github.com/anxincodeha/anxincode](https://github.com/anxincodeha/anxincode)，公众号内回复「笔记」或者查看github项目README.md即可获取所有的编程学习笔记和资料📝，欢迎大家关注👀和star⭐
>
> ![欢迎关注公众号“安心代码”](https://raw.githubusercontent.com/anxincodeha/anxincode/refs/heads/main/%E6%AC%A2%E8%BF%8E%E5%85%B3%E6%B3%A8%E5%85%AC%E4%BC%97%E5%8F%B7%E2%80%9C%E5%AE%89%E5%BF%83%E4%BB%A3%E7%A0%81%E2%80%9D.png)
>

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家分享一个 Linux 中**非常实用**的小技巧，好看又好用！📝⚙️🛠️✅

# 一、为什么要为命令行提示符设置颜色
默认的 Linxu 命令行界面是这样的：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736517874350-938aa7e8-4dce-4681-b8d5-a4e6affe7732.png)

给大家看看我的 linux 的命令行界面：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736520711932-9dc9b029-23b6-4e16-92ce-ee75623d9579.png)

怎么样？是不是很醒目呢😄😄😄这样设置一个最大的好处就是**在屏幕显示的多行文本中一下子找到我们命令行的位置，从而区分不同的文件、区分命令和文本等，尤其是通过命令行打印一大段文本时（一个典型的例子就是 tail 打印日志的时候~）**。举个例子🌰，这是命令行没设置前的样子：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736517785275-f323de0a-6b19-4d57-a641-758bb46e9310.png)

这是命令行设置后的样子：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736520037235-093ba918-ee63-406a-bc1f-5e3d75d406f3.png)

# 二、怎么为命令行设置颜色
通过设置`PS1`变量为命令行提示符设置颜色，这个变量就是设置命令行提示符格式的。

查看下默认格式下的 `PS1`值：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736519369206-ddf718c4-3363-4b24-8a83-2ff8136e8139.png)

```shell
[root@localhost ~]$echo $PS1
[\u@\h \W]$
```

我们修改下值：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736519894110-e2fe82ac-773f-4bf7-8944-f27094b47f5f.png)

```shell
PS1="\[\e[34m\][\u@\h \W]\$\[\e[0m\]"
```

然后，神奇的事情🌟🌟🌟发生了：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736519939274-71bff213-2e38-43e8-b737-7ee815def803.png)

好处也是显而易见的，我们再打开一个很长的文件，命令行输出看下：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736520037235-093ba918-ee63-406a-bc1f-5e3d75d406f3.png)

怎么样，这下是不是很容易区分命令行和文本内容了✨✨✨不过先别着急划走，我们还要持久化我们的设置⚙️✍️

# (三)重启不失效：持久化配置
上面配置的 `PS1`在虚拟机重新启动后会丢失，所以我们还需要持久化下配置。

首先，执行`vim ~/.bashrc`：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736520361506-61a3f0b8-bb78-4801-bc46-34dee1df8a93.png)

然后，把 上面的`PS1="\[\e[34m\][\u@\h \W]\$\[\e[0m\]"`复制到文件中并保存：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736520518700-2d3bd782-4a43-4f05-a3ab-0d1e058bed24.png)

这样无论电脑怎么重启都不会失效啦🌈🎉👏





