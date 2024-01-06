GIT & GITHUB BASIC TO ADVANCE

Some useful commands that needs to be there always to see everything works fine 

# Git Started
- To check what version of git is installed
> $ git --version
- To initialize a local repo
> $ git init
- To check the status of your repo, files which are changed are acknowledged here
> $ git status

git status plays a vital role when you create a {.gitignore} file which consist of files and directory names which you want to be excluded from being uploaded to public repo

STAGING: a very essential which is a must to know, a repo is just a snapshot, one need to add files or onjects before we commit it. It is where files are added before this, files remains untracked.

$ git add .(It will add all the untracked files to staging area)
$ git reset .(It will take down the added files back to untracked way)
$ git add FILENAME(Used to add specific files rather than adding everything)

$ git commit -m "commit message"(This commits the added files to the repo and clean the repo for further use)


Now we are done with the git thing we can, now we need to collaborate with real world to know this we need to go to Github, Gitlab or bitbucket, there we can create a repo which act as remote repository and then we can connect that remote with our local using git remote command

$ git remote(just to check the remote repo name)
$ git remote add origin REPO-URL(here origin is the name you give to ur remote repo and URL u get after creating the repo)
$ git remote(just to check more detailed view of remote repo)
$ git remote show origin(gives everything you need to know)

$ git push REMOTE-REPO-NAME BRANCH-NAME(it syncs local files with the remote repo)

Now we can look at the UI part where we can see different commits id which can be used to differnce it made to the files after each commit. 

In addition to this it is quite easy and handy that we can do changes from the github UI. But it will raise a commit ahead thing in the remote repo.

Now we need to sync our local repo with the changes we did using UI on remote repo.

- we need to fetch the changes
- we need to merge the branches of our local and remote repo.

$ git fetch(it will fetch and download the changes to the local done on remote repo. But it won't reflect in our local repo)
$ git merge REMOTE-BRANCH-NAME(It will merge the changes done on remote repo branch with the local repo branch)

# Fetch & Merge

Fetching and merging can be a tedious task to perform when you are working on a frequently changing codebase. git pull command got you covered. you can use this command to fetch and merge all at once. 

There are two ways to address this.

$ git pull REMOTE-REPO-NAME BRANCH-NAME

second option is where we don't need to mention the remote-repo-name and branch-name it is done when you push your code with -u flag which upstreams your remote branch priority and when you fire this command it exactly knows what and where to pick from.

$ git push REMOTE-REPO-NAME BRANCH-NAME -u

$ git pull

Here comes the most tedious thing, while using pull command there are two things that needs to be taken care.

- Your local repo should have clean working directory, it should ideally commit the changes you did or move it to stash area.
- Your local repo and remote repo should not be changing same line. It creates merge conflicts.

#Cloning a repo

- This is part of copying the remote repo on your local system and then can use commands like pull to get the latest changes on that repo. Once remote repo is copied in the local we can use git log command to check the history of commits.

$ git clone REMOTE-REPO-URL
$ git log

# Github Codespaces

When working on a repo and you don't wanna go for copying everything to the local. Github provides you with a utility which looks like cloud based version of VS code. We can launch it by clicking period/dot(.)

It doesn't have terminal to work on, it will ask you to open in codespaces on your computer to access the terminal.

# Branching(Github Branches)

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

# Switching Branches

- To switch to another branches, we can use following command

> $ git checkout BRANCH-NAME

- To create and checkout to a branch using one command

> $ git checkout -b BRANCH-NAME
 
- To checkout to previous branch you were in

> $ git checkout -

raising merge conflict
