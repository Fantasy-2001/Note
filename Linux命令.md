# Linux 系统目录结构

![Linux 树状目录结构](D:\Markdown\image\Linux\Linux目录树状图.jpg)

- **/bin**：
  bin 是 Binaries (二进制文件) 的缩写, 这个目录存放着最经常使用的命令。

- **/boot：**
  这里存放的是启动 Linux 时使用的一些核心文件，包括一些连接文件以及镜像文件。

- **/dev ：**
  dev 是 Device(设备) 的缩写, 该目录下存放的是 Linux 的外部设备，在 Linux 中访问设备的方式和访问文件的方式是相同的。

- **/etc：**
  etc 是 Etcetera(等等) 的缩写,这个目录用来存放所有的系统管理所需要的配置文件和子目录。

- **/home**：
  用户的主目录，在 Linux 中，每个用户都有一个自己的目录，一般该目录名是以用户的账号命名的，如上图中的 alice、bob 和 eve。

- **/lib**：
  lib 是 Library(库) 的缩写这个目录里存放着系统最基本的动态连接共享库，其作用类似于 Windows 里的 DLL 文件。几乎所有的应用程序都需要用到这些共享库。

- **/lost+found**：
  这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件。

- **/media**：
  linux 系统会自动识别一些设备，例如U盘、光驱等等，当识别后，Linux 会把识别的设备挂载到这个目录下。

- **/mnt**：
  系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将光驱挂载在 /mnt/ 上，然后进入该目录就可以查看光驱里的内容了。

- **/opt**：
  opt 是 optional(可选) 的缩写，这是给主机额外安装软件所摆放的目录。比如你安装一个ORACLE数据库则就可以放到这个目录下。默认是空的。

- **/proc**：
  proc 是 Processes(进程) 的缩写，/proc 是一种伪文件系统（也即虚拟文件系统），存储的是当前内核运行状态的一系列特殊文件，这个目录是一个虚拟的目录，它是系统内存的映射，我们可以通过直接访问这个目录来获取系统信息。
  这个目录的内容不在硬盘上而是在内存里，我们也可以直接修改里面的某些文件，比如可以通过下面的命令来屏蔽主机的ping命令，使别人无法ping你的机器：

  ```Linux
  echo 1 > /proc/sys/net/ipv4/icmp_echo_ignore_all
  ```

- **/root**：
  该目录为系统管理员，也称作超级权限者的用户主目录。

- **/sbin**：
  s 就是 Super User 的意思，是 Superuser Binaries (超级用户的二进制文件) 的缩写，这里存放的是系统管理员使用的系统管理程序。

- **/selinux**：
   这个目录是 Redhat/CentOS 所特有的目录，Selinux 是一个安全机制，类似于 windows 的防火墙，但是这套机制比较复杂，这个目录就是存放selinux相关的文件的。

- **/srv**：
   该目录存放一些服务启动之后需要提取的数据。

- **/sys**：

  这是 Linux2.6 内核的一个很大的变化。该目录下安装了 2.6 内核中新出现的一个文件系统 sysfs 。

  sysfs 文件系统集成了下面3种文件系统的信息：针对进程信息的 proc 文件系统、针对设备的 devfs 文件系统以及针对伪终端的 devpts 文件系统。

  该文件系统是内核设备树的一个直观反映。

  当一个内核对象被创建的时候，对应的文件和目录也在内核对象子系统中被创建。

- **/tmp**：
  tmp 是 temporary(临时) 的缩写这个目录是用来存放一些临时文件的。

- **/usr**：
   usr 是 unix shared resources(共享资源) 的缩写，这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于 windows 下的 program files 目录。

- **/usr/bin：**
  系统用户使用的应用程序。

- **/usr/sbin：**
  超级用户使用的比较高级的管理程序和系统守护程序。

- **/usr/src：**
  内核源代码默认的放置目录。

- **/var**：
  var 是 variable(变量) 的缩写，这个目录中存放着在不断扩充着的东西，我们习惯将那些经常被修改的目录放在这个目录下。包括各种日志文件。

- **/run**：
  是一个临时文件系统，存储系统启动以来的信息。当系统重启时，这个目录下的文件应该被删掉或清除。如果你的系统上有 /var/run 目录，应该让它指向 run。



# 实用指令



## 指定运行级别

**<u>0</u>** ：关机

**<u>1</u>** ：单用户【找回丢失密码】

**<u>2</u> **：多用户状态没有网络服务

**<u>3</u> **：多用户状态有网络服务

**<u>4</u> **：系统未使用保留给用户

**<u>5</u>** ：图形界面

**<u>6</u>** ：系统重启



## 编辑

### vi 和 vim 常用的三种模式

**正常模式**

