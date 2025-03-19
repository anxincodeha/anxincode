> **本文收录于公众号「**[**安心代码**](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)**」和github开源项目「**[**anxincode**](https://github.com/anxincodeha/anxincode)**」：**[**https://github.com/anxincodeha/anxincode**](https://github.com/anxincodeha/anxincode)**，公众号内回复「笔记」或者查看github项目README.md即可获取所有的编程学习笔记和资料**📝**，欢迎大家关注**👀**和star**⭐：
>
> ![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1736769473517-5b95c2cc-f21e-4758-bf90-4bc62b2e5998.png?x-oss-process=image%2Fformat%2Cwebp)
>

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家分享下**怎么在本地接入属于自己的官方满血版 deepseek~**

# **本文收录于我的专栏「玩转编程开发工具与办公软件」，专栏持续更新中！**
在之前的文章📝[《deepseek服务器繁忙？一招教你拥有属于自己的满血版deepseek！新手零基础可操作！》](https://github.com/anxincodeha/anxincode/tree/main/%E7%8E%A9%E8%BD%AC%E7%BC%96%E7%A8%8B%E5%BC%80%E5%8F%91%E5%B7%A5%E5%85%B7%E4%B8%8E%E5%8A%9E%E5%85%AC%E8%BD%AF%E4%BB%B6)中介绍了怎么接入阿里云的 deepseek api，当时 deepseek 官方 api 是无法充值的，但是现在官方已经可以充值了：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740648463964-adcfb048-f63c-4a01-8d17-0f53bcbe28f5.png)

下面给大家演示下怎么接入deepseek 官方的api。

首先，去 chatbox 官网[https://chatboxai.app/zh](https://chatboxai.app/zh)下载安装 chatbox，这是一个 AI 应用，有客户端也有网页版，支持各种 AI 模型及它们的 API,后面我们要把获取到的 deepseek-r1 API key 配置到这个客户端里面：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740147097671-2a438ef0-a89a-4597-a2d1-772ed08bd379.png?x-oss-process=image%2Fformat%2Cwebp)

chatbox 的安装很简单，没有什么需要注意的，按操作提示即可。安装完成后，我们来到 deepseek 官方开放平台：[https://platform.deepseek.com/](https://platform.deepseek.com/)，登录：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649012233-96f14583-d34c-4488-9ea8-20fea87cbaaa.png)

登录后来到这个界面：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649069160-559f51a9-85d7-4d9b-8690-e5e137316e88.png)

点击“去充值”，价格在这里看，[https://api-docs.deepseek.com/zh-cn/quick_start/pricing/](https://api-docs.deepseek.com/zh-cn/quick_start/pricing/)，

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649160467-4fe1781b-d61b-4ba0-892a-44ff5006d8b0.png)

可以说相当便宜了。

充值完成后是这样的：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649282933-6de748cb-998b-4cce-8811-5574f2251a88.png)

我们来到“API keys”界面，选择"创建 API key":

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649351602-5f250adc-e44b-46ef-8cc3-d7939d5339be.png)

随便起个名，然后点创建：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649800689-d092724f-573f-4f30-81dd-960478dc4183.png)

创建成功的话，会弹出个窗口，点下“复制”，就可以把 api key 复制到剪贴版中了，待会儿在 chatbox 中配置时会用到这个 api key:

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740649940751-e2b04002-51d1-4886-926d-e10d1f7b6887.png)

打开 chatbox,点击设置：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740651056792-edd0d10e-5afc-49df-91c8-8617db5f9671.png)

在“模型”界面配置，点击模型提供方按钮：（你的界面和我可能不太一样，因为我之前配置过阿里云百炼的 deepseek api，这个不要紧）：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740651437265-085d9d1e-67c7-43b8-803c-882fba1406f2.png)

选择 deepseek api:

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740651543134-6af82109-6084-4005-81ac-1fa1458dc92d.png)

填写密钥，选择模型：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740651698106-f39a3258-3a0c-4ba7-9d36-81ba8822d199.png)

这里有必要说明的是，模型有 3 个：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740651723325-d09173f0-a58a-42e9-8c2a-2b7a9ac82de2.png)

`deepseek-chat`就是`DeepSeek-V3`，`deepseek-reasoner`就是`DeepSeek-R1`，`deepseek-coder`是一个代码生成模型。

配置好了，点保存就可以了~

我们看配置的是否成功，点击新对话，输入你想问的问题：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740652126914-0c7a9156-71ba-453a-aa15-e4860ffcf3e8.png)

可以看到有输出了，配置成功🏆🎖️👏🙌！

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740652295287-834b0154-5b65-431a-90bc-4e4b5db6951b.png)

先别着急划走😂😂😂，还有一些地方需要注意：

在设置>显示中，可以关闭自动收起代码块，省的每次输出代码的时候需要点一下才能展开代码块：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740652515911-83d24692-9b3c-4b74-ae3c-0cab26c7011f.png)

也是在显示界面，可以调整字体大小：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740661958922-0a68bd85-2395-44c1-89fb-d423e556a6b4.png)

在 deepseek 的开放平台，我们可以看到用量信息：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740662102992-14ba9b6b-c012-4aed-ba35-35745b8c68b9.png)

其实在 chatbox 也能看到每条消息消耗的 token:

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740662397889-b2c790d8-0632-483f-8200-c23bd0cd34a3.png)

可以设置下余额预警，当余额低于某个额度时会通过手机号、邮箱发提示：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740662216242-077a832c-21fe-414e-815b-94f78166c126.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1740662430070-71dad3f1-b206-484a-bbd3-26e3d3c0323a.png)

相关阅读：[《deepseek服务器繁忙？一招教你拥有属于自己的满血版deepseek！新手零基础可操作！》](https://github.com/anxincodeha/anxincode/tree/main/%E7%8E%A9%E8%BD%AC%E7%BC%96%E7%A8%8B%E5%BC%80%E5%8F%91%E5%B7%A5%E5%85%B7%E4%B8%8E%E5%8A%9E%E5%85%AC%E8%BD%AF%E4%BB%B6)

