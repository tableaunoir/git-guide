# How to use git

git is very easy to use. You just have to learn 1024 different commands.

## SSH keys

Run `ssh-keygen -t rsa -b 4096`.

## Address of the repository

### How do I know what is the address of the repository?

Run `git remote -v`.


### I changed the name of a repository on github. How do I say to my local folder the new address of the repository?

Run  `git remote set-url origin blablablabla` where `blablablabla` is the address of the repository. For instance, run `git remote set-url origin git@github.com:tableaunoir/tableaunoir.git`.



## Commits

### How do I change the message of the last commit?

Run `git commit --amend -m "New commit message"`.




## Push

Sometimes, you push `git push` and you get:

`error: src refspec refs/heads/master matches more than one`
`error: failed to push some refs to 'git@github.com:tableaunoir/tableaunoir.git'`

These error messages are very explicit (joke). In clear, it usually means that a branch and a tag have the same name. Just delete/rename tag. You can rename/delete tags in the interface of github. Also, some releases may be generated so maybe a script is running and keeps generating some tag with the same name than a branch.


## Branches

`git branch` lists the existing branches (and does not branch, as its name says). To create a branch, do `git branch <nameofmybranch>`. (yes that is the same command... we could have imagined "git newbranch ...").
To move to a branch, we could have imagined "git changebranch ..." or "git gotobranch ...", but no.. it is `git checkout <nameofmybranch>`. 


Suppose you have a branch called `amazingfix` and you want to include this amazing fix into the main branch `master`. Proceed as follows:
- goto branch `master` via `git checkout master`
- rappatriate the new amazing fix `git merge amazingfix`

