# Git介绍 {#1-git介绍}

### 版本控制

> 版本控制是一种记录若干文件内容变化，以便将来查阅特定版本修订情况的系统。

版本控制的目的是实现开发团队并行开发、提高开发效率的基础。其目的在于对软件开发进程中文件或目录的发展过程提供有效的追踪手段，保证在需要时可回到旧的版本，避免文件的丢失、修改的丢失和相互覆盖，通过对版本库的访问控制避免未经授权的访问和修改，达到有效保护企业软件资产和知识产权的目的。

版本控制的功能在于跟踪记录整个软件的开发过程，包括软件本身和相关文档，以便对不同阶段的软件及相关文档进行表示并进行差别分析，对软件代码进行可撤消的修改，便于汇总不同开发人员所做的修改，辅助协调和管理软件开发团队。

### 分布式vs集中式 {#分布式vs集中式}

> 集中式版本控制：集中存放所有资料，所有变动都更新到中央服务器。同时所有相关人员想要进行相关浏览和修改都需要连接中央服务器。
>
> 分布式版本控制：分布式存放所有资料，客户端并不只提取最新版本的文件快照，而是把原始的代码仓库完整地镜像下来。所以每个人都可以独立进行改动资料，并且所有的改动都是在完整资料信息的环境下进行的。

git和svn分别是分布式和集中式的版本控制软件。

* 在使用svn时，版本库是存放在唯一的中央服务器里的。当在本地进行提交（submit）操作时，svn会将本地修改提交到中央服务器的版本库；而在本地进行更新（up）操作时，会将中央服务器版本库中的最新版本更新到本地。 这种版本控制方式被称为集中式版本控制。
* 在使用git时，git会在每一台机器上建立一个版本库，称为仓库（repository）。在使用git进行新建（init）、提交（commit）、分支（branch）等操作时，都只对本地仓库进行修改。 git是用远程仓库来实现的，通过从远程仓库克隆（clone）、拉取分支（pull），想远程仓库推送分支（push）来实现与其他机器上的仓库进行交流。 一般来说，在团队协作时，会在某台服务器上搭建一个git 服务器，这台服务器行使类似于“中央服务器”的功能。团队中每一个人首先在本地的仓库进行操作，需要的时候，把本地的分支推送到远程仓库里，这样，别人就可以看到了。 这种版本控制方式被称为分布式版本控制。

![](/assets/import.png)

Git 的优点：

* 克服网络依赖性：分布式可以进行本地代码提交。
* 加强数据安全性：分布式备份多份数据，防止中央服务器宕机。
* 速度快、简单设计
* 对非线性开发模式的强力支持（允许上千个并行开发的分支）
* 完全分布式 有能力高效管理类似 Linux 内核一样的超大规模项目（速度和数据量）

### 文件跟踪概念

文件已跟踪或未跟踪：

> 已跟踪的文件是指那些被纳入了版本控制的文件，在上一次快照中有它们的记录，在工作一段时间后，它们的状态可能处于未修改，已修改或已放入暂存区。
>
> 工作目录中除已跟踪文件以外的所有其它文件都属于未跟踪文件，它们既不存在于上次快照的记录中，也没有放入暂存区。

### ![](/assets/filetracking.png) {#暂存区的概念}

###  {#暂存区的概念}

### 暂存区的概念 {#暂存区的概念}

svn中没有暂存区的概念，如果想提交某一个文件，需要用commit命令后面加文件名作为参数  
而git中使用了暂存区：每次执行commit，不需要文件名作为参数，而是直接把暂存区的文件全部提交。因此，在执行commit命令之前，需要先执行add命令，把需要提交的文件存入暂存区。

**引入缓存区的概念，可以保持每一次 commit 的粒度，在完成一个相对独立的功能前，先将相关的代码提交到暂存区中，当完成一个独立的功能模块时，才进行一次commit。**

![](/assets/gitflow.png)

### 分支的概念 {#分支的概念}

假如现在手头上有一个项目的初始化版本，我们在这个版本的基础上新建分支A、分支B。这个时候，分支A和分支B的内容是一样的。这时，我们在分支A下进行修改、提交，分支A迭代了一个版本。这些操作仅仅会影响分支A，而影响不了分支B。因而，每条分支相当于一条独立的版本控制的路。那么，两条分支之间如何进行交流呢？

git是通过合并分支来实现分支之间的交流的。 假设分支A修改了文件1，分支2修改了文件2，这时，我们将分支A合并到分支B上，那么分支B里的文件1会变成分支A修改过的样子。这就是最简单的分支合并。

Git 处理分支的方式可谓是难以置信的轻量，创建新分支这一操作几乎能在瞬间完成，并且在不同分支之间的切换操作也是一样便捷。

在项目实践中，我们通常会有下面的分支：

* Master 主分支：稳定的产品线
* Develop 开发分支：测试环境分支
* Feature 特性分支：相关的子功能模块分支develop 开发分支
* Hotfix 修复 分支：修复相关的Bug分支，用于紧急处理

[https://www.atlassian.com/git/articles/10-years-of-git](https://www.atlassian.com/git/articles/10-years-of-git "［Git 十年发展历史］")

