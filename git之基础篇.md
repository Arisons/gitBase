# git之基础篇

### github

- https://github.com

- 只不过这个网站提供了允许通过git上传代码的功能
#### 提交代码到github
##### 通过`Use HTTPS` 上传或者下载服务端的代码（不推荐，不安全）
- `git push [地址] master`
 + 示例：`git push https://github.com/Arisons/gitBase.git master` 
 + 会把当前分支的内容上传到远程的master分支上
- `git pull [地址] master`
 + 示例：`git pull https://github.com/Arisons/gitBase.git master` 
 + 会把远程分支的数据得到：（*注意本地-要初始化 -> git init*）
- `git clone [地址]`
 + 会得到远程仓库相同数据，如果多次执行会覆盖本地内容。

 ##### 通过`Use ssh` 上传或者下载服务端的代码
 - 生成公钥、私钥
 - + 在命令行输入   `ssh-keygen -t rsa -C '邮箱'` 一直回车后，没意外就在本地电脑创建了`.ssh` ,路径是：C:\Users\Administrator\.ssh 里面有两个文件，`.pub`后缀结尾的是公钥，`.rsa`后缀结尾的是私钥。讲公钥文件打开，复制粘贴到github 中settings 里面