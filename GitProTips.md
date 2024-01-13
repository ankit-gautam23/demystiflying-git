## Combining add and commit

1. one way was using ```git commit -am "commit-msg"```
2. Another could be creating aliases
```bash
> $ git config --global alias.ac "commit -am"
```
This will create a alias for ```commit -am``` as ```ac```. It can be used as follows
```bash
> $ git ac "commit-msg"
```
## Command when you messed up with your last commit msg
```bash
> $ git commit --amend -m "new-commit-msg"
```
if you mistakingly forgot to add some file to staging area, following command could help without even changing the previous commit msg. 
```bash
> $ git add .
> $ git commit --amend --no-edit
```
Always remember --amend is useful when you haven't pushed your code. and if you did you need to forcefully push the code using following command
```bash
> $ git push origin master --force
```
This will rewrite the history of remote commits with reference to local commit. But you will lose the commits of remote branch.

## Command to revert the changes on the remote repo

revert command helps you to undo your commit with the new commit. it takes you one commit back.
```bash
> $ git revert better-days
```
## Hack to save your work without being commiting on the git

The best way to stash it from where you can pick it and apply with respect to your need.
```bash
> $ git stash 
```
to apply we use pop command
```bash
> $ git stash pop
```
- Let's imagine you have different ways to implement same thing and you wanna stash everything, stash command got you covered.

1. save your stash with a name
```bash
> $ git stash save stash-name
```
2. You can check the index of your index name which will be needed to apply exact stash
```bash
> $ git stash list
```
3. Last but not the least, command to apply the desired stash
```bash
> $ git stash apply stash-index
```
## checking the git log made easier using some flags
```bash
> $ git log --graph --oneline --decorate
```
## We can even tag our commit as good or bad while getting back to previous stage
```bash
> $ git bisect start

> $ git bisect bad

> $ git bisect good
```
## Working on a feature with too many commits, let's squash it down to one commit

- You want the final commit as commit
```bash
> $ git rebase master/main --interactive
```
It will open a file with all the options like ```pick``` to pick the commit you wanna merge all with, ```sqash``` which gives you option to squash(merge) the commits with the commit you picked, if you don't want combined commit you can use ```fixup``` to not mixup all the commit msg

### Another way to use squashing or fixup is wiht the commit command
```bash
> $ git commit --fixup commit-id

> $ git commit --squash commit-id
```
these can be utilized when you are using ```autosquash``` while rebasing
```bash
> $ git rebase -i -autosquash
```
## Maintaing a repo can be tedious so what could be useful here ```Hooks```

Hooks are the scripts which runs before and after any event happens and you are the one who can configure these hooks to deliver to your business requirements.

## So let's destroy things before it gets out of hand.

Let's say I have a remote repo I cloned and workign on it and I messed up everything. A proper way to do everything is

I will get back to original state of remote repo
```bash
> $ git fetch origin

> $ git reset --hard origin/main
```
- To remove the untracked file
```bash
> $ git clean -df
```
- To remove everything, you can remove hidden .git folder
```bash
> $ rm -rf .git
```
