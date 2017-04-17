# 分支管理规范 {#0-分支管理规范}

git 的分支管理功能非常强大，而为了提高效率、避免分支混乱，可采用一种规范化管理 git 分支的工具 git flow

### git flow 简介 {#git-flow-简介}

git flow 是规范化使用git branch 的一套方案来管理分支，规范代码流程。

### git flow 初始化 {#git-flow-初始化}

git flow 是管理 git 分支的工具，需要初始化。

#### git 命令行初始化 {#git-命令行初始化}

1. 在项目文件夹里右键——  
   `Git Bash Here`  
   ，打开 git 命令行窗口，输入

   ```
   git flow init
   ```

2. 之后 git 命令行会提示一系列问题让你给分支命名，为了统一应全部选择默认，一路按回车键就行了

#### sourcetree 初始化 {#sourcetree-初始化}

1. 点击“Git工作流”
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut16.png)
2. 弹出的提示框默认即可，点击确定

### git flow 分支规范 {#git-flow-分支规范}

#### 主要分支 {#主要分支}

master分支：永远处在即将发布（production-ready）状态

develop分支：最新的开发状态

#### 辅助分支 {#辅助分支}

feature分支：开发新功能的分支，基于develop，开发完成后merge回develop

release分支：准备要发布版本的分支（测试环境用的），用来修复SIT bug；基于develop分支，完成后merge回develop和master分支

hotfix分支：修复线上（master）紧急bug，等不及release分支就必须马上上线；基于master分支，完成后merge回master和develop分支。

