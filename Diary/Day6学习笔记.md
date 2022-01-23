# Day6学习笔记

## Linux

### 常用发行版

目前市面上较知名的发行版有：Ubuntu、RedHat、CentOS、Debian、Fedora、SuSE、OpenSUSE、Arch Linux、SolusOS 等。

### 文件与目录相关操作

#### 路径

绝对路径：
路径的写法，由根目录 / 写起，例如： /usr/share/doc 这个目录。

相对路径：
路径的写法，不是由 / 写起，例如由 /usr/share/doc 要到 /usr/share/man 底下时，可以写成： cd ../man 这就是相对路径的写法。

#### 常用命令


- ls: 列出目录及文件名
`[root@www ~]# pwd [-P]`
> `-P`：显示出确实的路径，而非使用连结路径。

- cd：切换目录
`cd [相对路径或绝对路径]`

- pwd：显示目前的目录
`[root@www ~]# pwd [-P]`
> `-P`：同样显示出确实的路径，而非使用连结路径。

- mkdir：创建一个新的目录
`mkdir [-mp] 目录名称`
> `-m `：配置文件的权限喔！直接配置，不需要看默认权限
`-p`：帮助你直接将所需要的目录(包含上一级目录)递归创建起来！

- rmdir：删除一个空的目录
` rmdir [-p] 目录名称`
> `-p `：从该目录起，一次删除多级空目录

- cp: 复制文件或目录
`[root@www ~]# cp [-adfilprsu] 来源档(source) 目标档(destination)
[root@www ~]# cp [options] source1 source2 source3 .... directory`

- rm: 删除文件或目录
` rm [-fir] 文件或目录`

- mv: 移动文件与目录，或修改文件与目录的名称
`[root@www ~]# mv [-fiu] source destination
[root@www ~]# mv [options] source1 source2 source3 .... directory`

- man：查看各个命令的使用文档
`man cp`

### 打包与压缩

#### tar

创建一个新的tar文件:
`$ tar cvf archive_name.tar dirname/`

解压tar文件:
`$ tar xvf archive_name.tar`

查看tar文件:
`$ tar tvf archive_name.tar`

#### grip

创建一个*.gz的压缩文件:
`$ gzip test.txt`

解压*.gz文件:
`$ gzip -d test.txt.gz`

显示压缩的比率:
`$ gzip -l *.gz
     compressed        uncompressed  ratio uncompressed_name
          23709               97975  75.8% asp-patch-rpms.txt`

####  bzip2

创建*.bz2压缩文件:
`$ bzip2 test.txt`

解压*.bz2文件:
`bzip2 -d test.txt.bz2`

### vim文本编辑器

基本上 vi/vim 共分为三种模式，分别是**命令模式**，**输入模式**和**底线命令模式**.

#### 实例

1. 使用 vi 来建立一个名为 LHC.txt的文件
`$ vim LHC.txt`
**注意: vi 后面一定要加文件名**

2. 按下 i 进入输入模式(也称为编辑模式)，开始编辑文字
在一般模式之中，只要按下 i, o, a 等字符就可以进入输入模式
在编辑模式当中，在左下角状态栏中会出现 –INSERT- 的字样，那就是可以输入任意字符的提示。
3. 按下 ESC 按钮回到一般模式
4. 在一般模式中输入 :wq 储存后离开 vi

### 用户管理

#### root用户与普通用户

root在linux里面拥有所有的系统权限，可以畅行无阻地修改所有系统文件和其他用户的文件，挂载文件系统等等的一系列操作

普通用户则有很大的限制，例如不能修改系统关键配置文件，想查看其他用户的文件则需要相应的权限，不能安装软件

##### 切换
普通用户切换成root用户
```
su: switch user
su//默认切换成管理员
```
root用户切换成普通用户

`exit`

#### 常用用户命令
`useradd`：添加用户

`adduser`：添加用户

`passwd`：为用户设置密码

`usermod`：修改用户命令，可以通过usermod 来修改登录名、用户的家目录等等；

`pwcov`：同步用户从/etc/passwd 到/etc/shadow

`pwck`：pwck是校验用户配置文件/etc/passwd 和/etc/shadow 文件内容是否合法或完整；

`pwunconv`：是pwcov 的立逆向操作，是从/etc/shadow和 /etc/passwd 创建/etc/passwd ，然后会删除 /etc/shadow 文件；

`finger`：查看用户信息工具