​	可以使用【上下左右】来移动光标，可以【删除字符】或【删除整行】，也可以【复制、粘贴】来处理你的文件数据

**插入模式**

​	按下【i , I , o , O , a , A , r , R】等任意一个字符进入该模式

**命令行模式**

​	可以提供相关指令：完成读取、存盘、替换、离开 vi 或 vim 、显示行号等动作

```Linux
vi file
vim file
//当有该文件时打开并进入正常模式
//当该文件不存在时则会创建
```



### vi 和 vim 快捷键

<u>**部分命令需要在正常模式下输入**</u>

1. 拷贝当前行 **yy**（ **5yy** 拷贝当前行向下的5行）
2. 删除当前行 **dd**（ **5dd** 删除当前行向下的5行）
3. 查找文件中某个单词 【**命令行下 <u>/</u>关键字**，回车查找，输入 **n** 查找下一个】
4. 设置文件的行号和取消【**命令行下 <u>:set nu</u> 和 <u>:set nonu</u>**】
5. 文档最末行与最首行【最末行 **G** ，最首行 **gg** 】
6. 撤回【 **u** 】
7. 选择跳到该行【输入行号 20 ，在输入 <kbd>shift</kbd> + <kbd>g</kbd>】光标移动至20行



## 关机&重启命令

```Linux
shutdown -h now		//立刻进行关机
shudown -h 1		//"hello，1分钟后会关机了"
shutdown -r now		//现在重新启动计算机
halt				//关机，作用和上面一样
reboot				//现在重新启动计算机
sync				//把内存的数据同步到磁盘
/*
1、不管重启系统还是关闭系统，首先要执行 sync 命令，把内存中的数据写入磁盘中
2、目前 shutdown/reboot/halt 等命令都在关机前执行了 sync 。但还是建议手动保存一遍
*/
```



## 用户登录和注销

```Linux
su - username		//切换用户
logout		//注销用户
exit		//登出
/*
logout 在图形运行级别无效，在运行级别 3 下有效
*/
```



## 用户管理

### 添加用户

```Linux
useradd 用户名
useradd -d 指定目录 新的用户名	//指定目录
useradd -g 用户组 用户名		//将新增用户添加到一个组中
```



### 指定/修改密码

```Linux
passwd 用户名
```



### 当前用户所在目录

```Linux
pwd
```



### 删除用户

```Linux
userdel 用户名		//删除用户但保留家目录
userdel -r 用户名	//删除用户以及主目录
```



### 查询用户信息指令

```Linux
id 用户名
```



### 查看当前用户/登录用户

```Linux
whoami/who am I
```



## 用户组

### 新增组

```Linux
groupadd 组名
```



### 删除组

```Linux
groupdel 组名
```



### 修改用户的组

```Linux
usermod -g 用户组 用户名
```





## 用户和组相关文件

### /etc/passwd

每行的含义：**用户名:口令:用户标识号:组标识号:注释性描述:主目录:登录shell**

### /etc/shadow

每行的含义：**登录名:加密口令:最后一次修改时间:最小时间间隔:最大时间间隔:警告时间:不活动时间:失效时间:标志**

### /etc/group

每行的含义：**组名:口令:组标识号:组内用户列表**



## 帮助指令

### man 获得帮助信息

```Linux
man [命令或配置文件]		//获得帮助信息
```



### help 指令

```Linux
help 命令		//获得shell内置命令的帮助信息
```



## 文件目录类

### pwd 指令

```Linux
pwd			//显示当前工作目录的绝对路径
```



### ls 指令

```Linux
ls [选项] [目录或是文件]
```



### cd 指令

```Linux
cd [参数]			//切换到指定目录

/*
cd ~ 或者 cd :	//回到自己的家目录
cd ..			//回到当前目录的上一级目录
*/
```



### mkdir 指令

```Linux
mkdir [选项] 要创建的目录

/*
-p ：创建多级目录
*/
```



### rmdir 指令

```Linux
rmdir [选项] 要删除的空目录

/*
如果目录下有内容无法删除
删除非空目录，使用 rm -rf 要删除的目录 
*/
```



### touch 指令

```Linux
touch 文件名称		//创建空文件
```



### cp 指令

```Linux
cp [选项] source dest

/*
source ：拷贝的文件
dest ：指定路径
-r ：递归复制整个文件夹
强制覆盖不提示的方法：\cp
*/
```



### rm 指令

```Linux
rm [选项] 要删除的文件或目录

/*
-r ：递归删除整个文件夹
-f ：强制删除不提示
*/
```



### mv 指令

```Linux
mv oldNameFile newNameFile		//重命名
mv /temp/movefile /targetFolder	//移动文件
```



### cat 指令

```Linux
cat [选项] 要查看的文件			//查看文件

/*
-n ：显示行号
*/
```



