Git is a distributed version control system.
Git is free software.

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
