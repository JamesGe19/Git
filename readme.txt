Git is a distributed version control system.
Git is free software.

显示文件
$ ls    
   
当前路径内创建文件夹”Git“                                    
$ mkdir Git

设置默认路径为当前路径下的“Git”文件夹
$ cd Git

设置默认路径为"e/xxx"
$ cd /e/xxx
$ cd /c/Users/GElab/Git

显示当前路径
$ pwd

初始化repository
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/

add “readme.txt” (staged)
$ git add readme.txt

add all files (staged)
$ git add .

commit file 注释"..."
$ git commit -m "wrote a readme file"

显示状态
$ git status


显示差异：
工作区 - 暂存区
$ git diff 

暂存区 - 版本库
$ git diff --cached

工作区 - 版本库
$ git diff HEAD

日志
$ git log
每个commit内容显示在一行
$ git log --oneline
$ git log --pretty=oneline
显示最近一次提交
$ git log -1

回到最近的一次commit
$ git reset --hard HEAD
回退到上一个commit
$ git reset --hard HEAD^

显示文件“readme.txt”
$ cat readme.txt

显示HEAD改动日志
$ git reflog
回退到“未来”固定ID(bff33ef...)
$ git reset --hard bff33ef

工作原理
Working Directory -add -> 
Repository
stage(index) -commit-> master(HEAD)

把readme.txt文件在工作区的修改全部撤销
$ git checkout -- readme.txt

把暂存区的修改撤销掉（unstage），重新放回工作区
$ git reset HEAD readme.txt

从工作区删除文件
$ rm test.txt
把误删的文件恢复到本本库最新版本
$ git checkout -- readme.txt

从版本库删除文件
$ git rm test.txt
$ git commit -m "remove test.txt"

$ git checkout
用版本库里的版本替换工作区的版本，
无论工作区是修改还是删除，都可以“一键还原”。
$ git checkout c6762a1 -- 1.py
仅对 1.py 进行回到过去操作, 回到 c6762a1 change 1 这一个 commit. 
使用 checkout + id c6762a1 + -- + 文件目录 1.py, 
就能将 1.py 的指针 HEAD 放在这个时刻 c6762a1
 

$ git remote add origin https://github.com/JamesGe19/Git.git
$ git remote add origin git@github.com:JamesGe19/Git.git
$ git push -u origin master
$ git push origin master
$ git clone git@github.com:JamesGe19/ITC.git

$ git remote -v
$ git remote rm origin
$ git remote add origin git@gitee.com:JamesGe19/Git.git

$ git remote rm origin
$ git remote add github-source git@github.com:JamesGe19/Git.git
$ git remote add gitee-source git@gitee.com:JamesGe19/Git.git
$ git remote 
$ git remote -v
$ git push github-source master
$ git push gitee-source master

显示不完全，输入“:q”退出

“Ctrl + C” 退出

"--no-edit": 不编辑直接合并到上一个 commit
$ git commit --amend --no-edit   

创建并切换到“dev”分支
$ git checkout -b dev
相当于以下2个命令：
$ git branch dev
$ git checkout dev

查看当前分支
$ git branch

切换回master分支
$ git checkout master

合并指定分支到当前分支
$ git merge dev

删除分支
$ git branch -d dev
强行删除未合并的分支
$ git branch -D dev

分支合并情况
$ git log --graph --pretty=oneline --abbrev-commit

合并时，如果可能Git会用Fast forward模式，该模式下删除分支后
丢掉分支信息。强制禁用Fast forward模式，Git在merge时生成一个
新的commit，这样从分支历史上就可以看出分支信息。
$ git merge --no-ff -m "merge with no-ff" dev

保存当前工作现场
$ git stash

查看工作现场
$ git stash list

恢复工作现场同时删除stash内容
$ git stash pop
相当于以下两个命令：
恢复stash，但内容不删除
$ git stash apply
删除stash
$ git stash drop

多次stash保存现场，恢复其中一个现场
$ git stash apply stash@{0}

创建远程github-source的dev分支到本地
$ git checkout -b dev github-source/dev

指定本地dev分支与远程github-source/dev分支的链接
$ git branch --set-upstream-to=github-source/dev dev

抓取远程分支内容
$ git pull

把分叉的提交历史“整理”成一条直线，看上去更直观。
缺点是本地的分叉提交已经被修改过了。
$ git rebase
rebase操作可以把本地未push的分叉提交历史整理成直线；
rebase的目的是使得我们在查看历史提交的变化时更容易，
因为分叉的提交需要三方对比。

打新标签
$ git tag v1.0
标签对应的commit id是eff6e
$ git tag v0.5 eff6e
指定commit ID 打新标签并注释
$ git tag -a v1.0 -m "version 1.0" eff6e

查看标签（时间顺序）
$ git tag
按字母排序显示标签信息
$ git show v0.5
注意：标签总是和某个commit挂钩,如果这个commit既出现在master分支，
又出现在dev分支，那么在这两个分支上都可以看到这个标签。

删除标签
$ git tag -d v0.1

标签推送到远程库
$ git push github-source v1.0

一次性推送全部尚未推送到远程的本地标签：
$ git push github-source --tags

删除远程标签一下两步：
先从本地删除：
$ git tag -d v0.9
从远程删除也是push，格式如下
$ git push github-source :refs/tags/v0.9

Git适当地显示不同的颜色
$ git config --global color.ui true

配置别名:
co表示checkout，ci表示commit，br表示branch
$ git config --global alias.co checkout
$ git config --global alias.ci commit
$ git config --global alias.br branch

查看用户的配置信息：
git config --global --list

查看当前仓库配置信息：
git config --glocal --list

每个仓库的Git配置文件都放在.git/config文件中
当前用户的Git配置文件放在用户主目录下的一个隐藏文件.gitconfig中

强制添加 add xxxx
$ git add -f xxxx
检查ignore
$ git check-ignore -v xxxx