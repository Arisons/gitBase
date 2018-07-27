# git之基础篇
### 初始化仓库

`git init`
初始化一个git，初始完git后，如果你是window 用户，你会在目录里看到一个`.git`文件夹，这就说明本地初始化git成功了，然后输入
```js
git add readme.md
```
给git添加文件readme.md,添加完之后，需要进行托付，并写明托付的原因：

```js
git commit -m '这里输入添加的托付'
```

其中`-m`后面的`' '`  就是你写的托付原因，当然也是支持汉语的，接下来就是，添加远程仓库：（注意后面的链接是你创建github项目时，自动生成的）

```js
git remote add origin https://github.com/Arison/gitBase.git
```

添加完远程仓库分支后，接下来就是提交这个分支了：

```js
git push -u origin master
```

提交的时候回要求你输入你账号和密码，如果没有要求也无关紧要，输入完成以后到我们的项目里看，它就创建成功过了。

##### 这种方式，是先初始化本地git，再把git提交成远程分支的，接下来我们来看另外一种本地化方式。

### github篇的关联

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
#### 在push和pull 操作进行时，先pull ,再push
- 当我们在push时，加上-u 参数，那么在下一次push 时，我们只需要写上`git push`就能上传我们的代码了（加上-u 之后，git 就会把当前的分支和远程指定的分支进行关联。git push origin master）