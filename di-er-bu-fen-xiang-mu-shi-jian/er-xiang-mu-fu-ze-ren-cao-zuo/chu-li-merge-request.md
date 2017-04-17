# 分支处理 {#4-处理merge-request}

在团队协作中，为了减小误操作带来的损失，要对一些关键的分支进行保护。保护以后，只有Master权限的用户才能对这个分支进行修改。

   0. 默认的项目 master 分支是受保护的， 只有相关的成员角色是 master 才能进行分支合并操作。

1. 登录 gitlab，进入项目页面，点击项目的"Setttings"，选择“Repository

2. 选定分支，并指定特定角色才能进行编辑。

![](/assets/protected.png)

1. # 4 处理merge request {#4-处理merge-request}

对于被保护的分支，只有Master权限的用户才能对这个分支进行修改。

而developer权限的用户可以发送merge request，即合并请求，请求把自己修改的分支合并到某一个被保护分支上。

发送请求后，管理者可以在gitlab的merge request页面看见merge request，进行检查后拒绝或者同意就行了。

![](/assets/merge.png)



