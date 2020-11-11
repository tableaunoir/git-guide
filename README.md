# How to use git

## Address of the repository

### How do I know what is the address of the repository?

Run `git remote -v`.


### I changed the name of a repository on github. How do I say to my local folder the new address of the repository?

Run  `git remote set-url origin blablablabla` where `blablablabla` is the address of the repository. For instance, run `git remote set-url origin git@github.com:tableaunoir/tableaunoir.git`.


## Commits

### How do I change the message of the last commit?

Run `git commit --amend -m "New commit message"`.
