# 1 安装git {#1-安装git}

### Windows {#windows}

Windows下用安装包安装就行了，安装包已经放在网盘里了，具体步骤如下：

1. `command+R`
   打开“运行”窗口
2. 输入
   `\\192.168.0.18`
   ，回车
3. 进入
   `运维网络硬盘\git相关软件`
   文件夹下
4. 64位系统选择
   `Git-2.9.0-64-bit`
   进行安装，32位选择
   `Git-2.9.3-32-bit`
   进行安装
5. 安装中的所有选项保留默认就行了，一直点
   `next`
   ，直到安装完成
6. 最后，还需要设置一下用户名和邮箱。开始菜单——
   &gt;
   Git——
   &gt;
   Git Bash，打开Git Bash窗口，输入下列代码。其中Your Name替换为你的用户名，email@example.com替换为公司邮箱
   ```
   $ git config --global user.name "Your Name"
   $ git config --global user.email "email@example.com"

   ```

   这一步的配置是为这台机器指定一个用户名。后面用这台机器提交代码时，会显示提交者的用户名。所以，为了团队协作方便，一般用名字拼音来作为用户名。（我试了一下，用中文作为用户名好像也是可以的，大家可以试试）
 
   另外，
   `git config`
   命令的
   `--global`
   参数表示这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。
   ### MacOS {#macos}

   MacOS下的安装请访问
   [Downloading Git](https://git-scm.com/download/mac)
   进行下载安装
   ### Linux {#linux}

   Linux下的安装请参见
   [Download for Linux and Unix](https://git-scm.com/download/linux)



