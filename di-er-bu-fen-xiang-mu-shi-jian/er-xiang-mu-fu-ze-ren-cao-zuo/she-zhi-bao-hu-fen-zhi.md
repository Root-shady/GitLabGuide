## Project {#project}

不同角色在项目中拥有的权限：

| Action | Guest | Reporter | Developer | Master | Owner |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 创建 issue | ✓ | ✓ | ✓ | ✓ | ✓ |
| 创建可信 issue | ✓ | ✓ | ✓ | ✓ | ✓ |
| 查看可信 issues | \(✓\)[1](https://docs.gitlab.com/ee/user/permissions.html#fn1) | ✓ | ✓ | ✓ | ✓ |
| 评论 | ✓ | ✓ | ✓ | ✓ | ✓ |
| 查看后台任务 | ✓[2](https://docs.gitlab.com/ee/user/permissions.html#fn2) | ✓ | ✓ | ✓ | ✓ |
| 查看任务日志 | ✓[2](https://docs.gitlab.com/ee/user/permissions.html#fn2) | ✓ | ✓ | ✓ | ✓ |
| 查看下载任务生成的软件包 | ✓[2](https://docs.gitlab.com/ee/user/permissions.html#fn2) | ✓ | ✓ | ✓ | ✓ |
| 查看 wiki 页面 | ✓ | ✓ | ✓ | ✓ | ✓ |
| 拉取项目代码 |  | ✓ | ✓ | ✓ | ✓ |
| 下载项目 |  | ✓ | ✓ | ✓ | ✓ |
| 创建代码片段 |  | ✓ | ✓ | ✓ | ✓ |
| 管理issue 追踪器 |  | ✓ | ✓ | ✓ | ✓ |
| 管理标签 |  | ✓ | ✓ | ✓ | ✓ |
| 查看commit 状态 |  | ✓ | ✓ | ✓ | ✓ |
| 查看容器或者注册机 |  | ✓ | ✓ | ✓ | ✓ |
| 查看环境 |  | ✓ | ✓ | ✓ | ✓ |
| 创建环境 |  |  | ✓ | ✓ | ✓ |
| 使用环境终端 |  |  |  | ✓ | ✓ |
| 停用环境 |  |  | ✓ | ✓ | ✓ |
| 查看合并请求列表 |  | ✓ | ✓ | ✓ | ✓ |
| 管理／接受合并分支 |  |  | ✓ | ✓ | ✓ |
| 创建合并请求 |  |  | ✓ | ✓ | ✓ |
| 创建新的分支 |  |  | ✓ | ✓ | ✓ |
| Push to non-protected branches |  |  | ✓ | ✓ | ✓ |
| Force push to non-protected branches |  |  | ✓ | ✓ | ✓ |
| Remove non-protected branches |  |  | ✓ | ✓ | ✓ |
| 打标签 |  |  | ✓ | ✓ | ✓ |
| 编写 wiki |  |  | ✓ | ✓ | ✓ |
| 取消或者重试任务 |  |  | ✓ | ✓ | ✓ |
| Create or update commit status |  |  | ✓ | ✓ | ✓ |
| Update a container registry |  |  | ✓ | ✓ | ✓ |
| Remove a container registry image |  |  | ✓ | ✓ | ✓ |
| Create new milestones |  |  |  | ✓ | ✓ |
| Add new team members |  |  |  | ✓ | ✓ |
| Push to protected branches |  |  |  | ✓ | ✓ |
| Enable/disable branch protection |  |  |  | ✓ | ✓ |
| Turn on/off protected branch push for devs |  |  |  | ✓ | ✓ |
| Enable/disable tag protections |  |  |  | ✓ | ✓ |
| Rewrite/remove Git tags |  |  |  | ✓ | ✓ |
| Edit project |  |  |  | ✓ | ✓ |
| Add deploy keys to project |  |  |  | ✓ | ✓ |
| Configure project hooks |  |  |  | ✓ | ✓ |
| Manage runners |  |  |  | ✓ | ✓ |
| Manage job triggers |  |  |  | ✓ | ✓ |
| Manage variables |  |  |  | ✓ | ✓ |
| Manage pages |  |  |  | ✓ | ✓ |
| Manage pages domains and certificates |  |  |  | ✓ | ✓ |
| Switch visibility level |  |  |  |  | ✓ |
| Transfer project to another namespace |  |  |  |  | ✓ |
| Remove project |  |  |  |  | ✓ |
| Force push to protected branches[3](https://docs.gitlab.com/ee/user/permissions.html#fn3) |  |  |  |  |  |
| Remove protected branches[3](https://docs.gitlab.com/ee/user/permissions.html#fn3) |  |  |  |  |  |
|  |  |  |  |  | Remove pages |

## Group {#group}

Any user can remove themselves from a group, unless they are the last Owner of the group. The following table depicts the various user permission levels in a group.

| Action | Guest | Reporter | Developer | Master | Owner |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Browse group | ✓ | ✓ | ✓ | ✓ | ✓ |
| Edit group |  |  |  |  | ✓ |
| Create subgroup |  |  |  |  | ✓ |
| Create project in group |  |  |  | ✓ | ✓ |
| Manage group members |  |  |  |  | ✓ |
| Remove group |  |  |  |  | ✓ |

## Gitlab CI

GitLab CI permissions rely on the role the user has in GitLab. There are four permission levels it total:

* admin
* master
* developer
* guest/reporter

The admin user can perform any action on GitLab CI in scope of the GitLab instance and project. In addition, all admins can use the admin interface under`/admin/runners`.

| Action | Guest, Reporter | Developer | Master | Admin |
| :--- | :--- | :--- | :--- | :--- |
| See commits and jobs | ✓ | ✓ | ✓ | ✓ |
| Retry or cancel job |  | ✓ | ✓ | ✓ |
| Remove project |  |  | ✓ | ✓ |
| Create project |  |  | ✓ | ✓ |
| Change project configuration |  |  | ✓ | ✓ |
| Add specific runners |  |  | ✓ | ✓ |
| Add shared runners |  |  |  | ✓ |
| See events in the system |  |  |  | ✓ |
| Admin interface |  |  |  | ✓ |



