## GIT & GITHUB BASIC TO ADVANCE

Some useful commands that needs to be there always to see everything works fine 

## Git Started
- To check what version of git is installed
> $ git --version
- To initialize a local repo
> $ git init
- To check the status of your repo, files which are changed are acknowledged here
> $ git status

git status plays a vital role when you create a {.gitignore} file which consist of files and directory names which you want to be excluded from being uploaded to public repo

STAGING: a very essential which is a must to know, a repo is just a snapshot, one need to add files or onjects before we commit it. It is where files are added before this, files remains untracked.

> $ git add .(It will add all the untracked files to staging area)
> $ git reset .(It will take down the added files back to untracked way)
> $ git add FILENAME(Used to add specific files rather than adding everything)

> $ git commit -m "commit message"(This commits the added files to the repo and clean the repo for further use)


Now we are done with the git thing we can, now we need to collaborate with real world to know this we need to go to Github, Gitlab or bitbucket, there we can create a repo which act as remote repository and then we can connect that remote with our local using git remote command

> $ git remote(just to check the remote repo name)
> $ git remote add origin REPO-URL(here origin is the name you give to ur remote repo and URL u get after creating the repo)
> $ git remote(just to check more detailed view of remote repo)
> $ git remote show origin(gives everything you need to know)

> $ git push REMOTE-REPO-NAME BRANCH-NAME(it syncs local files with the remote repo)

Now we can look at the UI part where we can see different commits id which can be used to differnce it made to the files after each commit. 

In addition to this it is quite easy and handy that we can do changes from the github UI. But it will raise a commit ahead thing in the remote repo.

Now we need to sync our local repo with the changes we did using UI on remote repo.

- we need to fetch the changes
- we need to merge the branches of our local and remote repo.

