# Git Basic Command

![img](https://upload.wikimedia.org/wikipedia/commons/3/3f/Git_icon.svg)

## Setup Git
```git config --global user.name "yourname"```

```git config --global user.email "mail@domain.com"``` : setting up email

```git config --global color.ui auto``` : enable color in command line

## Create Repo

```git init``` : create a local repo system will be create .git in directory

```git clone URL``` : clone repo from remote server (Github/Bitbucket) to local

## Local Repo

```git status``` : check status

```git add FILENAME``` : add FILENAME to staging ready for commit

```git add .``` : add all file to staging when edit or change

```git diff``` : show files change

```git diff FIRST_BRANCH SECOND_BRANCH``` : compare between branch1 and branch2

```git log``` : show list log history

```git log --online``` : show log history single line

```git commit -m "Message"``` : commit staged and save into Project History

## Remote Repo

```git push origin master``` :  push to remote repository

```git remote -v``` : list remote URL

```git remote rename origin destination``` : change remote name

```git remote rm REMOTE_NAME``` : remove remote repository

## Branch

```git branch``` : show list all branch

```git branch BRANCH_NAME``` : create new branch

```git checkout BRANCH_NAME``` : change woring branch (move HEAD to new branch)

```git branch -d BRANCH_NAME``` : delete branch

```git merge BRANCH_NAME``` : combine code & history branch

## Undo

```git reset --hard HEAD``` : reset local repo

```git reset COMMIT``` : undo all then return COMMIT lastest

```git reset FILENAME``` : undo specific file

```git revert``` : undo and commit (deffrence reset will be  reset and return commit but revert will be create new commit)

## Remove

```git rm FILENAME``` : remove file and untracked file

```git rm --cached FILENAME``` : untracked file but not delete file

```git clean -df```: git clean removes all untracked files and git checkout clears all unstaged changes. (WARNING: while it won't delete ignored files mentioned directly in .gitignore, git clean -df may delete ignored files residing in folders.)

## Sync

```git fetch``` : check diffrence code change local and remote repo

```git pull``` : check code and merge code from remote to local

```git rebase``` : seem git merge but delete branch when code combined

## Generate SSH

```ssh-keygen -t rsa -C "mail@domain.com"``` : generate SSH Key then file was created and gen to  ~/.ssh/id_rsa

```ssh -T git@github.com``` : test SSH connection to remote GitHub
