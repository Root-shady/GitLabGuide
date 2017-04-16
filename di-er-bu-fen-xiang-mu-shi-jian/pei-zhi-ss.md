# 4 配置ssh key {#4-配置ssh-key}

SSH是一种网络协议，用于计算机之间的加密登录。  
本机和服务器上的gitlab使用ssh协议建立连接。

### 1 本机配置 {#1-本机配置}

#### 生成ssh密钥 {#生成ssh密钥}

1. 打开Git Bash，输入
   `$ ssh-keygen`
   ，回车
2. 连按三次空格
   1. 首先会提示
      `Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa):`
      ，意思是让指定密钥保存的地址。一般默认就行了，直接回车。默认存放在
      `/c/Users/Administrator/.ssh/id_rsa`
      ，注意
      `.ssh`
      文件夹是隐藏文件夹，需要Windows设置隐藏文件夹可见才能看见
      1. 然后会提示
         `Enter passphrase`
         ，无需设置
3. 生成成功

#### 修改访问远程主机的端口 {#修改访问远程主机的端口}

ssh默认的端口是22，而远程主机`gitlab.oneitfarm.com`把端口修改成了29622，所以在本地需要配置一下

1. 进入之前存放密钥的文件夹（默认是
   `/c/Users/Administrator/.ssh`
   ）
2. 用sublime、Atom、记事本等文本编辑器新建一个
   `config`
   文件，放在该目录下（注意没有
   **后缀名**
   ）
3. `config`
   文件中的内容如下

```
Host gitlab.oneitfarm.com
    HostName gitlab.oneitfarm.com
    Port 29622
    User 你的邮箱地址
    IdentityFile ~/.ssh/id_rsa

```

### 2 gitlab帐号配置ssh密钥 {#2-gitlab帐号配置ssh密钥}

在本机生成ssh密钥后，会生成`id_rsa`和`id_rsa.pub`两个文件，分别是私钥和公钥。我们需要把公钥配置到自己的gitlab帐号上，这样才能与gitlab之间通过ssh建立连接

1. 访问
   `gitlab.oneitfarm.com`
   ，登录，单击右上角头像，Profile Settings，进入帐号设置
2. 选择 SSH Keys，进入如下页面
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/part2/shot1.png)
3. 进入之前存放密钥的文件夹（默认是
   `/c/Users/Administrator/.ssh`
   ），用sublime、Atom、记事本等文本编辑器打开
   `id_rsa.pub`
   ，把里面的内容全部复制出来，粘贴到下图所示位置
 
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/part2/shot2.png)
4. Title随便填一个就行了，填完单击Add key，就OK啦

配置完以后，就可以用 Git Bash 从 gitlab 上克隆项目，或者向 gitlab 推送分支啦。

### 3 sourcetree中导入ssh密钥 {#3-sourcetree中导入ssh密钥}

1. 打开sourcetree
2. 单击“工具”——“选项”
3. 在下图红框内导入ssh密钥，“SSH 密钥”栏填写私钥的地址，默认是
   `C:\Users\Administrator\.ssh\id_rsa`
   ，“SSH 客户端”选择“OpenSSH”，如下图所示
 
   ![](https://albertlin1102.gitbooks.io/sc_git_guide/content/part2/shot3.png)
4. 点击确定，就OK啦



