# sourcetree 介绍 {#2-sourcetree介绍}

> Where there is a shell, there is a way.                                                          喜欢 GUI 的直接看下面：

**SourceTree **是 Windows 和Mac OS X 下免费的 Git  客户端，拥有可视化界面，容易上手操作。同时它也是Mercurial和Subversion版本控制系统工具。支持创建、提交、clone、push、pull 和merge等操作。

### 相关名词解释：

* 克隆\(clone\)：从远程仓库URL加载创建一个与远程仓库一样的本地仓库
* 提交\(commit\)：将暂存文件上传到本地仓库（我们在Finder中对本地仓库做修改后一般都得先提交一次，再推送）
* 检出\(checkout\)：切换不同分支
* 添加（add）：添加文件到缓存区
* 移除（remove）：移除文件至缓存区
* 暂存\(git stash\)：保存工作现场
* 重置\(reset\)：回到最近添加\(add\)/提交\(commit\)状态
* 合并\(merge\)：将多个同名文件合并为一个文件，该文件包含多个同名文件的所有内容，相同内容抵消
* 抓取\(fetch\)：从远程仓库获取信息并同步至本地仓库
* 拉取\(pull\)：从远程仓库获取信息并同步至本地仓库，并且自动执行合并（merge）操作，即 _**pull=fetch+merge**_
* 推送\(push\)：将本地仓库同步至远程仓库，一般推送（push）前先拉取（pull）一次，确保一致
* 分支\(branch\)：创建/修改/删除分枝
* 标签\(tag\):给项目增添标签
* 工作流\(Git Flow\):团队工作时，每个人创建属于自己的分枝（branch），确定无误后提交到master分枝
* 终端\(terminal\):可以输入git命令行

### 安装并配置

请到相关的内部 Samba 服务器上拉取， 如果发现没有对应的安装包，请自行下载并上传, 方便后面的年轻人直接取用。

完成相关的登录注册

1. 完成相关的登录注册

![](/assets/sourcetree2.png)

1. 完成相关的配置

![](/assets/sourcetreeemail.png)

1. 规范 commit 信息

![](/assets/commit.png)

[http://www.ruanyifeng.com/blog/2016/01/commit\_message\_change\_log.html](http://www.ruanyifeng.com/blog/2016/01/commit_message_change_log.html)

### 命令行配置

如果你欣赏命令行，可以添加下面相关的配置\(添加前请确保你知道相关命令的意思\)：

```
[user] 
name = shady   
email = enming.xie@blabla.fr

[color]      
ui= auto

[alias]      
st = status       
pl = pull --ff-only      
ps = push      
co = checkout      
ci = commit    
df = difftool        
cp= cherry-pick   
ca = commit --amend    
br = branch        
l = log --stat    
last= log -1
lg = log --color --graph --pretty=format:'%Cred%h%Creset  -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)
 < %an > %Creset' --abbrev-commit      
up = push origin      
lf = log --follow -p      
aa = ls-files --modified      
su = status -uno      
cm = commit -m    
uf = push origin -f     
cl = clean -fdx   
fe = fetch --prune    
cf  = clean -fdx    
bd = branch -D      
cb = checkout -b

[push]      
default = simple

[core]    
editor = vim    
pager  = more -+F

[diff]        
tool = meld

[difftool]        
prompt = false

[merge]        
tool = meld

[init]      
templatedir = ~/.git_template
```

相关配置文件：

Git 提供了一个叫做 git config 的工具，专门用来配置或读取相应的工作环境变量。相关变量可以存放在以下三个不同的地方：

●/etc/gitconfig 文件：系统中对所有用户都普遍适用的配置。若使用 git config 时用--system 选项，读写的就是这个文件。

●~/.gitconfig 文件：用户目录下的配置文件只适用于该用户。若使用 git config 时用--global 选项，读写的就是这个文件。

●当前项目的 git 目录中的配置文件（也就是工作目录中的 .git/config 文件）：这里的配置仅仅针对当前项目有效。每一个级别的配置都会覆盖上层的相同配置，所以.git/config 里的配置会覆盖/etc/gitconfig 中的同名变量。