### more 指令

```Linux
more 要查看的文件

/*
more 是一个基于 vi 编辑器的文本过滤器，它以全屏的方式按页显示文本文件的内容，
该指令中内置了若干快捷键（交互指令）详细操作如下
*/
```

| 操作     | 功能说明                              |
| -------- | ------------------------------------- |
| 空白键   | 代表向下翻一页                        |
| Enter    | 代表向下翻【一行】                    |
| q        | 代表立刻离开 more，不再显示该文件内容 |
| Ctrl + F | 向下滚动一屏                          |
| Ctrl + B | 返回上一屏                            |
| =[       | 输出当前行的行号                      |
| :f       | 输出文件名和当前行的行号              |



### less 指令

```Linux
less 要查看的文件

/*
用来分屏查看文件内容，它的功能与 more 指令类似，但更强大，支持各种显示终端。
该指令显示文件内容时，并不是一次将整个文件加载之后才显示，是根据显示需要加载内容，
对于显示大型文件具有较高的效率。
*/
```

| 操作       | 功能说明                                             |
| ---------- | ---------------------------------------------------- |
| 空白键     | 向下翻动一页                                         |
| [pagedown] | 向下翻动一页                                         |
| [pageup]   | 向上翻动一页                                         |
| /字串      | 向下搜寻【字串】的功能；n ：向下查找；N ：向上查找； |
| ？字串     | 向上搜寻【字串】的功能；n ：向上查找；N ：向下查找   |
| q          | 离开 less 这个程序                                   |



### echo 指令

```Linux
echo [选项] [输出内容]		//输出内容到控制台
```



### head 指令

```Linux
head 文件			//查看文件头10行内容
head -n 5 文件		//查看文件头5行内容，5可以是任意行数

/*
head用于显示文件的开头部分内容，默认情况下head指令显示文件的前10行内容
*/
```



### tail 指令

```Linux
tail 文件				//查看文件尾10行内容
tail -n 5 文件		//查看文件尾5行内容，5可以是任意行数
tail -f 文件			//实时追踪该文件的所有更新

/*
tail 用于输出文件中尾部的内容，默认情况下 tail 指令显示文件的后10行内容
*/
```



### > 指令和 >> 指令

  ```Linux
  > 输出重定向
  >> 追加
  
  //例子：
  ls -l > 文件				//列表的内容写入文件中（覆盖写）
  ls -al >> 文件			//列表的内容追加到文件的末尾
  cat 文件1 > 文件2			//文件1的内容覆盖文件2
  echo "内容" >> 文件
  ```



### ln 指令 

```Linux
ln -s [原文件或目录] [软链接名]		//给原文件创建一个软链接

/*
软链接也称为符号链接，类似于 Windows 里的快捷方式，主要存放了链接其他文件的路径。
当使用 pwd 指令查看目录时，仍然看到的是软链接所在目录
删除使用 rm 指令就好了
*/
```



### history 指令

```Linux
history			//查看已经执行过历史命令
history 10		//显示最近使用过的10个指令
!5				//执行历史编号为5的指令

/*
查看已经执行过历史命令，也可以执行历史命令
*/
```





## 时间日期类

### data 指令-显示当前日期

```Linux
date			//显示当前时间
date + %Y		//显示当前年份
date + %m		//显示当前月份
date + %d		//显示当前是哪一天
date "+%Y-%m-%d %H:%M:%S"		//显示年月日时分秒
```



### data 指令-设置日期

```Linux
date -s 字符串时间

//例子：
date -s "2021-12-13 20:53:53"
```



### cal 指令

```Linux
cal [选项]		//不加选项，显示本月日历

//例子：
cal 2020		//显示2020年日历
```





## 搜索查找类

### find 指令

```Linux
find [搜索范围] [选项]

//例子：
find /home -name hello.txt		//按文件按名查询
find /opt -user root			//按用户名查询
find / -size +200M		//查找 / 下查找大于200M的文件（+n大于 -n小于 n等于）
//单位除了 M 还有 k，M，G

/*
将从指定目录向下递归地遍历其各个子目录，将满足条件的文件或者目录显示再终端
*/
```

| 选项            | 功能                             |
| --------------- | -------------------------------- |
| -name<查询方式> | 按照指定的文件名查找模式查找文件 |
| -user<用户名>   | 查找属于指定用户名所有文件       |
| -size<文件大小> | 按照指定的文件大小查找文件       |



### locate 指令

```Linux
locate 搜索文件

//例子：
updatedb
locate hello.txt

/*
locate 指令可以快速定位文件路径。locate指令利用事先建立的系统中所有文件名称及路径
的locate数据库实现快速定位给定的文件。locate 指令无需遍历整个文件系统，查询速度较快。
为了保证查询结果的准确度，管理员必须定期更新 locate 时刻

 注意：
由于 locate 指令基于数据库进行查询，所以第一次运行前，必须使用 updatedb 指令创建
locate数据库
*/
```



### which指令

```Linux
which 命令

/*
可以查看某个指令在哪个目录下，比如 ls 指令在哪个目录
*/
```



### grep指令和管道符号

```Linux
grep [选项] 查找内容 源文件
命令 | 命令		//管道符号：表示将前一个命令的处理结果输出传递给后面的命令处理

//例子：
grep -n "yes" /home/hello.txt		//在hello.txt文件中，查找 "yes" 所在行
cat /home/hello.txt | grep "yes"	//在hello.txt文件中，查找 "yes" 所在行

/*
grep 过滤查找
grep 命令是一种强大的文本搜索工具
*/
```



| 选项 | 功能             |
| ---- | ---------------- |
| -n   | 显示匹配行及行号 |
| -i   | 忽略字母大小写   |



## 压缩和解压类

### gzip/gunzip 指令

```Linux
gzip 文件			//压缩文件，只能将文件压缩为*.gz文件
gunzip 文件.gz	//解压缩文件命令
```

 

### zip/unzip 指令

```Linux
zip [选项] XXX.zip 将要压缩的内容	//压缩文件和目录的命令
unzip [选项] XXX.zip				//解压缩文件

/*
zip常用选项
-r ：递归压缩，即压缩目录

unzip
-d <目录> ：指定解压后文件的存放目录
*/
```



### tar 指令

```Linux
tar [选项] XXX.tar.gz 打包的内容		//打包目录，压缩后的文件格式.tar.gz

//例子：
tar -zcvf pc.tar.gz /home/pig.txt /home/cat.txt		//将两个文件打包压缩
tar -zcvf myhome.tar.gz /home/			//打包压缩 home 目录下的所有文件
tar -zxvf pc.tar.gz						//解压
tar -zxvf /home/myhome.tar.gz -C /opt/tmp2			//解压到指定目录

/*
tar 指令 是打包指令，最后打包后的文件是 .tar.gz 的文件
*/
```

| 选项 | 功能               |
| ---- | ------------------ |
| -c   | 产生 .tar 打包文件 |
| -v   | 显示详细信息       |
| -f   | 指定压缩后的文件名 |
| -z   | 打包同时压缩       |
| -x   | 解包 .tar 文件     |

 

## 组

1. 所有者
2. 所在组
3. 其它组
4. 改变用户所在的组



### 查看与修改文件的所有者

```Linux
ls -ahl			//查看文件的所有者
chown 用户名 文件名		//修改文件的所有者
chown newowner 文件/目录 	//改变所有者
chown newowner:newgroup 文件/目录 	//改变所有者和所在组
chgrp newgroup 文件/目录		//改变所在组
-R 如果是目录 则使其下所有子文件或目录递归生效
```



### 修改文件所在的组

```Linux
chgrp 组名 文件名
```



### 修改用户所在的组

```Linux
usermod -g 组名 用户名
usermod -d 目录名 用户名 改变该用户登录的初始目录
```



### 权限

```Linux
-rwxrw-r--

/*
1. 第0位确认文件类型（d,-,l,c,b）
	l 是链接，相当于windows的快捷方式
	d 是目录，相当于windows的文件夹
	c 是字符设备文件，鼠标，键盘
	b 是块设备，比如硬盘
2. 第1-3位确定所有者（该文件的所有者）拥有该文件的权限。---User
3. 第4-6位确定所属者（同用户组的）拥有该文件的权限，---Group
4. 第7-9位确定其他用户拥有该文件的权限 ---Other

[r]：可读，ls查看目录内容
[w]：可写，对目录内创建+删除+重命名目录
[x]：可执行，可以进入该目录
*/
```

 

### 修改权限

```Linux
chmod

/*
u：所有者 g：所有组 o：所有人 a：所有人（u、g、o的总和）
chmod u=rwx,g=rx,o=x 文件/目录名		//赋予权限
chmod o+w 文件/目录名				//添加权限
chmod a-x 文件/目录名				//删除权限
chmod 751						//r=4，w=2，x=1
*/
```



## crond && at 任务调度

任务调度：是指系统在某个时间执行的特定的命令或程序。



### crond 使用

```Linux
crontab [选项]

/*
-e：编辑 crontab 定时任务
-l：查询 crontab 任务
-r：删除当前用户所有的 crontab 任务
*/

//例子：
crontab -e
//回车后会进入 vi 编辑如下
*/1 * * * * ls -l /etc/ > /tmp/to.txt	//每分钟往to.txt中重定向 ls -l

conrtab -r		//终止任务调度
conrtab -l		//列出当前有那些任务调度
service crond restart		//重启任务调度
```

| 项目       | 含义                 | 范围                    |
| ---------- | -------------------- | :---------------------- |
| 第一个 "*" | 一小时当中的第几分钟 | 0-59                    |
| 第二个 "*" | 一天当中的第几小时   | 0-23                    |
| 第三个 "*" | 一个月当中的第几天   | 1-31                    |
| 第四个 "*" | 一年当中的第几月     | 1-12                    |
| 第五个 "*" | 一周当中的星期几     | 0-7（0和7都代表星期日） |

| 特殊符号 | 含义                                                         |
| -------- | ------------------------------------------------------------ |
| *        | 代表任何时间，比如第一个 "*" 就代表一小时中每分钟都执行一次的意思 |
| ，       | 代表不连续的时间。比如 ”0，8，12，16 * * * “，就代表在每天的8点，12点，16点都执行一次命令 |
| -        | 代表连续的时间范围。比如 “0 5 * * 1-6 ”，代表在周一到周六的凌晨5点执行命令 |
| */n      | 代表每隔多久执行一次。“*/10 * * * * ”，代表每隔10分钟就执行一遍命令 |



### at定时任务

基本介绍

1. at 命令一次性定时计划任务，at的守护进程 atd 会以后台模式运行，检查作业队列来运行。
2. 默认情况下，atd 守护进程每60秒检查作业队列，有作业时，会检查作业运行时间，如果时间与当前时间匹配，则运行作业。
3. at 命令是一次性定时计划任务，执行完一个任务后不再执行此任务了
4. 在使用at命令的时候，一定要保证atd进程的启动，可以使用相关指令来查看

```Linux
at [选项] [时间]
//Ctrl + D 结束at命令的输入，输入两次 
//ps -ef | grep atd			//使用命令查看进程，管道命令+过滤 grep atd 
//atq查看系统中没有执行的工作任务
//atrm 4 表示将job队列，编号为4的job删除

//时间定义
/*
1. hh:mm（小时：分钟），如果时间已经过去则第二天执行
2. midnight（深夜），noon（中午），teatime（一般是下午4点）
3. AM（上午）、PM（下午）
4. month day（月 日）或 mm/dd/yy（月/日/年）
或 dd.mm.yy（年.月.日）指定日期必须在指定时间后面
5. now + count time-units, now 就是当前时间，time-units是时间单位，能够是minutes（分钟）、hours（小时）、days（天）、weeks（星期）。count是时间数量，几天
，几小时。例如：now + 5 minutes
6. 直接使用today（今天）、tomorrow（明天）来指定完成命令的时间
*/
```

| 选项         | 含义                                                     |
| ------------ | -------------------------------------------------------- |
| -m           | 当指定的任务被完成后，将给用户发送邮件，即使没有标准输出 |
| -I           | atq的别名                                                |
| -d           | atrm的别名                                               |
| -v           | 显示任务将被执行的时间                                   |
| -c           | 打印任务的内容到标准输出                                 |
| -V           | 显示版本信息                                             |
| -q <队列>    | 使用指定的队列                                           |
| -f <文件>    | 从指定文件读入任务而不是从标准输入读入                   |
| -t<时间参数> | 以时间参数的形式提交要运行的任务                         |



## 磁盘分区机制（挂载）

1. Linux无论有几个分区，分给哪一目录使用，它都只有一个根目录，一个唯一且独立的文件结构，Linux每个分区都是组成整个文件系统的一部分
2. Linux采用了一种叫”载入“的处理方法，它的整个文件系统中包含了一整套的文件和目录，且将一个分区和一个目录联系起来。这时要载入的一个分区将使它的存储空间在一个目录下获得。
3. Linux硬盘分**IDE硬盘**和**SCSI硬盘**，目前基本上是SCSI硬盘，
   1. 对于**IDE硬盘**，驱动表示符为”hdx~“，其中”hd“表明分区所在设备的类型，这里是指IDE硬盘。**”x“**为盘号（a为基本盘，b为基本从属盘，c为辅助主盘，d为辅助从属盘），”波浪线“代表分区，前四个分区用数字1到4表示，它们是主分区或拓展分区，从5开始就是逻辑分区。例，hda3表示为第一个IDE硬盘上的第三个主分区或拓展分区，hdb2表示为第二个IDE硬盘上的第二个主分区或扩展分区。
   2. 对于**SCSI硬盘**则标识为”sdx~“，SCSI硬盘是用”sd“表示分区所在设备的设备的类型的，其余则和IDE硬盘表示方法一样



```Linux
lsblk 		//查看分区
lsblk -f		//详细分区
```



### 分区命令

```Linux
fdisk /dev/sdb		//分区命令

/*
m 显示命令列表
p 显示磁盘分区 同 fdisk -l
n 新增分区
d 删除分区
w 写入并退出
说明：开始分区后输入n，新增分区，然后选择p，分区类型为主分区。两次回车默认剩余全部空间。
最后输入w写入分区并退出，若不保存退出输入q。
*/

//分区后还需格式化
mkfs -t ext4 /dev/sdb1		//ext4是分区类型
```



### 挂载

```Linux
//挂载：将一个分区与一个目录联系起来
mount 设备名称 挂载目录
//例子：
mount /dev/sdb1 /newdisk

//取消挂载
umount 设备名称 或者 挂载目录
//例子：
umount /dev/sdb1 或者 nmount /newdisk

/*
注意：使用命令行的方式挂载重启会失效
永久挂载：通过修改/etc/fstab实现挂载
例子：
UUID=a.....		  /				  ext4 		defaults     1 1
/dev/sdb1         /newdisk        ext4      defaults     0 0  //新增
*/
```



### 磁盘情况查询

```Linux
df -h			//查询系统整体磁盘使用情况

/*
查询指定目录的磁盘占用情况，默认为当前目录
-s 指定目录占用大小汇总
-h 带计量单位
-a 含文件
--max-depth=1 子目录深度
-c 列出明细的同时，增加汇总值
*/
```



### 磁盘情况-工作使用指令

```Linux
1.统计/opt文件夹下文件的个数
ls -l /opt | grep "^-" | wc -l	//使用过滤找到 - 开头的文件用 wc 统计数量
2.统计/opt文件夹下目录的个数
ls -l /opt | grep "^d" | wc -l	//使用过滤找到 - 开头的目录用 wc 统计数量
3.统计/opt文件夹下文件的个数，包括子文件夹里的
ls -lR /opt | grep "^-" | wc -l	//使用过滤找到-开头的文件用wc统计数量R递归显示
4.统计/opt文件夹下目录的个数，包括子文件夹里的
ls -lR /opt | grep "^d" | wc -l	//使用过滤找到-开头的目录用wc统计数量R递归显示
5.以树状显示目录结构
tree 目录		//如果没有该该指令，使用 yum install tree 安装
```



## 网络配置

### 网络连接的三种模式

**桥接模式：**与物理在同一个网段下，但会占用一个ip，当ip不够分配时会造成ip冲突

**NAT：**会生成一个虚拟网卡，虚拟机的ip与虚拟网卡的ip互通，虚拟网卡通过物理机ip连接外网，不造成ip冲突**（推荐使用）**

**主机模式：**独立系统，不和外界发生联系

### ifconfig

```Linux
ifconfig		//查看网络配置
```



### ping

```Linux
ping 目的主机		//测试当前服务器是否可以连接目的主机
```



### 指定ip

```Linux
vi /etc/sysconfig/network-scripts/ifcfg-ens33 //ens33是网卡使用ifconfig查看

/*
DEVICE=eth0
HWADDR=00:0C:2x:6x:0x:xx
TYPE=Ethernet
UUID=926a57ba-92c6-4231-bacb-f27e5e6a9f44
ONBOOT=yes				#no 改 yes
#IP的配置方法[none|static|bootp|dhcp](引导时不使用协议|静态分配IP|BOOTP协议|DHCP协议)
//复制如下
BOOTPROTO=static		//该参数一般会存在，存在修改成static就好了
#IP地址
IPADDR=192.168.200.130		//复制修改需要的ip
#子网掩码
NETMASK=255.255.255.0
#网关
GATEWAY=192.168.200.2		//复制修改
#域名解析器
DNS1=192.168.200.2			//复制修改
*/

//NAT模式下还需要再VM下修改虚拟网络编辑器ip使其与虚拟机在一个网段下

//配置后重启网络服务或者重启系统生效
service network restart		||		reboot
//CentOS 8 重启网卡
nmcli c reload ens33


ifconfig eth0 192.168.4.1 netmask 255.255.255.0 up
```



### hostname 设置主机名 && 修改主机名

```Linux
hostname		//查看主机名

vi /etc/hostname		//进入文件修改主机名
reboot					//修改后重启系统
```



### 设置hosts映射

```Linux
ping 主机名	//需要通过主机名映射ip，才可ping通

//windows：
在C:\Windows\System32\drivers\etc\hosts 文件指定即可
例子：192.168.200.130 hspedu100

//Linux
在 /etc/hosts 文件 指定
例子：192.168.200.1 ThinkPad-PC
```



### 主机名解析过程分析

```Linux
Hosts是一个文本文件，用来记录 IP 和 Hostname（主机名）的映射关系
1. DNS，Domain Nmae System的缩写，翻译过来是域名系统
2. 是互联网上作为域名和 IP 地址相互映射的分布式数据库

//查找顺序
1. 浏览器缓存中是否存在该域名的解析IP地址
2. 电脑第一次成功访问某一网站后，在一定时间内浏览器和系统会缓存IP地址（DNS解析记录）。这两个缓存可以理解为本地解析器缓存
windowns：
ipconfig /displaydns	//DNS域名解析缓存
ipconfig /flushdns		//手动清理DNS缓存
3. 如果本地解析器缓存没有找到对应映射，则检查hosts文件中有没有配置对应的域名IP映射
4. 如果 本地DNS解析器缓存 和 host文件都没有，则到域名服务DNS进行解析域名
```



## 进程管理

在Linux中，每个执行的程序都称为一个进程。每一个进程都分配一个ID号（pid，进程号）



### ps 显示系统指定的进程

```Linux
ps [选项]
-a：显示当前终端的所有进程信息
-u：以用户的格式显示进程信息
-x：显示后台进程运行的参数

/*
PID		进程识别号
TTY		终端机号
TIME	此进程所消 CPU 时间
CMD		正在执行的命令或进程名
*/

USER：用户名称
PID：进程号
%CPU：进程占用CPU的百分比
%MEM：进程占用物理内存的百分比
VSZ：进程占用的虚拟内存大小（单位：KB）
RSS：进程占用的物理内存大小（单位：KB）
TT：终端名称，缩写
STAT：进程状态，其中S-睡眠，s-表示该进程是会话的先导进程，N-表示进程拥有比普通优先级更低的优先级，R-正在运行，D-短期等待，Z-僵死进程，T-被追踪或者被停止等等
STARTED：进程的启动时间
TIME：CPU时间，即进程使用CPU的总时间
COMMAND：启动进程所有的命令和参数，如果过长会被截断显示
```



### 父子进程

父进程：可以创建多个子进程，多线程，如果关闭了父线程子线程也会被杀掉

```Linux
ps -ef		//全格式显示当前所有的进程
-e 显示所有进程。  -f 全格式

/*
UID：用户ID
PID：进程ID
PPID：父进程ID
C：CPU用于计算机执行优先级的因子，数值越大，表明进程是CPU密集型运算，执行优先级会降低；
数值越小，表明进程是I/O密集型运算，执行优先级会提高
STIME：进程启动的时间
TTY：完整的终端名称
TIME：CPU时间
CMD：启动进程所用的命令和参数
*/
```



### 终止进程 kill 和 killall

```Linux
kill [选项] 进程号（功能描述：通过进程号杀死进程）
killall 进程名称（功能描述：通过进程名称杀死进程，也支持通配符，这在系统因负载过大而变得很慢时很有用）

/*
-9：表示强迫进程立即停止
*/
```



### 查看进程树 pstree

```Linux
pstree [选项] 	//可以更加直观的来看进程信息

/*
-p：显示进程的PID
-u：显示进程的所属用户
*/
```



## 服务管理

服务（service）本质就是进程，但是是运行在后台的，通常都会监听某个端口，等待其他程序的请求，比如（mysqld，sshd 防火墙等），因此我们又称为守护进程

### service管理指令 

```Linux
service 服务名[start | stop | restart | reload | status]
setup		//可以查看所有的服务

/*
在CentOS7后 很多服务不再使用service，而是 systemctl
service 指令管理的服务在 /etc/init.d 查看
*/
```

#### 开机流程 && 运行级别设置

**开机** -> **BIOS** -> **/boot** -> **systemd进程1** -> **运行级别** -> **运行级对应的服务**

```Linux
multi-user.target:analogous to runlevel 3		//多用户级别
graphical.target:analogous to runlevel 5		//图形化界面级别

/*
systemctl get-default		//查看当前级别
systemctl set-default TARGET.target		//设置级别

设置好后需要重启系统，每次启动时就会进入设置的运行级别
*/
```



### chkconfig 指令运行级别

通过 chkconfig 命令可以给服务的各个运行级别设置自 启动/关闭

```Linux
chkconfig --list [|grep xxx]
chkconfig 服务名 --list
chkconfig --level 5 服务名 on/off
```



### systemctl 管理指令

```Linux
systemctl [start | stop | restart | status] 服务名
systemctl list-unit-files [| grep 服务名]（查看服务开机启动状态grep可以进行过滤）
systemctl enable 服务名 （设置服务开机启动，在3和5的运行级别）
systemctl disable 服务名（关闭服务开机启动，在3和5的运行级别）
systemctl is-enabled 服务名（查询某个服务是否是自启动的）

/*
systemctl 指令管理的服务在 /usr/lib/systemd/system 查看
*/
```



### firewall指令

```Linux
firewall-cmd --permanent --add-port=端口号/协议		//打开端口
firewall-cmd --permanent --remove-port=端口号/协议		//关闭端口
firewall-cmd --reload								//重新载入，才能生效
firewall-cmd --query-port=端口/协议					//查询端口是否开放
```



## 动态监控进程 top

top 与 ps 命令很相似，都是用来显示正在进行的进程。top 与 ps 最大的不同是，top在执行一段时间内可以更新正在运行的进程。

```Linux
top [选项]
```

| 选项    | 功能                                       |
| ------- | ------------------------------------------ |
| -d 秒数 | 制定top命令每隔几秒更新。默认是3秒         |
| -i      | 使top不显示任何闲置或者僵死进程            |
| -p      | 通过制定监控进程ID来仅仅监控某个进程的转态 |



### 交互操作

| 操作 | 功能                          |
| ---- | ----------------------------- |
| P    | 以CPU使用率排序，默认就是此项 |
| M    | 以内存的使用率排序            |
| N    | 以PID排序                     |
| q    | 退出top                       |

监控指定用户：输入u回车，在输入用户名

终止指定进程：输入k回车，再输入要结束的制定进程ID号，再输入9强制删除



## 监控网络状态 netstat

```Linux
netstat [选项]

/*
-an 按一定顺序排列输出
-p 显示哪个进程在调用
*/
```



## rpm 与 yum

rpm用户互联网下载包的打包及安装工具，它包含在某些Linux分发版中。它生成具有.RPM扩展名的文件。RPM是RedHat Package Manager（RedHat软件包管理工具）的缩写，类似Windows的setup.exe，这一文件格式名称虽然打上了RedHat的标志，但理念是通用的。可以算公认的行业标准。



### 查看 rpm 包

```Linux
rpm -qa | grep xxx		//查询已安装的rpm列表
rpm -q 软件包名			//查询软件包是否安装，例如：rpm -q firefox
rpm -qi 软件包名		//查询软件包信息，例如：rpm -q firefox
rpm -ql 软件包名		//查询软件包中的文件
rpm -qf 文件全路径名		//查询文件所属的软件包

/* rpm包名基本格式
firefox-60.2.2-1.el.centos.x86_64
名称：firefox
版本号：60.2.2-1
适用操作系统：el7.centos.x86_64
表示centos7.x的64位系统
如果是i686、i386表示32位系统，noarch表示通用
*/
```



### 卸载 rpm 包

```Linux
rpm -e rpm包的名称			//删除firefox 软件包
//如果其他软件包依赖于你要卸载的软件包，卸载时会产生错误信息
rpm -e --nodeps 包名		//强制删除，一般不推荐
```



### 安装 rpm 包

```Linux
rpm -ivh RPM包全路径名称

/*
i = install 安装
v = verbose 提示
h = hash 进度条
*/
```



### yum

yum 是一个 Shell 前端软件包管理器。基于RPM包管理，能够从指定的服务器自动下载 RPM包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软件包。

```Linux
yum list | grep xxx			//查询yum服务器是否有需要安装的软件
yum info xxx	//显示指定的rpm包的详细信息，这个包可以是安装过的或是没有安装过的，list是概要信息
yum install xxx				//安装指定的yum包
yum remove xxx				//移除，不会移除掉依赖组件
yum update xxx				//更新

yum clean all		#清除缓存
yum makecache		#重新生成缓存
yum repolist all	#查看所有仓库
```



### CentOS 8 使用本地源

```Linux
mount /dev/cdrom /media/		#挂载
cd /etc/yum.repos.d/			
mkdir ./back					#在该目录下创建文件夹
mv *.repo ./back				#将所有扩展名 .repo 移动到 back目录下
cp back/CentOS-Linux-Media.repo ./		#将...Media.repo 复制到该目录下

/* 修改如下
enable=0,全都修改成1
file:///media/CentOS/BaseOS			修改后：file:///media/BaseOS
file:///media/CentOS/AppStream		修改后：file:///media/AppStream
*/
```



### CentOS 8 网络源配置

```Linux
mount /dev/cdrom /media/		#挂载
cd /etc/yum.repos.d/			
mkdir ./back					#在该目录下创建文件夹
mv *.repo ./back				#将所有扩展名 .repo 移动到 back目录下
cp back/CentOS-Linux-BaseOS.repo ./		#将...Media.repo 复制到该目录下

/*修改如下
然后编辑 /etc/yum.repos.d/ 中的相应文件，在 mirrorlist= 开头行前面加 # 注释掉；并将 baseurl= 开头行取消注释（如果被注释的话），把该行内的域名（例如mirror.centos.org）替换为 mirrors.tuna.tsinghua.edu.cn
注意：如果需要启用其中一些 repo，需要将其中的 enabled=0 改为 enabled=1。
*/
yum makecache		#更新缓存
```





