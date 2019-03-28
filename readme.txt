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

回到最近的一次commit
$ git reset --hard HEAD
回退到上一个commit
$ git reset --hard HEAD^

显示文件“readme.txt”
$ cat readme.txt

$ git reflog
$ git reset --hard bff33ef

Working Directory -add -> 
Repository
stage(index) -commit-> master(HEAD)

$ git checkout -- readme.txt
$ git reset HEAD readme.txt

$ rm test.txt
$ git checkout -- test.txt

$ git rm test.txt
$ git commit --m "remove test.txt"

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