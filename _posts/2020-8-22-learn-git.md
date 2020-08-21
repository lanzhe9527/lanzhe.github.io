---
layout: post
title: 常用git笔记
date: 2020-8-22 
tags: git命令   
---


##  git命令情形

本地改动了文件index.html和index.css

情形1：改了文件还没有执行git add想撤销index.html的内容
```
$ git checkout -- pages/src/index.html

```

情形2：改了文件还没有执行git add想撤销所有的内容
```
$ git reset --hard HEAD

```
情形3：改了文件执行了git add但是没有执行git commit想撤销index.html内容.
```
$ git reset HEAD pages/src/index.html
$ git checkout -- pages/src/index.html

```
用命令git reset HEAD <file>可以把暂存区的修改撤销掉（unstage），重新放回工作区(也就是git add之前)











### 理解这张图(重要)
![](https://www.git-tower.com/learn/media/pages/git/ebook/cn/command-line/basics/working-on-your-project/452967006-1597909835/staging-area-file-status.png)
###  设置Git
安装完git后设置你的全局的用户名和邮箱
```
$ git config --global user.name "John Doe"
$ git config --global user.email "john@doe.org"

```
注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

### 从一个未被纳入版本控制的项目开始
你现在正在着手在一个项目开发上，但是它还未被纳入版本控制系统的管理中，那就让我们从这个项目开始吧！在命令行界面中跳转到这个项目的根目录（root folder），然后键入 “git init” 命令来建立一个 Git 项目：
```
$ cd /d/dev/project
$ git init

```
现在我们来看看在这个目录下都有哪些文件（也包括所有的隐藏文件）：
```
ls -la

```
你将会看到其中有一个新建的并且名字为 “.git” 的隐藏目录。为什么有这么一个新的目录呢？其实这是 Git 给我们创建的一个空的本地仓库（local repository）。为什么是　“空”　呢？开始时 Git 并不会自动地把当前项目中的所有的内容当作　“初始版本（initial version）”　添加到本地仓库中的，因此现在这个本地仓库还不包含任何你的项目文件。
### 忽略文件设置

### 第一次提交
####  这个时候本地仓库是空的，需要把工作区的项目提交到本地仓库
把工作区的所有内容添加到暂存区
```
git add .
```
把暂存区的内容添加到本地仓库
```
git commit -m "第一次提交"
```
### 本地 / 远程工作流程
![](https://www.git-tower.com/learn/media/pages/git/ebook/cn/command-line/remote-repositories/introduction/-1045933932-1597909835/basic-remote-workflow.png)

　假设你在github上创建了一个仓库，下面的命令是关联本地仓库和远程仓库
```
$ git remote add origin git@github.com:lanzhe9527/learngit.git

```

请千万注意，把上面的`lanzhe9527`替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。


 下一步把本地库的所有内容推送到远程库上
```
$ git push -u origin master
```
由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

### 另外一种方式就是从远程仓库直接克隆（适用于项目才开始或者新加入到项目的成员）

```
git clone git@github.com:lanzhe9527/lanzhe9527.github.io.git
```
