# 2 修改提交 {#2-修改提交}

修改提交需要以下过程：

1. 将修改的文件加入暂存区
2. 将暂存区的文件提交

需要注意以下两点：

1. 修改提交是基于分支的，即进行提交后，只会对当前分支进行修改
2. 提交后，只会修改本地仓库的当前分支，如果希望把修改同步到远程仓库，则需要把当前分支推送到远程仓库里

### Git 命令行方式 {#git-命令行方式}

这里用一个例子来说明怎么用Git 命令行来进行修改提交。

1. 进入项目文件夹，打开`Git Bash`

2. 首先，使用`git status`命令可以查看当前文件的状态。输入`git status`，得到以下结果

   ```
   $ git status
   On branch feature1
   nothing to commit, working directory clean
   ```

   这里表明：当前在feature1分支下；没有需要提交的文件，指上次提交后文件没有进行过修改。

3. 修改index.php文件，再次查看`git status`，结果如下

   ```
   $ git status
   On branch feature1
   Changes not staged for commit:
        (use "git add 
   <
   file
   >
   ..." to update what will be committed)
        (use "git checkout -- 
   <
   file
   >
   ..." to discard changes in working directory)
            modified: index.php
   no changes added to commit (use "git add" and/or "git commit -a")
   ```

   表明：index.php已经被修改了，但是没有放入暂存区

4. 输入`git add index.php`命令，把index.php放入暂存区，再次查看`git status`，结果如下

   ```
   $ git status
   On branch feature1
   Changes to be committed:
        (use "git reset HEAD 
   <
   file
   >
   ..." to unstage)
            modified: index.php
   ```

   表明：暂存区里现在有index.php文件

5. 输入  
   `git commit -m "修改index.php"`  
   ，进行提交，再次查看  
   `git status`  
   ，得到

   ```
   $ git status
   On branch feature1
   nothing to commit, working directory clean
   ```

   表明：当前目录下，没有需要提交的文件，即上次的提交成功了

### Sourcetree方式（推荐） {#sourcetree方式（推荐）}

1. 修改index.php文件，则在文件状态里看到如下状态  
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut24.png)

   表明：index.php已经被修改了，但是没有放入暂存区

2. 单击“Stage All”（因为这里只有index.php文件，所以只能选中“Stage All”，如果修改多个文件，而只想提交部分文件的话，则在“未暂存文件”里选中需要暂存的文件，单击“Stage Selected”）。得到如下结果
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut25.png)
   表明：暂存区里现在有index.php文件
3. 编辑提交信息，进行提交
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/assets/shotcut26.png)