> $ git fetch(it will fetch and download the changes to the local done on remote repo. But it won't reflect in our local repo)
> $ git merge REMOTE-BRANCH-NAME(It will merge the changes done on remote repo branch with the local repo branch)

## Fetch & Merge

Fetching and merging can be a tedious task to perform when you are working on a frequently changing codebase. git pull command got you covered. you can use this command to fetch and merge all at once. 

There are two ways to address this.

> $ git pull REMOTE-REPO-NAME BRANCH-NAME

second option is where we don't need to mention the remote-repo-name and branch-name it is done when you push your code with -u flag which upstreams your remote branch priority and when you fire this command it exactly knows what and where to pick from.

> $ git push REMOTE-REPO-NAME BRANCH-NAME -u

> $ git pull

Here comes the most tedious thing, while using pull command there are two things that needs to be taken care.

- Your local repo should have clean working directory, it should ideally commit the changes you did or move it to stash area.
- Your local repo and remote repo should not be changing same line. It creates merge conflicts.

##Cloning a repo

- This is part of copying the remote repo on your local system and then can use commands like pull to get the latest changes on that repo. Once remote repo is copied in the local we can use git log command to check the history of commits.

> $ git clone REMOTE-REPO-URL
> $ git log

## Github Codespaces

When working on a repo and you don't wanna go for copying everything to the local. Github provides you with a utility which looks like cloud based version of VS code. We can launch it by clicking period/dot(.)

It doesn't have terminal to work on, it will ask you to open in codespaces on your computer to access the terminal.

## Branching(Github Branches)

In github we can create branches to work on our piece of code independent of what code is already running, or without disturbing the main code. Once you are done with the code on your branch you can merge that branch code to the main code.

- You can create branch by following command

> $ git branch NEW-BRANCH-NAME

- You can see the branches, the branch you are in will highlighted with the branch name you created

> $ git branch 

- You can even delete a branch using flags along with command, but here is one crucial thing to understand the flag ```-d``` works in safe manner deleting branch which is not merged and not having any changes in it but ```-D``` will delete avoiding everything on the first place.

> $ git branch -d BRANCH-NAME

> $ git branch -D BRANCH-NAME

- You can even change the name of branch you are in using following command

> $ git branch -m BRANCH-NEW-NAME

## Switching Branches

- To switch to another branches, we can use following command

> $ git checkout BRANCH-NAME

- To create and checkout to a branch using one command

> $ git checkout -b BRANCH-NAME
 
- To checkout to previous branch you were in

> $ git checkout -

## Merge Conflicts or Merge fails

- Merge fails occurs when you are working on same code and the other person completed the code and asks you to merge his changes

> $ git merge BRANCH-NAME

- Here merge will fail if your current working directory has some uncommited things in it.

> $ git commit -am "message"

- Merge conflict occurs when more than one dev is working on same line of code and both have committed there work and now the owner wanna merge so one who is merging needs to either take his or other person changes. one command to see the difference is 

> $ git diff

- There is a possibility that the merge conflict is so huge at that time we can abort the merge by using following command

> $ git merge --abort

## Fork 

- Forking is wayy different than cloning, Cloning is the taking a copy of code from remote server to your local machine where as FOrking is a github thing where a copy of repo is made on your profile

- After forking one can clone the repo on local as before and start working in it.

- When you fork a repo, you have a link to original repo like clone but the best part is you can make that code as your own version and can write code to get things done moreover. The original repo is called as upstream repo from where we can get new updates made in original repository.

## Pull Request

- Pull request or merge request is something which address the same thing. It's like asking to look at my code and get it merged if it looks good to you.

- It has several steps when it comes to contributing to another repo or another organization

- Get yourself with a repo you wanna contribute on(very subjective to user).
- Fork the repo to get that repo copied to your github repo
- clone the repo in the local like we do for our own 

> $ git clone REMOTE-REPO-URL

- clone the repo which is copied to your github account not the original one, it is called upstream repo which is used to pull the changes when necessary.

- next create a branch from it.

> $ git branch BRANCH-NAME

- checkout to the branch

> $ git checkout BRANCH-NAME

- or do both at once

> $ git checkout -b BRANCH-NAME

- do the changes 

- add the files to the staging area

> $ git add FILE-NAME

- commit the changes

> $ git commit -m "commit message"

= or do everything with single command

> $ git commit -am "commit message"

- push to the remote repo

> $ git push REMOTE-REPO-NAME BRANCH-NAME

- As soon as we push our code we can see the compare and pull request button on our repo page in github. There we can read about the contribution guidelines and can generate pull request following the contribution guidelines.

## Must know things when working with the remote repository which either belongs to you or someone else.

- Always upstream the remote repo so you can pull the latest changes 

> $ git remote add upstream REMOTE-REPO-URL

- Use fetch command to fetch/download the changes on the upstream repo

> $ git fetch upstream

- Use rebase command to add upstream changes on top of our personal work.

> $ git rebase upstream/main

# Git Reset

- Case 1: file is insdie staging area: Git reset alone can move your file from staging area to current working directory

> $ git reset

- Case 2: File is committed: In such case we can use git reset command with the commit id which we can get by running git log command. Using the following command you will enter in the mixed mode where you will be moved to previous commit but files won't be deleted or changed. Head will be pointing to the previous commit.

> git reset COMMIT-ID

- Case 3: You wanna delete everything.

> git reset --hard COMMIT-ID

- NOTE: Git reset is good for working on local repo but not in remote because if we use ```--hard``` flag with the git reset command it will basically delete that commit and that commit will be lost.

## Git Revert

- When working on remote repo its safe to use ```git revert``` command rather than ```git reset``` because ```git revert``` command gives you back a commit id so that revert is never lost.

> $ git revert COMMIT-ID

## Git commit --amend

- Most of the time we don't look at the staging area and run for running combined command ```git commit -am "commit msg"```, to fix this we can use --amend flag with the ```git commit``` command. 

> $ git commit --amend -m "new message"

- it even got you covered if you missed adding files to staging area, you can do so using the ```git add FILENAME``` command then you can use ```--amend``` ```--no-edit``` flags

> $ git add .

- Post this you can look for adding these files to same commit which you did before. For that you need to use ```--no-edit``` flag along with ```git commit --amend``` command.

> $ git commit --amend --no-edit

## Stash

- Stash is about saving your work without actually commiting your work to remote repo and is very useful in long run when you actually need to get your working repo clean for pull/merge operations.

- Stash maintains an array of your code changes when you exactly run ```git stash``` command. 

> $ git stash 

- To apply your stashed changes you can run the following command:

> $ git stash pop

- But pop command will apply the most recent changes that we did. So let's give stash a name, to assign a name use following command.

> $ git stash save STASH-NAME

- To get the list of stash your local repo is holding, use following command:

> $ git stash list

- To apply the stash you need to run floowing command along with the number you see which is nothing but the stash index:

> $ git stash apply STASH-INDEX-NUMBER

## Rebase

- Rebase is very powerful when you don't wanna merge things up as you are working on your branch. You can sync with the main branch by rebasing it over your branch. All it will do it will rewrite the history of commits as you started from where you rebased it. That means you don't need to do merge commits

> $ git rebase master/main(depend on your master branch name, use any one)

## Squash

- Squash is a strategy that one could follow to merge commits as one once everything is done. Moreover, we can utilize the ```git rebase``` command with ```--interactive``` flag to achive so.

> $ git rebase main --interactive

- It will make you enter in the interactive mode, where you can see the commits you did followed by PICK, The command you wanna squash, change ```PICK``` to ```SQUASH```

## Github Actions

- Actions are the part of github which can be setted up manually using bunch of codes as well as some already templates are written which could be used for getting the work done. 

- Actions are the reusable piece of codes that can be used for creating workflows for your project. 

## Github pro tips