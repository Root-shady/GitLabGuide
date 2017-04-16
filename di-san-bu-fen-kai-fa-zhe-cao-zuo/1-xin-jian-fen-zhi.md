# 1 新建分支 {#1-新建分支}

### Git 命令行方式 {#git-命令行方式}

新建分支的常用命令如下

```
# 新建一个分支，但依然停留在当前分支
$ git branch [branch-name]

# 新建一个分支，并切换到该分支
$ git checkout -b [branch]

```

### Sourcetree方式（推荐） {#sourcetree方式（推荐）}

1. 点击“分支”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut17.png)
2. 输入分支名，点击“创建分支”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut20.png)
3. 在sourcetree的左侧可以看到所有分支和当前所在分支，如下图所示，当前在 feature1 分支下
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut21.png)

### git flow 规范下新建分支 {#git-flow-规范下新建分支}

1. 点击“Git工作流”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut18.png)
2. 根据分支的作用选择动作，比如，如果新分支的作用是为开发版本添加一个功能，则选择“建立新的功能”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut19.png)
3. 输入名称，点击确定
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut22.png)
4. 结果如下图所示
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut23.png)



