# How to use git

git is very easy to use. You just have to learn 1024 different commands.

## Basics


In order to install a project on your computer, open a terminal in the folder you put all your projects. Write 

`git clone 'address'` 


Whereever you want to work, open a terminal in the folder of your project. First, in order to get all the changes made by your colleagues, `run git pull`.
    Work locally as you are used to work. When you think that you made some progress that you want to stamp, run `git commit -a -m "I added a new section"`.
    When you want to share all your committed work with your colleagues, run `git push`.

For removing a file, simply remove it!
   For adding a file that you want git to keep track, run `git add miaou.txt` where `miaou.txt` is the file you want to add.
   
   
## Conflicts

 Sometimes, the system indicates that you have made changes that differ from what your colleagues have done. In that case, do `git pull` before.
    Sometimes, there are conflicts meaning that you and some other colleagues worked on the same part of the project. In that case, edit the files and keep the version of the lines you like. In order to solve conflicts, I strongly recommend to use Visual Studio Code for editing text files, because solving conflicts is as easy as clicking!
    In case of conflicts, if they are solved, simply do `git commit -a -m "conflict solved"` and `git push`.



## SSH keys

I think it is more convenient to work with SSH keys. The only thing is to know the magic command for creating your own SSH keys.
Run `ssh-keygen -t rsa -b 4096`.



## Branches

`git branch` lists the existing branches (and does not branch, as its name says). To create a branch, do `git branch <nameofmybranch>`. (yes that is the same command... we could have imagined "git newbranch ...").
To move to a branch, we could have imagined "git changebranch ..." or "git gotobranch ...", but no.. it is `git checkout <nameofmybranch>`. 


Suppose you have a branch called `amazingfix` and you want to include this amazing fix into the main branch `master`. Proceed as follows:
- goto branch `master` via `git checkout master`
- rappatriate the new amazing fix `git merge amazingfix`





## Specific questions

### How do I know what is the address of the repository?

Run `git remote -v`.


### I changed the name of a repository on github. How do I say to my local folder the new address of the repository?

Run  `git remote set-url origin blablablabla` where `blablablabla` is the address of the repository. For instance, run `git remote set-url origin git@github.com:tableaunoir/tableaunoir.git`.




### How do I change the message of the last commit?

Run `git commit --amend -m "New commit message"`.




### Error when push!

Sometimes, you push `git push` and you get:

`error: src refspec refs/heads/master matches more than one`
`error: failed to push some refs to 'git@github.com:tableaunoir/tableaunoir.git'`

These error messages are very explicit (joke). In clear, it usually means that a branch and a tag have the same name. Just delete/rename tag. You can rename/delete tags in the interface of github. Also, some releases may be generated so maybe a script is running and keeps generating some tag with the same name than a branch.



