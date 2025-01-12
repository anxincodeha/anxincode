> 本文收录于**公众号**「[**安心代码**](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和**github开源项目**「[**anxincode**](https://github.com/anxincodeha/anxincode)」：[https://github.com/anxincodeha/anxincode](https://github.com/anxincodeha/anxincode)，**公众号内回复**「**笔记**」或者**查看github项目README.md即可获取所有的编程学习笔记和资料**📝，欢迎大家关注👀和star⭐：
>
> ![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736345049932-31910132-e4c5-4187-b03c-5ff647224114.png)️
>

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家分享下 centos 下载软件失败时，怎么更换 yum 源📝⚙️🛠️✅

# 一、从 centos下载软件失败说起😭
新在 VMware 开了一台 centos,然后想下个 vim:

```java
yum install vim -y
```

结果报这一串错误😭😭😭：

```shell
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
Could not retrieve mirrorlist http://mirrorlist.centos.org/?release=7&arch=x86_64&repo=os&infra=stock error was
14: curl#6 - "Could not resolve host: mirrorlist.centos.org; Unknown error"


 One of the configured repositories failed (Unknown),
 and yum doesn't have enough cached data to continue. At this point the only
 safe thing yum can do is fail. There are a few ways to work "fix" this:

     1. Contact the upstream for the repository and get them to fix the problem.

     2. Reconfigure the baseurl/etc. for the repository, to point to a working
        upstream. This is most often useful if you are using a newer
        distribution release than is supported by the repository (and the
        packages for the previous distribution release still work).

     3. Run the command with the repository temporarily disabled
            yum --disablerepo=<repoid> ...

     4. Disable the repository permanently, so yum won't use it by default. Yum
        will then just ignore the repository until you permanently enable it
        again or use --enablerepo for temporary usage:

            yum-config-manager --disable <repoid>
        or
            subscription-manager repos --disable=<repoid>

     5. Configure the failing repository to be skipped, if it is unavailable.
        Note that yum will try to contact the repo. when it runs most commands,
        so will have to try and fail each time (and thus. yum will be be much
        slower). If it is a very temporary problem though, this is often a nice
        compromise:

            yum-config-manager --save --setopt=<repoid>.skip_if_unavailable=true

Cannot find a valid baseurl for repo: base/7/x86_64

```

这个错误的原因就是安装软件时访问 yum 源失败。遇到这种情况，可以把 yum 源换成国内的阿里 yum 源。

# 二、更换仓库为阿里 yum 源
## 1.打开阿里镜像官方地址
[https://developer.aliyun.com/mirror/](https://developer.aliyun.com/mirror/)

点这个 `centos`

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736345721514-32581baa-407d-48ee-9207-461efc3f0a2e.png)

进入[https://developer.aliyun.com/mirror/centos?spm=a2c6h.13651102.0.0.3e221b11sm7iDg](https://developer.aliyun.com/mirror/centos?spm=a2c6h.13651102.0.0.3e221b11sm7iDg)

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736345752259-5b91d0d5-0c53-4f88-b5b8-b54a4a023ecb.png)

这个文档中有关于 centos6 、centos7、centos8 怎么配置 yum 源的方法，我开的虚拟机是一台 centos7，所以演示下 centos7 的配置方式。

## 2.虚拟机备份源 yum 源
```shell
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

## 3.下载阿里云配置文件
这一步，官方文档给出的命令是：

```shell
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
```

或者：

```shell
curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
```

如果你的虚拟机没有安装过 wget 软件和 curl 软件，那么可以手动下载[https://mirrors.aliyun.com/repo/Centos-7.repo](https://mirrors.aliyun.com/repo/Centos-7.repo)，然后上传到到虚拟机中，文件位置和文件名：`/etc/yum.repos.d/CentOS-Base.repo`

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736433480249-23e98694-478c-43ed-8d8e-55c4474e67bc.png)

## 4.运行yum makecache<font style="color:rgb(36, 41, 46);">生成缓存</font>
执行：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736433729480-0dc0330a-a2d9-4510-91ad-4d56192e0271.png)

会去下载一些东西，耐心等待完成

## 5.再运行yum install vim -y 下载 vim 测试下
执行

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736433689196-12fb24d8-fd81-4924-9d0f-813e6c404159.png)

等待下载完成：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736433667061-f5c880f0-9dcf-4dc9-a35f-0d2af0a5859c.png)

执行下 vim 看是否正常:

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736433783659-d35b82a6-755a-41ce-bacb-83588b37dfc7.png)

结果当然是成功啦🌈🎉👏~~~

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736433819729-6481c09d-93e6-46bb-9072-ff6b87e575f1.png)

