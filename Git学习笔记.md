# Git学习笔记

## Git概述

Git 是一个免费的、开源的分布式版本控制系统，可以快速高效地处理从小型到大型的各种

项目。

Git 易于学习，占地面积小，性能极快。 

它具有廉价的本地库，方便的暂存区域和多个工作

流分支等特性。其性能优于 Subversion、CVS、Perforce 和 ClearCase 等版本控制工具。

### **何为版本控制**

版本控制是一种记录文件内容变化，以便将来查阅特定版本修订情况的系统。

版本控制其实最重要的是可以记录文件修改历史记录，从而让用户能够查看历史版本，

方便版本切换

### Git工作机制

![image-20221111231535591](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20221111231535591.png)

## Git基本命令

| 命令名称                             | 作用         |
| ------------------------------------ | ------------ |
| git config --global user.name 用户名 | 设置用户签名 |
| git config --global user.email 邮箱  |              |
| git init                             | 初始化本地库 |
| git status                           |              |
| git add 文件名                       | 添加到暂存区 |
| git commit -m "日志信息" 文件名      | 提交到本地库 |
| git reflog                           |              |
| git reset --hard 版本号              |              |
|                                      |              |

**git config --global user.name 用户名**

**git config --global user.email 邮箱**

说明：

签名的作用是区分不同操作者身份。用户的签名信息在每一个版本的提交信息中能够看

到，以此确认本次提交是谁做的。Git 首次安装必须设置一下用户签名，否则无法提交代码。

**※注意：**这里设置用户签名和将来登录 GitHub（或其他代码托管中心）的账号没有任

何关系

## Git分支

### 什么是分支

在版本控制过程中，同时推进多个任务，为每个任务，我们就可以创建每个任务的单独分支。使用分支意味着程序员可以把自己的工作从开发主线上分离开来，开发自己分支的时候，不会影响主线分支的运行。对于初学者而言，分支可以简单理解为副本，一个分支就是一个单独的副本。（分支底层其实也是指针的引用）

![image-20221111232252208](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20221111232252208.png)

### 分支的好处

同时并行推进多个功能开发，提高开发效率。

各个分支在开发过程中，如果某一个分支开发失败，不会对其他分支有任何影响。失败的分支删除重新开始即可。

### 分支基本操作命令

查看当前分支：**git branch -v**

创建分支：**git branch** 分支名

切换分支：**git checkout 分支名**

合并分支： **git merge 分支名**

### 产生冲突

#### 冲突产生原因？

合并分支时，两个分支在**同一个文件的同一个位置**有两套完全不同的修改。Git 无法替我们决定使用哪一个。必须**人为决定**新代码内容。

查看状态（检测到有文件有两处修改）

#### 解决冲突

编辑有冲突的文件，删除特殊符号，决定要使用的内容

#### 创建分支和切换分支

![image-20221111232809654](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20221111232809654.png)

master、hot-fix 其实都是指向具体版本记录的指针。当前所在的分支，其实是由 HEAD决定的。所以创建分支的本质就是多创建一个指针。

HEAD 如果指向 master，那么我们现在就在 master 分支上。

HEAD 如果执行 hotfix，那么我们现在就在 hotfix 分支上。

### Git团队协作机制

![image-20221111232906876](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20221111232906876.png)

![image-20221111232919516](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20221111232919516.png)

## GitHub操作

查看当前所有远程地址别名：**git remote -v**

起别名：**git remote add 别名 远程地址**

推送本地分支上的内容到远程仓库：**git push 别名 分支 **

将远程仓库的内容克隆到本地：**git clone 远程地址**

将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并：**git pull 远程库地址别名 远程分支名**

