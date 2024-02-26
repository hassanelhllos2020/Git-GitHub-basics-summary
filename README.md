# Git & GitHub

# resources

[AraBigData/Git/git.ipynb at main · ahmedsami76/AraBigData · GitHub](https://github.com/ahmedsami76/AraBigData/blob/main/Git/git.ipynb)

[(1) Git and GitHub | شخبط وانت متطمن - YouTube](https://www.youtube.com/watch?v=Q6G-J54vgKc&t=9319s)

[My progress - Git Exercises (fracz.com)](https://gitexercises.fracz.com/committer/71580966ec5aef994480cca3ac088af7ebf307e3?email=hassanelhllos@gmail.com)

## game

[Learn Git Branching](https://learngitbranching.js.org/) 

[https://ohmygit.org/](https://ohmygit.org/)

- Github desktop
    
    [https://youtu.be/8Dd7KRpKeaE?si=o6sZBBqHfjPCSO1g](https://youtu.be/8Dd7KRpKeaE?si=o6sZBBqHfjPCSO1g)
    

![Brainstorming (1).jpg](Git%20&%20GitHub%209cdab09eeee14f4488bbc26d94d9a01a/Brainstorming_(1).jpg)

## gitting started

```bash
git config --global user.name "hassan elhllos"
git config --global user.email"hassanelhllos@gmail.com"
-----------
git init 
**delete ripo**
	$ rm -rf .git
```

## querying configration

```bash
git config --list
```

---

## some important prompts

```bash
clear
ls | ls -al // show files in current folder
pwd #to see which path you are currently in
cd # to open folder
cd .. # back
cd /f #open partition
cd 'programing languages' # use '' on multible words folder
----
mkdir gitwork # creates folder
echo "hello , git" >> file.txt # creates txt file
cat file.txt # shows file content
```

## set Git repo

```bash
git init                    #Initialized empty Git repository
git status
git ls-files                # show files in **index
git ls-files -s             # show sha1 of files**
find .git/objects/ -type f # show files in **repo**
```

## index and repo prompts (we are in index now)

```bash
git add file.text | * # add file to index (staging) 
git rm --cached # udno (staging)
git restore file.txt
-------
git cat-file -p "file-sha"    # shows file content >> **git ls-files -s** 
git cat-file -t "file-sha"    # shows file type
git cat-file -s "file-sha"    # shows file size
```

![Untitled](Git%20&%20GitHub%209cdab09eeee14f4488bbc26d94d9a01a/Untitled.png)

## commit & Log

```bash
#https://www.atatus.com/blog/tracking-code-changes-with-git-log/#introduction-to-git-log
$ git commit -m "intial commit"   #commit file to repo
$ git commit -am "<msg>"        #Skipping the Staging Area
git log                           #history
$ git log -n 3                    #number of commits 3
$ git log --oneline
git log --graph
$ git log file.txt    #show log for specific file 
$ git log --oneline file.txt
-------------------------------
find .git/objects/ -type f  #show files in **repo
$ git cat-file -p ("sha")   #read the commit file , i get sha from (**git log**)
------------------------------
git diff // diffrence between tree and index
git diff SHA1..head //diffrence between two commits
$ git diff --staged // diffrence between index and repo
$ git show 789cde6** 
```

## remove and undo

```bash
$ git rm file.txt   #removes file from tracking(index) and from filesystem
$ git restore file.txt #REVERTING IT FROM THE LAST index (staged)
$ git restore --staged file.txt #REVERTING IT FROM THE LAST stage
------------------------
$ git add <file>
$ git rm --cached <file> # Untracking tracked file
------------------------
$ git commit --amend #edit last commit message
```

## #move head in commits

```bash
$ git reflog   #show head moves
$ git reset head~1        #git back to any commit i want
$ git reset head@{1}      #git forward to any commit
#the commit i reset are stored in the index , so i need to do $git restore .
#to skip this step just add --hard
$ git reset head@{1} --hard      #restore last commit directly
----------------------------------------------
git checkout main^ #git back to "the first parent of main".
git branch -f main HEAD~3 #moves (by force)the main branch to three parents behind HEAD.
```

### important concept “detching”

![1.PNG](Git%20&%20GitHub%209cdab09eeee14f4488bbc26d94d9a01a/1.png)

![2.PNG](Git%20&%20GitHub%209cdab09eeee14f4488bbc26d94d9a01a/2.png)

## Taging

```bash
$ git tag -a <version> -m "<msg>"
$git show v2.0
```

## alias

```bash
$ alias logs="git log --oneline --all --graph --decorate"
```

## Branching

```bash
$git branch <"name">   #create branch
$git branch -m "main" #rename branch
$git branch -v  #show branch list
$git switch teting  #switch brtween branches || $git checkout
$git checkout -b [yourbranchname]  #create branch and switch to it at same time
$git merge <"name of branch i'm merging into master"? #i'm in master branch
$Git Rebase #like merge but make a linear sequence and much cleaner
$git branch --merged #show branches that had merged into master
$git branch -d <"name"> #delete branch
```

---

# **remote**

## clone

```bash
$git clone <"path"> <"name">  
$git remote -v #show remote details
$git fetch origin    #pull updates from remote - requiers $git merge
$ git pull origin    #fetch and merge in one step

$git push -u origin <"my current branch"> #update the remote 
-------------------
**#to push into remote i should be in deffrent branch before pushing** 
$git push --all #Push all of your local branches to the specified remote.

```

---

### astrics

```bash
$rm *hassan # remove any thing end with hassan
```

---

# GitHub

## github https

after creating empty repo

```bash
echo "# newrep" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main #change branch master name to main
git remote add origin https://github.com/hassanelhllos2020/newrep.git
$ git remote rename origin dest #Change remote name from 'origin' to 'desti'
$ git remote rm destination     #remove remote
git push -u origin main

```

## ssh

[https://github.com/settings/keys](https://github.com/settings/keys)

[Generating a new SSH key and adding it to the ssh-agent - GitHub Docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

---

1- one the local git 

 

```bash
ssh-keygen -t ed25519 -C "hassanelhllos@.com"
```

2- after runnig this code and hit enter 3 times,

> **it creates two files**
> 
> 
> Your identification has been saved in /c/Users/HASSA/.ssh/id_ed25519
> Your public key has been saved in /c/Users/HASSA/.ssh/id_ed25519.pub
> 

3- show the public key

```bash
$cat ~/.ssh/id_ed25519.pub
```

4- add shh key from github setting

5- on bash

```bash
$ git remote add origin git@github.com:hassanelhllos2020/newrep.git
```

---

## how to contribute

1- do a fork to the repo

2- clone the forked repo , and add remote the original repo

3- do edits and push to my forked repo

4- pull request

# **تمت بحمد الله**
