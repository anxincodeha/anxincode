> 本文收录于**公众号**「[**安心代码**](https://www.yuque.com/anxincode/dhdqgs/kbur0qozkulu6413?singleDoc#%20%E3%80%8A%E5%85%AC%E4%BC%97%E5%8F%B7%E5%9C%B0%E5%9D%80%E3%80%8B)」和**github开源项目**「[**anxincode**](https://github.com/anxincodeha/anxincode)」：[https://github.com/anxincodeha/anxincode](https://github.com/anxincodeha/anxincode)，**公众号内回复**「**笔记**」或者**查看github项目README.md即可获取所有的编程学习笔记和资料**📝，欢迎大家关注👀和star⭐：
>
> ![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1737205014340-7831ba6c-bd64-4186-b7fe-f23309c4a131.png)
>

安心代码，我是安心❤️💻😊朋友们好呀👋✨~~~这篇文章跟大家介绍下 `mysql` 的配置文件：`my.cnf`📝⚙️🛠️✅相信很多人和我一样，知道 mysql 有这么个配置文件，也在这个配置文件中进行过配置，但是还是有很多对这个配置文件不了解的地方。希望读完这篇文章后，可以让你对 mysql 的配置文件有更进一步的了解😊😊😊

# 本文收录于我的专栏「玩转 mysql」
# 一、mysql 的配置文件在哪里？
在 Linux 系统下，一般位于`/etc/my.cnf`或者`/etc/mysql/my.cnf`,当然也可以通过 linux 命令查询下文件的具体位置：

```shell
[root@192 ~]$find / -name "my.cnf*"
/etc/my.cnf
/etc/my.cnf.d
[root@192 ~]$
```

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1737207608993-bc519317-301f-4c3c-a822-abcb4e849b7b.png)

>  💡注意：怎么在 linux 下搜索文件，可以参考下我的这篇博客📝：[常用！Linux快速查找某个文件或文件夹位置](https://mp.weixin.qq.com/s/JI_5LERMVPoPjiAHCe-QGA)

# 二、mysql 原始配置文件内容
原始的配置文件内容如下：

```plain
# For advice on how to change settings please see
# http://dev.mysql.com/doc/refman/8.4/en/server-configuration-defaults.html

[mysqld]
#
# Remove leading # and set to the amount of RAM for the most important data
# cache in MySQL. Start at 70% of total RAM for dedicated server, else 10%.
# innodb_buffer_pool_size = 128M
#
# Remove the leading "# " to disable binary logging
# Binary logging captures changes between backups and is enabled by
# default. It's default setting is log_bin=binlog
# disable_log_bin
#
# Remove leading # to set options mainly useful for reporting servers.
# The server defaults are faster for transactions and fast SELECTs.
# Adjust sizes as needed, experiment to find the optimal values.
# join_buffer_size = 128M
# sort_buffer_size = 2M
# read_rnd_buffer_size = 2M

datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock

log-error=/var/log/mysqld.log
pid-file=/var/run/mysqld/mysqld.pid
```

可以看出，mysql 的配置文件是标准的 `INI 格式`，`INI 格式`指的是一种配置文件⚙️的格式：

1. 使用分区将配置分为多个逻辑模块（或者说，分组）。例如`[mysqld]`就是一个逻辑模块，表示 mysql 服务器的配置
2. 以键值对的形式存储配置项。 例如， `datadir=/var/lib/mysql`就是`[mysqld]`逻辑模块下的一个配置项

> 💡注意：配置要放在正确的逻辑模块下才能起作用

# 三、mysql 原始配置文件内容分析
mysql 原始配置文件中有些很多注释及初始配置，我们按部就班的看下。

## 1.文档地址
```plain
# For advice on how to change settings please see
# http://dev.mysql.com/doc/refman/8.4/en/server-configuration-defaults.html
有关如何更改设置的建议，请参阅：
http://dev.mysql.com/doc/refman/8.4/en/server-configuration-defaults.html
```

这部分注释明确告知了文档的地址，打开文档如下：

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1737209219804-0f0fd119-3e7b-4f95-a334-b071591c16a1.png)

## 2.innodb_buffer_pool_size
修改配置文件时可以参考文档，在此不多做赘述~

```plain
[mysqld]
# Remove leading # and set to the amount of RAM for the most important data
# cache in MySQL. Start at 70% of total RAM for dedicated server, else 10%.
去掉行首的 # 并设置 MySQL 中用于缓存最重要数据的内存量（RAM）。如果是专用服务器（只运行 MySQL），建议分配总内存的 70%；如果不是专用服务器（同时运行其他服务），建议分配总内存的 10%。
# innodb_buffer_pool_size = 128M
```

`innodb_buffer_pool_size`是 mysql 中 `InnoDB存储引擎`的一个关键参数，**它决定了 InnoDB 缓冲池的大小,缓冲池是用来缓存 InnoDB 表的数据📕和索引，减少 I/O 操作。**

## 3. disable_log_bin  
```plain
# Remove the leading "# " to disable binary logging
移除行首的 "# " 来禁用二进制日志功能
# Binary logging captures changes between backups and is enabled by
# default. It's default setting is log_bin=binlog
二进制日志记录捕获备份之间的更改，默认情况下处于启用状态。默认设置为log_bin=binlog
# disable_log_bin
```

