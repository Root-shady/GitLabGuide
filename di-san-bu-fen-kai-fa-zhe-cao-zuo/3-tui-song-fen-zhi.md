# 3 推送分支 {#3-推送分支}

### 怎么查看本机记录的远程仓库 {#怎么查看本机记录的远程仓库}

推送分支是指：把本地仓库的当前分支推送到远程仓库的某一分支上。因此，在推送分支之前，需要确认本机上有远程仓库的信息。在git命令行和sourcetree里都可以查看和修改远程仓库

**Git命令行**

输入`git remote -v`，可以查看远程仓库

```
$ git remote -v
origin git@gitlab.oneitfarm.com:linxingyuan/example.git (fetch)
origin git@gitlab.oneitfarm.com:linxingyuan/example.git (push)

```

上面结果表明：当前只有一台远程主机，叫做origin，它的ssh网址是`git@gitlab.oneitfarm.com:linxingyuan/example.git`

如果没有远程仓库信息的话，则需要用`git remote add`命令来添加远程主机

**soucetree**

请见下图![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut27.png)如果没有远程仓库信息的话，则需要用“仓库”——“项目设置”——“添加”来添加远程主机

### Git 命令行方式 {#git-命令行方式}

git push命令用于将本地分支的更新，推送到远程主机。它的完整格式为

```
$ git push 
<
远程主机名
>
<
本地分支名
>
:
<
远程分支名
>
```

如果省略远程分支名，则表示将本地分支推送与之存在"追踪关系"的远程分支（通常两者同名），如果该远程分支不存在，则会被新建。

```
$ git push 
<
远程主机名
>
<
本地分支名
>
```

如果当前分支与远程分支之间存在追踪关系，则本地分支和远程分支都可以省略。

```
$ git push 
<
远程主机名
>
```

如果当前分支只有一个追踪分支，那么主机名都可以省略。

```
$ git push

```

示例：

1. 首先，输入
   `git branch -a`
   查看本地和远程仓库的所有分支，结果如下
   ```
   $ git branch -a
   develop
   *feature1
   master
   remotes/origin/master

   ```

   表明：本地有develop、feature1、master三个分支，当前分支为feature1；有一个远程仓库origin，origin有一个分支master。
2. 输入
   `git push origin feature1`
   ，把本地feature1分支推送到远程仓库origin里，由于没有指定远程分支名，则会将本地分支推送与之存在"追踪关系"的远程分支（通常两者同名），而远程feature1分支不存在，因此会新建这个分支。
3. 再次输入
   `git branch -a`
   ，查看本地和远程仓库的所有分支，结果如下
   ```
   $ git branch -a
   develop
   *feature1
   master
   remotes/origin/master
   remotes/origin/feature1

   ```

   可以看出，远程仓库新建了一个feature1分支
4. 这时，登入
   `gitlab.oneitfarm.com`
   ，进入项目页面，可以看出，feature1分支已经被推送到远程仓库里了
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut28.png)

### Sourcetree方式（推荐） {#sourcetree方式（推荐）}

1. 点击“推送”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut29.png)
2. 选中需要推送的分支，比如，推送develop分支
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut30.png)
3. 点击“推送”，然后可以在sourcetree左边栏看出，远程仓库origin多了develop分支
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut31.png)



