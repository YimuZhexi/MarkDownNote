---
typora-copy-images-to: upload
---

[TOC]

# Git

## 一、Git基础

### 1、Git介绍

​		Git是目前世界上最先进的分布式**版本控制系统**。

### 2、Git与Github

#### 两者区别

​		**Git**是一个分布式版本控制系统，简单的说其就是**一个软件**，用于记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的软件。

​		**Github** (https://www.github.com)是一个为用户提供**Git**服务的网站，**简单说就是一个可以放代码的地方**（不过可以放的当然不仅是代码)。**Github**除了提供管理**Git**的 **web**界面外，还提供了订阅、关注、讨论组、在线编辑器等丰富的功能。**Github**被称之为**全球最大的基友网站**（不是重点的重点。。。）。

### 3、安装Git

​		下载网站(https://git-scm.com/downloads)。

​		过程极多且复杂，但总结下来，一句话：除更改安装路径外直接**疯狂下一步**即可。

​		当出现下面图示内容时安装成功。

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211013235923531.png" alt="image-20211013235923531" style="zoom:80%;" />

## 二、Git的使用

### 1、本地仓库

#### 1.1、工作流程

Git本地操作的**三个区域**：

​		**Git Repository（Git仓库）**：最终确定的文件保存到仓库，成为一个新的版本，并且对他人可见。

​		**暂存区**：暂存已经修改的文件最后统一提交到git仓库中。

​		**Working Directory（工作区）**：添加、编辑、修改文件等动作

**工作流程：**

![网页捕获_14-10-2021_9413_www.bilibili.com](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/%E7%BD%91%E9%A1%B5%E6%8D%95%E8%8E%B7_14-10-2021_9413_www.bilibili.com.jpeg)

​		在工作区对文件进行修改，让后将其放入暂存区，**当所有操作最终确定后，最后保存到Git仓库**。

#### 1.2、本地仓库操作（repository）

**简介**：仓库又名**版本库**，我们可以简单理解成是一个**用于存放代码的目录**，这个目录			里面的所有文件都可以被Git管理起来，**每个文件的修改、删除等操作Git都			能跟踪到**。

##### ①在安装好后**首次使用需要先进行全局配置**

桌面空白处右键，点击“Git Bash Here”以打开Git命令行窗口。

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014092358349.png" alt="image-20211014092358349" style="zoom: 80%;" />

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014092630831.png" alt="image-20211014092630831" style="zoom: 67%;" />

输入以下内容：

```
$ git config --global user.name"用户名”

$ git config --global user.email"邮箱地址”
```

（如下图）

![image-20211014093731881](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014093731881.png)

##### ②创建仓库

当我们需要让 Git去管理某个新项目/已存在项目的时候，就需要创建仓库了。注意，**创建仓库时使用的目录不一定要求是空目录，选择一个非空目录也是可以的**，但是**不建议在现有项目上来学习Git**，否则造成的一切后果概不负责!
注意:为了避免在学习或使用过程中出现各种奇葩问题，请**不要使用包含中文的目录名**(父目录亦是如此)。

###### 创建新目录

```
$ mkdir xxxx(文件名)
```

例如下图：

![image-20211014122500252](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014122500252.png)

或者直接右键新建文件夹：

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014122649893.png" alt="image-20211014122649893" style="zoom: 60%;" />

最终效果：

![image-20211014122804767](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014122804767.png)

###### 进入目录

```
$cd xxxx(文件名)
```

如下图：

![image-20211014130344830](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014130344830.png)

###### Git仓库初始化（让 Git知道，它需要来管理这个目录)

```
$ git init
```

执行后Git会创建git**隐藏目录.git**，**不能删除，不能随意更改**(除非需要)。

效果图

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014132257613.png" alt="image-20211014132257613" style="zoom:80%;" />

进入文件夹，点击查看---勾选隐藏的项目

![image-20211014132437463](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014132437463.png)

##### ③Git常用指令操作

```
查看当前状态: git status		【非必要】

添加到缓存区: git add文件名

提交至版本库: git commit -m“注释内容”
```

git status：

![image-20211014185943253](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014185943253.png)

```添加到缓存区：git add ……
语法1：git add 文件名	（添加一个文件）

语法2：git add 文件名1 文件名2 文件名3 ……	（添加多个文件）

语法3：git add .	（添加当前目录到缓存区中）
```

![image-20211014193111821](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014193111821.png)

（添加reone.txt到git缓存区并用git status查看状态）

```
提交至版本库：git commit -m "注释内容"
```

注释内容可为中文

![image-20211014194014371](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014194014371.png)

（注释效果图）

后续对文件进行操作后，重复使用git add 和git commit -m即可。

#### 1.3、修改文件

##### ①查看文件

```
$  vim 文件名
```

![image-20211014201526095](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014201526095.png)

##### ②修改文件

```
$vim 文件名
```

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014201759799.png" alt="image-20211014201759799" style="zoom: 80%;" />

（进入后按i修改文件，esc退出后“：wq”保存文件）

##### ③再次查看状态

```
$ git status
```

![image-20211014202102905](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014202102905.png)

再次添加到暂存区并上传到版本库并查看版本（$ git reflog）

![image-20211014203157692](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014203157692.png)

#### 1.4、历史版本

##### ①查看历史版本

```
git reflog 查看版本信息
```

![image-20211014203917219](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014203917219.png)

git log查看版本详细信息

 ![image-20211014204005072](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014204005072.png)

##### ②版本穿梭

```
基本语法：git reset --hard
```

查看文件：

![image-20211014222622719](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014222622719.png)

查看历史版本号：

![image-20211014224723220](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014224723220.png)

进入之前的版本：

![image-20211014224758343](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014224758343.png)

再次查看版本号：

![image-20211014224858421](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014224858421.png)

**Git通过调用不同的指针来指向不同版本来起到切换版本作用，而不是简单的复制粘贴。**

#### 1.5、Git的分支操作

![image-20211014232253410](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014232253410.png)

##### ①什么是分支

在版本控制过程中，同时推进多个任务，为每个任务，我们就可以创建每个任务的单独分支。**使用分支意味着程序员可以把自己的工作从开发主线上分离开来，开发自己分支的时候，不会影响主线分支的运行**。对于初学者而言，分支可以简单理解为副本，一个分支就是一个单独的副本。(**分支底层其实也是指针的引用**)。

![image-20211014234430666](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211014234430666.png)

##### ②分支的好处

​		**同时**并行推进**多个功能的开发**，提高开发效率。

​		各分支在开发过程中，如果**某一个分支开发失败，不会对其它分支有任何影响**。失败的分支删除重新开始即可。

##### ③分支的操作

![image-20211015131257848](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211015131257848.png)

###### 查看分支

```
git branch -v
```

![image-20211015131453798](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211015131453798.png)

###### 创建分支

```
git branch 分支名
```

![image-20211015230320015](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211015230320015.png)

查看分支

![image-20211015230617817](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211015230617817.png)

###### 切换分支

```
git checkout 分支名
```

![image-20211015233356743](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211015233356743.png)

在第二分支上修改文件

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211015234718917.png" alt="image-20211015234718917" style="zoom: 67%;" />

###### 合并分支

切换分支并查看当前分支上的文件

![image-20211016105041476](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016105041476.png)

合并分支并查看文件

```
合并语法：$ git merge “被合并分支名”
```

![image-20211016105128918](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016105128918.png)

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016105256126.png" alt="image-20211016105256126" style="zoom:70%;" />

###### 合并冲突

**冲突产生的原因**:
合并分支时，**两个分支在同一个文件的同一个位置有两套完全不同的修改**。Git无法替我们决定使用哪一个。必须人为决定新代码内容。

查看冲突：

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016112558796.png" alt="image-20211016112558796" style="zoom: 80%;" />

###### 解决冲突



查看文件

![image-20211016113012020](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016113012020.png)

<<<<<<< HEAD与= == == ==之间是当前分支修改的内容

![image-20211016113447881](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016113447881.png)

== == ===与>>>>>>>first之间是其它（first）分支修改内容

![image-20211016113559297](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016113559297.png)

修改方法：删除多余符号等内容，保留修改内容，如图：

![image-20211016123840637](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016123840637.png)

再次添加和提交（注意，**提交时不能带文件名！**）

![image-20211016124058995](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016124058995.png)

发现后面出现了下图变化：

![image-20211016124127477](https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016124127477.png)

#### 1.5、创建分支和切换分支图解

<img src="https://raw.githubusercontent.com/YimuZhexi/PicGo/master/img/image-20211016130654481.png" alt="image-20211016130654481" style="zoom: 33%;" />

master、hot-fix其实都是指向具体版本记录的指针。

当前所在的分支，其实是由HEAD决定的。所以创建分支的本质就是多创建一个指针。

HEAD如果指向master，那么我们现在就在master分支上。

HEAD 如果指向其它分支，那么我们现在就在其它分支上。

所以切换分支的本质就是移动HEAD指针。

