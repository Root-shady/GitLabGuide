# 初始化项目 {#初始化项目}

### Step 1 在gitlab中新建一个分组（项目小组） {#step-1-在gitlab中新建一个项目}

1 访问 公司gitlab网址 并登录

1. 点击左上角的 tarbar， 选定 groups 进行小组的创建，

创建规范：

* \[强制\] 小组名称使用项目合同编号（因为在该小组命名空间下，项目仓库地址会包含小组的名称）
* ［建议］如果名称需要分隔，统一使用下划线。
* ［强制］需要在小组的相关描述中，对改小组对应的项目进行中文描
* ［建议］默认的小组 visibility 选用 internal， 即只要是系统登录的用户就可以看到

![](/assets/addgroup.png)

1. 进行相关的成员添加和项目添加

添加规范：

* ［强制］默认项目成员添加权限为 Developer
* ［建议］项目创建默认权限为 private，如果为 internal， 则非小组成员能够进行仓库 clone
* ［提醒］项目创建后，相关权限可以在项目的设置进行修改

![](/assets/members.png)

1. 单击小组命名空间中的 “New Project”按钮，新建项目

创建规范

* ［强制］Project Name 填入项目名称 ，使用合同编号名称
* ［建议］Project description填入项目描述，项目的相关信息
* ［建议］Visibility Level选择Private

![](https://albertlin1102.gitbooks.io/sc_git_guide/content/part2/shotcut2.png)

4 这样 gitlab中新建了一个项目啦，如下图所示，中间文本框显示的是用ssh方式访问项目的地址

![](https://albertlin1102.gitbooks.io/sc_git_guide/content/part2/shotcut3.png)

### Step 2 把本地的项目文件推送到gitlab上 {#step-2-把本地的项目文件推送到gitlab上}

#### 方法一 Git命令行方式 {#方法一-git命令行方式}

1 进入项目所在的文件夹，在空白处右键，选择`Git Bash Here`。输入以下代码

```
git init
git remote add origin 你的项目地址
git add .
git commit -m "你要添加的提交信息"
git push -u origin master
```

示例如下

```
git init
git remote add origin git@gitlab.oneitfarm.com:linxingyuan/example.git
git add .
git commit -m "初始化项目"
git push -u origin master
```

每行代码的含义是：  
a. 初始化本地仓库  
b. 添加远程仓库，命名为origin  
c. 把本地所有文件都放入暂存区  
d. 提交暂存区的所有文件到本地仓库  
e. 把本地当前分支推送到远程仓库origin的master分支上

2 这样，就成功把项目文件推送到gitlab上了，访问gitlab上的这个项目，选择Repository，就可以在gitlab上查看远程仓库的分支情况了![](https://albertlin1102.gitbooks.io/sc_git_guide/content/part2/shotcut4.png)

#### 方法二 Sourcetree方式 {#方法二-sourcetree方式推荐}

1 文件——克隆/新建，选择“创建新仓库”，“目标路径”填入项目文件夹地址，点击“创建”，如下图所示

![](/assets/createproject.png)

2 单击“Stage All”，将项目文件夹中所有文件放入暂存区，然后编辑提交信息，进行提交，如下图所示

![](/assets/stage.png)

3 为项目添加远程仓库， 填写相关的 “远端名称”，“URL/路径”。“远端名称”是指远程仓库在本地的名字，“URL/路径”填写仓库的ssh地址，如下图所示

![](/assets/remote.png)

4 分别填写“远端名称”，“URL/路径”。“远端名称”是指远程仓库在本地的名字，“URL/路径”填写仓库的ssh地址，如下图所示

1. 进行相关的分支的推送，需要选定上传的分支

![](/assets/remotepush.png)

