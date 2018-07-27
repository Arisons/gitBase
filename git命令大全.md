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
- 