`id`：查看用户的UID、GID及所归属的用户组

`chfn`：更改用户信息工具

`su`：用户切换工具

`sudo`：sudo 是通过另一个用户来执行命令，su 是用来切换用户，然后通过切换到的用户来完成相应的任务，但sudo 能后面直接执行命令，如sudo 不需要root 密码就可以执行root 赋与的执行只有root才能执行相应的命令；但得通过visudo 来编辑/etc/sudoers来实现；

#### 用户与用户组的概念

Linux是一个多用户多任务的分时操作系统。每个用户都用一个唯一的用户名和用户口令，在登录系统时，只有正确输入了用户名和密码，才能进入系统和自己的主目录。
而用户组是具有相同特征用户的逻辑集合，有时我们需要让多个用户具有相同的权限，如查看、修改某一个文件的权限，合理的方法是建立一个组，让这个组具有查看、修改此文件的权限，然后将所有需要访问此文件的用户放入这个组中，那么所有用户就具有了和组一样的权限。这就是用户组，将用户分组是Linux 系统中对用户进行管理及控制访问权限的一种手段，通过定义用户组，在很大程度上简化了管理工作。

### 系统管理

#### 正则表达式

正则表达式描述了一种字符串匹配的模式，可以用来检查一个串是否含有某种子串、将匹配的子串替换或者从某个串中取出符合某个条件的子串等
> (用多种元字符与运算符可以将小的表达式结合在一起来创建更大的表达式)

#### 文本查找

#### grep
用于查找文件里符合条件的字符串
语法：
`grep [-abcEFGhHilLnqrsvVwxy][-A<显示行数>][-B<显示列数>][-C<显示列数>][-d<进行动作>][-e<范本样式>][-f<范本文件>][--help][范本样式][文件或目录...]`

#### find
用来在指定目录下查找文件。任何位于参数之前的字符串都将被视为欲查找的目录名。如果使用该命令时，不设置任何参数，则 find 命令将在当前目录下查找子目录与文件。并且将查找到的子目录和文件全部进行显示。
语法：
`find   path   -option   [   -print ]   [ -exec   -ok   command ]   {} \;`

#### 磁盘管理

磁盘管理常用三个命令为 `df`、`du `和 `fdisk`

df：列出文件系统的整体磁盘使用量
`df [-ahikHTm] [目录或文件名]`

du：检查磁盘空间使用量
`du [-ahskm] 文件或目录名称`

fdisk：用于磁盘分区
`fdisk [-l] 装置名称`
> `-l` ：输出后面接的装置所有的分区内容。若仅有 fdisk -l 时， 则系统将会把整个系统内能够搜寻到的装置的分区均列出来。

## shell

### bash

一个能编写代码的文本编辑器和一个能解释执行的脚本解释器
`#!/bin/bash`告诉系统其后路径所指定的程序即是解释bash脚本文件的 Shell 程序

### 重定向与管道

#### 管道

##### 概念
在Linux中有很多标准的命令例如find、sort等，可以满足我们完成文档管理、系统管理等诸多需求，但是大多时候一些复杂的需求都需要多个命令搭配起来使用，对于Linux来说一个命令对应于一个进程，因此多个命令协同工作，就涉及到多个进程的通信，Linux提供一种管道的方式来完成进程间通信

管道在Linux中对应管道符号：|

`Command1 | Command2 | Command3`

Command1执行的输出作为Command2的输入；同时Command2执行的输出作为Command3的输入

例：

`cat test.sh | grep -n 'echo' #`
读出test.sh文件内容，通过管道转发给grep 作为输入内容，筛选出echo命令输出到屏幕上

#### 重定向

##### 概念
Linux重定向是指修改原来默认的一些东西，对原来系统命令的默认执行方式进行改变，如果说用户不想看到在显示器的输出而是希望输出到某一文件中就可以通过Linux重定向来进行这项工作。

##### 输入重定向

输入重定向符号：<

`CommandA < file #`输入重定向到file

特殊的输入重定向符号：<<

`CommandA <<EOF`


##### 输出重定向

输出重定向符号：>(覆盖)， >> (追加)

`Command > file`

`Command >> file`

##### 文件描述符

系统中默认的文件描述符号：

0 标准输入

1 标准输出

2 标准错误输出

`ls -l > file 2 > /home/test/a.txt # `将输出重定向到file,且将错误输出重定向到/home/test/a.txt中

