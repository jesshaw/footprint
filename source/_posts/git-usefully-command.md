---
title: git常用命令
tags: git,git命令
categories: 
  - git

thumbnail: /gallery/blue-water9.jpg
---

收集平时常用的一些maven命令。
<!-- more -->
## 箭头键不能工作

经常碰到在bash中执行命名后需要使用上下箭头键来完成选择，但是偏偏在win7中不能使用。(当然换到cmd中是可以的，不使用此方式的原因你懂的)

实际上我们是实现选择的工作，虽然体验上是差了一些，但以下方法是行的

即使用输入"数字+回车"实现选择的功能，如下示例
```bash
yo generate
what would you like to do? (Use arrow keys)
Run a generator
Bootstrap
Loopback
exit
## 输入2+回车即选择了Bootstrap
```


## 设置提交的用户名和邮箱

##### 列出所有配置
```bash
git config [--local|--global|--system] -l
```

##### 设置某个配置项的值
```bash
git config [--local|--global|--system] section.key value

git config --local user.name "lexiangmiao"
```

##### 查看某项的当前值

```bash
git config name

git config user.name
```

## 回滚

回滚前两次提交

```bash
git revert HEAD~2
git push
```

push之后会增加一条revert "引用上一次提交的备注"的提交记录

## 获取分支
```sh
$ git checkout -b dev.0.1 origin/dev.0.1 
$ git checkout dev.0.1
```

## 以ssh方式复制项目（不需要输入帐户）
```sh
$ git clone git@github.com:jesshaw/node-sample-project.git
```

## 日志输出更友好
```bash
$ git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
$ git config --global alias.lg "log --color --graph --pretty=format:'%C(bold cyan)%h%C(reset) -%C(yellow)%d%C(reset) %s %C(green)(%cr) %C(bold magenta)<%an>%C(reset)' --abbrev-commit"
$ git config --global alias.lgl "log --color --graph --pretty=format:'%C(bold cyan)%h%C(reset) -%C(yellow)%d%C(reset) %s %C(green)(%ci) %C(bold magenta)<%an>%Creset' --abbrev-commit"
$ git config --global --unset alias.lg
$ git config --global --unset alias.lgl
```

## 怎样移除远程的提交日志
##### 示例数据如下
	```bash
	$ git lg -5
	* 728e3ed - (HEAD -> master, origin/master, origin/HEAD) test4 (26 minutes ago) <ximing>
	* c8f834f - (mywork) test3 (19 hours ago) <ximing>
	* 3992e9c - test2 (19 hours ago) <ximing>
	* abbe339 - test1 (19 hours ago) <ximing>
	* 2936159 - add bookmark (21 hours ago) <ximing>
	```
##### 方法1 

移除c8f834f之后的提交历史

	```bash
	$ git reset --hard 3992e9c
	$ git push origin -f  master
	```

##### 方法2  
1. 仅移除abbe339的提交，其他保留

	```bash
	$ git rebase -i 2936159
	error: could not apply 3992e9c... test2

	When you have resolved this problem, run "git rebase --continue".
	If you prefer to skip this patch, run "git rebase --skip" instead.
	To check out the original branch and stop rebasing, run "git rebase --abort".
	Could not apply 3992e9c9ac3a6e6bb64e0876dace165980990b45... test2
	```
2. 此时应当解决冲突，然后多次执行以下命令直至没有error: could not apply 3992e9c... test2此类错误为止

	```bash
	$ git status
	$ git add -A 
	$ git rebase --continue
	```
3. 提交到远程

	```bash
	$git push origin +master
	```

## 清除远程上某个文件的所有提交日志

``` bash
$ cd current directory
$ git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch 文件名' --prune-empty --tag-name-filter cat -- --all
$ git push origin master --force
$ rm -rf .git/refs/original/
$ git reflog expire --expire=now --all
$ git gc --prune=now
$ git gc --aggressive --prune=now
```

## 提交所有更改的文件

``` bash
$ git commit -a -m "提交备注"
```

## 取消远程某次或某几次提交(远程日志保留)

``` bash
$ git revert --no-commit b49eb8e 1d8b062
## 解决冲突后提交
$ git commit -a -m "Revert commits b49eb8e and 1d8b062"
```

## 取消本地文件修改
``` bash
$ git checkout file1.js file2.js
```

## 选择某个（dev1）分支上指定的提交合并到其他（bugfix）分支

``` bash
$ git checkout dev1
$ git rebase -i bugfix #基于bugfix，列出提交的记录，选择需要的提交执行。有时需要解决冲突
$ git checkout bugfix
$ git merge dev1 
```




