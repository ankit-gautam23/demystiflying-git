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

