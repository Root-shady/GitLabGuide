# 相关配置

### Gitlab 访问地址

* 内网测试服务器：[http://\*.honray.cc](http://*.honray.cc)  \(192.168.1.130\)
* 外网测试服务器：[http://\*.honray.cc](http://*.honray.cc)  \(112.74.98.251\)

### 文件共享服务器

相关的文件下载都可以在公司内部的 samba 服务器下载，相关的详细信息请查看邮件

* mac 下在Finder 里面找到 connect to server, 然后输入下面的地址：   smb://192.168.1.130/share
* Window下在网络设置那里（开启设备发现功能）， 然后找到 honray-server 主机

### DNS 服务器

### 内网访问

公司本地自建 DNS 服务器，使用公司内部网络，请使用  内部服务器地址 \([http://gitlab.honray.cc](http://gitlab.honray.cc)\)。

检查自己电脑的 DNS 设置主 DNS 是否为：192.168.1.130, 局域网默认 DNS 则不需要改动，可以通过在命令行使用下面的命令进行检测：

```
ping gitlab.honray.cc   
#正确配置可解析到 192.168.1.130，如果结果是外网地址，请自行检查本机 DNS 设置
```

### 外网如何访问

外网可直接访问 外部服务器地址 \([http://gitlab.honray.cc\](http://gitlab.honray.cc\)\), 相关的操作和使用内部网络一样，如果需要进行相关的代码仓库 clone， 请参照下面的方法：

    获取 VPN 连接 配置文件  
    下载 OpenVPN 客户端，连接到公司服务器 VPN
    在 baidu 输入， ip， 可以看到本机 IP 变成  `112.74.98.251` 则表示连接成功

下面举例说明如何进行仓库 clone：

```
目标仓库地址为： git@gitlab.honray.com:SQA/ThinkTest.git
将仓库地址的相关域名改成服务器在 VPN 中的主机地址： 10.8.0.6 此 IP 为固定地址
则为下面命令： git clone  git@10.8.0.6:SQA/ThinkTest.git
```

如果上述步骤出现未知问题，请检测目标主机是否连通

```
ping 10.8.0.6  
如果无法连通， 请截图保留相关错误信息，并联系管理员。
```


