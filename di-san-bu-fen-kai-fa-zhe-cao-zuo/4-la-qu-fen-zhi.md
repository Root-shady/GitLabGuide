# 4 拉取分支 {#4-拉取分支}

拉取分支是指取回远程仓库指定分支的变化，并与本地分支合并

### Git命令行方式 {#git命令行方式}

需要使用`git pull`命令。它的完整格式为

```
$ git pull 
<
远程主机名
>
<
远程分支名
>
:
<
本地分支名
>
```

如果远程分支是与当前分支合并，则冒号后面的部分可以省略。

```
$ git pull 
<
远程主机名
>
<
远程分支名
>
```

如果当前分支与远程分支之间存在追踪关系，则本地分支和远程分支都可以省略

```
$ git pull 
<
远程主机名
>
```

如果当前分支只有一个追踪分支，那么主机名也可以省略。

```
$ git push

```

### sourcetree方式（推荐） {#sourcetree方式（推荐）}

#### 场景一 检出分支 {#场景一-检出分支}

检出分支是指，需要拉取的远程分支，本地并没有分支与之存在追踪关系。

示例： 本地有develop、feature1、master三个分支，远程仓库origin有develop、feature3、master三个分支，想要拉取远程的feature3分支  
![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut32.png)只需要在想要拉取的分支上右键——检出，就行了  
![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut33.png)

### 场景二 拉取分支 {#场景二-拉取分支}

这里指，需要拉取的远程分支，本地有与之存在追踪关系的分支。

示例： 本地有develop、feature1、master三个分支，远程仓库origin有develop、feature3、master三个分支，想要拉取远程的master分支![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut32.png)

1. 切换到本地的master分支上，点击“拉取”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut34.png)
2. 点击“确定”就可以了
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut35.png)



