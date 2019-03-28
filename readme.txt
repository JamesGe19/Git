Git is a distributed version control system.
Git is free software.

$ ls
$ mkdir Git
$ cd Git
$ cd /e/xxx
$ cd /c/Users/GElab/Git
$ pwd

$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/

$ git add readme.txt
$ git commit -m "wrote a readme file"

$ git status

$ git diff 
$ git diff --cached
$ git diff HEAD

$ git log
$ git log --pretty=oneline

$ git reset --hard HEAD^
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
$ git remote add github git@github.com:JamesGe19/Git.git
$ git remote add github git@gitee.com:JamesGe19/Git.git
$ git remote -v
$ git push github master
$ git push gitee master