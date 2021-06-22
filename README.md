# How to use git

This guide is sarcastic. Of course we all love git! git is very easy to use. You just have to learn 1024 different commands.

## Basics


In order to install a project on your computer, open a terminal in the folder you put all your projects. Write 

`git clone 'address'` 


Whereever you want to work, open a terminal in the folder of your project. First, in order to get all the changes made by your colleagues, `run git pull`.
    Work locally as you are used to work. When you think that you made some progress that you want to stamp, run `git commit -a -m "I added a new section"`.
    When you want to share all your committed work with your colleagues, run `git push`. In `git` the commit and the push phases are distinct, otherwise it would have been too simple.

For removing a file, simply remove it! That is may too complicated, they should have invented a special command for that, but no, this time, it is simple.
   For adding a file that you want git to keep track, run `git add miaou.txt` where `miaou.txt` is the file you want to add.
   
  
  
## Git pull

Sometimes `git pull` is made difficult. Do you know why? Because `git` opens a `vi` interface! `vi` is a very super-easy intuitive text editor, and it is so obvious that quitting `vi` is by pressing Ctrl + XW (I think). `git` could have been coupled by default with another text editor, or could have embedded its own editor, but they preffered to choose the best super-easy intuitive text editor: `vi`.
   
  
## Conflicts

 Sometimes, the system indicates that you have made changes that differ from what your colleagues have done. In that case, do `git pull` before.
    Sometimes, there are conflicts meaning that you and some other colleagues worked on the same part of the project. Some file contains portions like:
   
    `<<<<<<< HEAD`
        `what you have on your computer`
    `=======`
       `what others have done`
    `>>>>>>> cbc151ae7fa34600f830302e52d85d6109aab9c7`
    
 (do not ask me what is `cbc151ae7fa34600f830302e52d85d6109aab9c7`, git should remain a bit obscure ;) )
    
   In that case, just edit the files and keep the version of the lines you like. Remove the ugly lines `<<<<<<< HEAD`, `=======` and `>>>>>>> cbc151ae7fa34600f830302e52d85d6109aab9c7`. Also, in order to solve conflicts, I strongly recommend to use Visual Studio Code for editing text files, because solving conflicts is as easy as clicking!
   In case of conflicts, if they are solved, simply do `git commit -a -m "conflict solved"` and `git push`. I do not know what happens if your file contains lines `<<<<<<< HEAD`, `=======` and `>>>>>>> cbc151ae7fa34600f830302e52d85d6109aab9c7` on purpose. It would be very interesting to know which lines are the real content of the files and which are the new lines inserted by git. Hum... no it is not interesting.



## SSH keys

I think it is more convenient to work with SSH keys. The only thing is to know the magic command for creating your own SSH keys.
Run `ssh-keygen -t rsa -b 4096`.



## Branches

Branching is a nice mechanism, but its use is counterintuitively simple. For instance, if you want to list the existing branches, but to branch, use `git branch`. Yes! `git branch` does not branch, otherwise the name of the command would have been to transparent. A command like "git list-branch" would have been too crystal clear. 

To create a branch, do `git branch <nameofmybranch>`. (yes that is the same command... we could have imagined "git newbranch ..."). 
To move to a branch, we could have imagined "git changebranch ..." or "git gotobranch ...", but no.. it is `git checkout <nameofmybranch>`. 

<img src="branchmasteramazingfix.png" height="300px"/>





Suppose you have a branch called `amazingfix` and you want to include this amazing fix into the main branch `master`. Proceed as follows:
- goto branch `master` via `git checkout master`
- rappatriate the new amazing fix `git merge amazingfix`





## Specific questions

### How do I know what is the address of the repository?

Run `git remote -v`.


### I changed the name of a repository on github. How do I say to my local folder the new address of the repository?

Run  `git remote set-url origin blablablabla` where `blablablabla` is the address of the repository. For instance, run `git remote set-url origin git@github.com:tableaunoir/tableaunoir.git`.







### How do I change messages in previous commit?

To change the message of the *last* commit, run `git commit --amend -m "New commit message"`. Otherwise, read the manual because git is too user-friendly.


### Error when push!

Sometimes, you push `git push` and you get:

`error: src refspec refs/heads/master matches more than one`
`error: failed to push some refs to 'git@github.com:tableaunoir/tableaunoir.git'`

These error messages are very explicit (joke). In clear, it usually means that a branch and a tag have the same name. Just delete/rename tag. You can rename/delete tags in the interface of github. Also, some releases may be generated so maybe a script is running and keeps generating some tag with the same name than a branch.



