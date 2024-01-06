GIT & GITHUB BASIC TO ADVANCE

Some useful commands that needs to be there always to see everything works fine 

- Git Started

$ git --version(to check if git is installed or not)
$ git init(to initialize any repository)
$ git status(to check the status of your repo, files which are changed are acknowledged here)

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