# git的常用操作

>记录github命令行下常用命令,如果想了解git相关知识推荐git官方书籍[Pro Git](https://git-scm.com/book/zh/v2)

</br>

## 添加或修改文件

在本地修改文件之后使用git add . 将项目中所有的修改提交到暂存区  
使用commit命令提交到仓库，-m中描述本次提交(支持[emoji](https://www.webfx.com/tools/emoji-cheat-sheet/):+1:)  
push到远程仓库中  

~~~shell
git add .
git commit -m "say something about this commit"
git push
~~~

> 跳过暂存区

虽然使用git add . 可以精心准备要提交的细节，但是有时略显麻烦，Git提供了一个跳过使用暂存区的方法

~~~shell
git commit -a
~~~

## 查看更改

~~~shell
git diff
~~~

> 加号表示新增加的行，减号表示删掉的行

## 查看提交历史

~~~shell
git log
# 查看最近两次提交,并和现在的版本比较差别
git log -p -2
# 让程序只显示一行简略信息
git log pretty=oneline
# 查看特定文件的改动
git log README.md
~~~

## 撤销操作

为了使仓库历史减少“啊！忘记了一个文件”、“一个小修改”:joy:  
commit提供了 --amend参数，在上次commit之后紧跟可以追加漏掉的修改

~~~shell
git commit -m"initial commit"
git add forgotten.md
git commit --amend
~~~

撤销工作区的更改

~~~shell
git restore <file>...
~~~

> 撤销了**本地的修改**,不可逆

## 添加标签

轻量标签

~~~shell
git tag v1.4-lw
~~~

附注标签

~~~shell
get tag -a v1.4 -m "my version 1.4"
~~~

> 轻量标签只会显示提交信息  
> 附注标签显示了打标签者的信息、打标签的日期时间、附注信息，然后显示具体的提交信息

后期打标签

~~~shell
git log pretty=oneline
git tag -a v1.0 6ce31bd
~~~

## 添加分支

## 回滚到某个版本

