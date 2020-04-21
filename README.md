# Git

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://github.com/aboelkassem/Git/blob/master/Git.pdf)

**The Content**


- [Version Control System](#version-control-system)
- [Three Stages of a File](#three-stages-of-a-file)
- [Three States of git project](#three-states-of-git-project)
- [Command Line](#command-line)
  * [Tracked files by git has three stages](#tracked-files-by-git-has-three-stages)
  * [Untracked Files](#untracked-files)
  * [Push committed changes to Origin Master branch](#push-committed-changes-to-origin-master-branch)
  * [Track commits and see the history of previous commits](#track-commits-and-see-the-history-of-previous-commits)
  * [Commit Message](#commit-message)
  * [Remove and Move Files](#remove-and-move-files)
  * [Branches](#branches)
  * [Merge](#merge)
  * [Git stash](#git-stash)
  * [Git reset](#git-reset)


## What is Git?

##### Version Control System
- Software designed to record changes to files over time
- Ability to revert back to previous file version or project version
- Compare changes made to files from one version to another
- Version control any plain text file not just source code

## Three Stages of a File

- Committed
mean that files is stored safely in repo of the project
- Modified
when make changes in last commit, just introduced new changes but has committed them yet
- Staged
when changes finished and ready to commit.

## Three States of git project
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/250e9652-aa36-4973-aac8-0d9de42ce9aa/vlcsnap-2020-04-19-17h00m49s358.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200421%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200421T153833Z&X-Amz-Expires=86400&X-Amz-Signature=cf85fe146f27ad3dcb16d9607a7d1451057a0c050113c8f33a1ff73555c98b37&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22vlcsnap-2020-04-19-17h00m49s358.png%22)

## Command Line

> [github-git-cheat-sheet.pdf](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)

> [git-docs-all-commends](https://git-scm.com/docs/git#_git_commands)

### Tracked files by git has three stages
+ Committed
Unmodified changes from the last commit snapshot, when make changes to these files
content then moved to modified stage
+ Modified
Changes made to files since last commit snapshot, when you satisfied with changes and
stage them for commit will move to staged area
+ Staged
Changes marked to be added into the next commit snapshot, now can commit it to origin
repositories

### Untracked Files


mean that git sees a new file that didn't exist in her last commit. and add them to stage are to
be ready to commit


```
$ git status
$ git status --short
```
> This commend show the status of tracked and untracked files for your local and remote origin repository
```
$ git diff
$ git diff --staged
```

 this commend answer the following two questions

> 1- What changes have I staged that are ready to be committed?

> 2- What changes have I made but not yet staged?

![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/6b5308b7-7582-420b-99d1-54bd104122d3/vlcsnap-2020-04-21-11h09m20s731.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200421%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200421T154954Z&X-Amz-Expires=86400&X-Amz-Signature=248cd4f6f7f2a0a408efc7e828ea5b50d7463d1e0ef14458f6f98dcc824dbc14&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22vlcsnap-2020-04-21-11h09m20s731.png%22)
### Push committed changes to Origin Master branch
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/115b331e-0b74-4679-b31d-970a81149d58/vlcsnap-2020-04-21-11h33m34s653.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200421%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200421T155115Z&X-Amz-Expires=86400&X-Amz-Signature=4223bb92f5a67f5998da0fb9794402d3bb3e8cb5933ebb17c3512147d10390fd&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22vlcsnap-2020-04-21-11h33m34s653.png%22)

After Commit push these files from local project to remote origin repository on github

```
$ git push origin master
$ touch <file_name> # create a new file
```
### Track commits and see the history of previous commits
```
$ git log
$ git log -1
$ git log --oneline
$ git log --stat
$ git log --patch
```
### Commit Message

There are guidelines are followed to commit message to be useful and helpful to other
contributors there are blog that had a lot of information about these seven rules in [this blog](https://chris.beams.io/posts/git-commit/)

> 1- Separate subject from body with a blank line
> 2- Limit the subject line to 50 characters
> 3- Capitalize the subject line
> 4- Do not end the subject line with a period
> 5- Use the imperative mood in the subject line
> 6- Wrap the body at 72 characters
> 7- Use the body to explain what and why vs. how
### Remove and Move Files

```
$ git rm <file-name> # remove file from project and git untracks it
$ git rm --cached <file-name> # only git untracks it but keeping in local repo$ git mv <old-file-name> <new-name> # to rename file
$ git reset head <file-name> # to stop tracking this file
```
### Branches

branches to organize your code to adding new features or working separately from base code
and merge this after finishing or creating pull request. especially working with multiple collaborators to get a copy of version and work in it and merge it This tool is animate to understanding branching in git
```
$ git checkout <name-of-new-branche> # working/switching on new_branch and commit to it
$ git checkout -b <name-of-new-branch> # creating and working/switching on new_branch and commit to it
$ git checkout master # working/switching in master brance
$ git branch # list of branches do you have
$ git branch <name-of-branche> # create new branch but don't switch to it (checkout)
$ git branch -m <old-name> <new-name> # rename a branch
$ git branch -d <branch-name> # delete a branch
$ git branch -D <branch-name> # Force delete a branch if this branch have commits do not merged yet
```
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/e46f79f1-7c12-4027-9d92-6723ad0a0d3c/Capture.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200421%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200421T155756Z&X-Amz-Expires=86400&X-Amz-Signature=e20fc32f2eae9de3b9b62fb1aa9c3c6e48b023cfe8cf59a772e4832a968f5870&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Capture.png%22)

### Merge

merge command it to merge branches with all it's commits and working files to master branch. if you are contributor you can make branches and working at them and merge them as pull request to your master branch and send it to origin master branch as also pull request to be merged
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/14e74003-287d-44d9-a8bd-ffa20fd5230d/Capture.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200421%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200421T155819Z&X-Amz-Expires=86400&X-Amz-Signature=620398267dfef3ab03806118c089399c8c40dfb0d1c2cf59e9e95ed1ec037a99&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Capture.png%22)

### Git stash
git stash temporarily shelves (or stashes) changes you've made to your working copy. The git stash command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy
```
$ git stash # saving our working directory and staging area as a secert box
$ git stash list # get list a stashes or progress chages that we've stashed
$ git stash pop # get the chages/files from stash to dropped back into his working directory
```
### Git reset
git reset allow us move commits from history back into our working or staging area
![](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/4b2b793f-e882-4bfa-8ada-3a6e089c0840/vlcsnap-2020-04-21-16h01m05s279.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200421%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200421T160037Z&X-Amz-Expires=86400&X-Amz-Signature=28c0944c4f445adec5b30735c93678a03e8640b7709747f1c4e1ed407c565bf5&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22vlcsnap-2020-04-21-16h01m05s279.png%22)
```
$ git reset --soft <head-of-commit>
$ git reset --mixed <head-of-commit>
$ git reset --hard <head-of-commit>
```
