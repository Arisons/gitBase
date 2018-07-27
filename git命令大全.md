### git的一些基础命令

##### 一般配置

```js
git --version //查看git的版本信息
git config --global user.name  //获取当前登录的用户
git config --global user.email // 获取当前登录用户的邮箱
```

##### 创建一个文件夹

```js
mkdir nodejs //创建文件夹nodejs
cd nodejs //切换到nodejs目录下
```

##### 初始化git仓库

`git init` //在nodejs文件夹下初始化一个仓库，此时文件里会到一个.git的隐藏文件夹

##### 创建忽略文件

```js
touch .gitignore  //不需要服务器端提交的内容可以写到忽略文件里
```

##### 查看目录

```js
ls -al
```

##### 创建文件并写入内容

如果文件不存在则会创建文件

```js
echo "hello git"
> index.html //将'hello git'写入到index.html中
```

单个 > 箭头表示写入，>>表示追加

##### 查看文件内容

```js
cat index.html
```

##### 增加到暂存区中

```js
git add index.html
git  add -A  //全部添加到缓存区
git add ./    // 亲测这种也是全部添加文件
```

##### 增加到版本库中

```js
git commit -m "备注信息"
```

##### 查看版本

```js
git log --oneline
```

##### 比较差异

- 比较的是暂存区和工作区的差异

  ```js
  git diff
  ```

- 比较的是暂存区和历史区的差异

  ```js
  git diff -cached
  ```

- 比较的是历史区和工作区的差异（修改）

  ```js
  git diff master
  ```

  ##### 撤回内容

  （如果修改了工作区的文件后发现错了，可以用暂存区或者版本库里的文件替换掉工作区的文件）

 ```js
	git checkout index.html
 ```

##### 取消增加到暂存区的内容（添加时）

```js
git reset HEAD index.html
```

//显示目录的状体 有没有添加或者修改文件

```js
git status
```

##### 删除本地文件

```js
rm fileName
```

##### 删除暂存区

- 保证当前工作区中没有index.html

  ```js
  git rm index.html --cached
  ```

  使用--cached 表示删除缓存区中的内容

##### 回滚版本

- 回滚最近的一个版本`git log`

  ```js
  git reset --hard HEAD commit_id
  ```

  ##### 回滚到未来

  ```js
  git reflog
  ```

  ### 分支管理

  ##### 创建分支

  ```js
  git branch dev
  ```

  ##### 切换分支

  ```js
  git checkout dev
  ```

  ##### 创建分支并切换分支

  ```js
  git checkout -b dev
  ```

  ##### 删除分支

  ```js
  git branch -d dev
  ```

  ##### 在分支上提交新的版本

  ```js
  git commit -a -m '提交的信息说明'
  ```

  ##### 合并分支

  ```js
  git merge dev
  ```

  ##### 分支的合并后显示log

  ```js
  git log --oneline --graph --decorate
  ```

  ##### 在分支开发的过程中遇到其他问题乣切换其他分支

  - 保留写好的内容在切换到主干
  - 保留内容

  ```js
  git stash
  ```

  ##### 再次切换分支后需要应用一下保留的内容

  ```js
  git stash apply
  ```

  ##### 丢掉保存的内容

  ```js
  git stash drop
  ```

  ##### 使用并丢掉

  ```js
  git stash pop
  ```

  ##### 最佳分支

  - 有的时候开发需要合并指定的内容，而不是合并所有的提交，所以我们需要挑选最好的，自己生产的版本

  ##### 合并分支把树杈搬到主干上

  ```js
  git rebase
  ```

  ### 添加远程的仓库

  ##### push  -u

  -u 参数 upstream

  ```js
  git  push origin master -u  //获取最新代码
  ```

  ##### 连接远程仓库

  ```js
  git remote add origin 仓库的地址
  ```

  ##### 查看远程仓库

  ```js
  git remote -v
  ```

  ##### 删除远程仓库

  ```js
  git remote rm origin
  ```

  