`disable_log_bin`是关闭 mysql 二进制日志的配置。mysql 二进制日志用于记录所有涉及更改的 SQL 语句（例如 INSERT、UPDATE、DELETE 等），不记录只读的查询（如 SELECT，SHOW 等）。二进制日志结合备份文件，可以还原数据；同时，mysql 的主从复制🔄也依赖于二进制日志，主服务器将写操作记录✍到二进制日志中，然后通过网络🌐将日志内容传递给从服务器，从服务器通过读取二进制日志执行对应的操作，从而保证从服务器和主服务器数据的一致。

## 4.join_buffer_size 和sort_buffer_size 和read_rnd_buffer_size
```plain
# Remove leading # to set options mainly useful for reporting servers.
移除行首的 # 以设置主要用于报表服务器的选项
# The server defaults are faster for transactions and fast SELECTs.
服务器的默认配置更适合事务处理和快速 SELECT 查询。
# Adjust sizes as needed, experiment to find the optimal values.
根据需要调整大小，并通过实验找到最佳值
# join_buffer_size = 128M
# sort_buffer_size = 2M
# read_rnd_buffer_size = 2M
```

有两个新词，`reporting servers`和`fast SELECTs`。`reporting servers` 字面意思是报表服务器，这种服务器的职责就是执行复杂的查询任务和数据分析。而`fast SELECTs`指的是简单的 sql 查询，比如说单表查询或者有索引的查询。

这段注释的意思就是，**服务器的默认设置适合事务相关的 sql 语句和简单查询的 sql 语句，如果想要执行复杂**♾️**的 sql 查询，需要自己去调整参数并且通过实验找到最佳值。**

`join_buffer_size`：这个参数是一个内存缓冲区的大小，调整这个参数可以优化无索引连接（JOIN）时的性能。当两个表连接时，如果不能用索引的话，就只能一行一行的匹配，但是一行一行的从磁盘读很耗费性能，所以把数据批量加载到`join_buffer_size`。

`sort_buffer_size`：这个也是一个内存缓冲区的大小，当 mysql 执行需要排序的查询（如 `ORDER BY`）,如果排序的数据能够放入这个缓冲区，排序操作就会在内存中完成，很快；如果放不下，那么需要借助磁盘临时文件才能完成，性能就很差🐢了。

`read_rnd_buffer_size`：这个参数是排序操作后读取数据时的一块专用缓冲区的大小，减少随机 I/O 的影响。

## 5.datadir和socket和log-error和pid-file
```plain
datadir=/var/lib/mysql
socket=/var/lib/mysql/mysql.sock

log-error=/var/log/mysqld.log
pid-file=/var/run/mysqld/mysqld.pid
```

+ `datadir=/var/lib/mysql`：MySQL 存储数据库文件的根目录，通常用来存放数据库的物理表文件（如.ibd 文件），日志文件等

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1737291249850-7eedbd08-d477-4f27-a309-cbe6d20d6b42.png)

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1737291391341-cc8bc9e4-bbb3-4292-af4a-60d1e87e2481.png)

+ `socket=/var/lib/mysql/mysql.sock`指定 mysql 服务与客户端通过 Unix 套接字通信的路径



> 💡注意： Unix 套接字是一种本地通信方式（仅适用于同一台主机），通过文件系统中的套接字文件实现进程间通信，比 TCP/IP 更加高效 

+ `log-error=/var/log/mysqld.log`：错误日志的存储路径和文件名  
+ `pid-file=/var/run/mysqld/mysqld.pid`： 存放 MySQL 服务的进程 ID（即 PID） 

![](https://cdn.nlark.com/yuque/0/2025/png/50835397/1737291905612-cc1d4fb2-7e3c-485c-88c1-f3debcfe2511.png) 

# 四、多个配置文件读取顺序
可能 mysql 有多个配置文件，那么最终哪个配置文件生效、哪个配置文件中的配置会最终生效呢？

可以通过以下方式来查看：

```shell
[root@192 testdb]$which mysqld
/usr/sbin/mysqld
[root@192 testdb]$/usr/sbin/mysqld --verbose --help | grep -A 1 'Default options'
Default options are read from the following files in the given order:
/etc/my.cnf /etc/mysql/my.cnf /usr/etc/my.cnf ~/.my.cnf 
```

输出结果很明显了：当 mysql 服务器启动时，会按照顺序从`/etc/my.cnf、/etc/mysql/my.cnf、/usr/etc/my.cnf、~/.my.cnf`读取这些配置文件并合并配置项，如果某个选项在多个文件中定义，最后加载的文件会覆盖之前的设置~

> 💡注意：/usr/sbin/mysqld --verbose --help 是一个很好用的辅助命令，可以看下我的这篇博客：[mysql一个很有用的辅助命令](https://github.com/anxincodeha/anxincode)

> 💡 注意：不同版本的 mysql 有不同的配置，所以在配置某些配置前先去官网查看这些配置是否能用在自己的 mysql 版本上

