# __Commands in Git and Terminal__

## __TERMINAL__

---

## __Typical commands__

#### cd foldername 
* get into the folder you want to work in, can be a repo or a folder in a repo

#### ls 
* see the files (and folders) in the folder you are in

<br />

#### Get into your virtual environment
* also needed when you want to create or edit file(s) in VSC, otherwise you cannot select the Kernel

    __pyenv local 3.9.4__

    __python -m venv .venv__

    __source .venv/bin/activate__

    __pip install --upgrade pip__

<br />

#### git status

always a good idea, here you can see if you modified or created file, different stati (untracked, tracked, staged, unstaged)


* __Git status__ "Changes not staged for commit: here in red --> _file.xxx_ is modified"

* __Git commit -m "your new comment"__ (this comment is visible on Git behind your file name!)
        "Changes not staged for commit: modified: file.xxx"

* __Git status__ "changes not staged for commit: modified: _file.xxx_"

* __Git add__ _file.xxx_ (your file is staged but not committed)

* __Git restore --staged__ _file.xxx_ (your file is unstaged now)

* __Git add__ _file.xxx_ (tracked file)

* __Git rm --cached__ _file.xxx_ (untracked file)

* __Git rm__ _file.xxx_ (removes your file, you can do it when you don't want this file but it is on Git and you deleted it in your folder on your Mac)

---

## __Working steps__
---

### __Start in Git with a new repo and then switch to Terminal: Work with Git Clone__
* Copy the SSH code from your repo or the one you forked in GitHub 
* Paste it into your Terminal with __git clone__ 'git@github.com:yourprofilename/yournewrepo.git'
* Create a new switch to a branch locally: __git switch -c <new_branch>__
* Get into your .venv (see above)
* Install packages if needed - e.g. for Plotly (see [commands folder](https://github.com/IronMan2483/All_About_Basics/blob/main/Commands/Commands_Import.md))
* Open VSC with __code .__ or Jupyter Notebook with __Jupyter Lab__ to work on the files

---

### __Save your work - Step 1 in Terminal__
* __git status__ what has changed?
* __git add__ _file.xxx_ or _*.ipynb_ or _folder/_
* __git commit -m "comment"__

<br />

* __git switch -c newbranch__ 

    * if you are still in main you need to switch before you can push
    * if you are already in the new branch you can push from here
    
<br />

* __git push__
    * if you have done it right you should see an push upstream link you need to c&p in your next line

---

## __GIT__
---

### __Save your work - Step 2 in Git__
* Go to your Git repo on Git
* If you have done everything right you will see a yellow block with your branch name you pushed from and that this is a pull request

#### __GOOD PUSH__
* Go to the Pull Request
* Go to files changed and click on merge (take care that it is the right "main branch" in which your branch will merge in!!!)
* If you have done everything right before you will see a green button with "squash and merge"
* Click 2 times on the button
* Delete the branch

    #### __Yeah!!! You made it!__


![Angry Panda](https://github.com/IronMan2483/All_About_Basics/blob/main/Images/Angry_Panda.gif)



#### __BAD PUSH or MERGE CONFLICT__
* Go to the Pull Request
* Go to files changed and click on merge (take care that it is the right "main branch" in which your branch will merge in!!!)
* __OMG! You have a merge conflict you need to resolve! Don't cry!!!__
* Click on the conflict
* You will see the file with the conflict and click on the conflicts (you should see text in yellow brackets "main" version and "new branch" version)
* You need to delete the "old version" including the lines with the "main" version and "new branch" version
* You should be able to click now on the button "resolve problem"
* You are now able to merge __YEAH!!!__
* You will see now the green button with "squash and merge" 
* Click 2 times on the button
* Delete the branch

    #### __Yeah!!! You made it!__
---

## __TERMINAL__
---
### __Save your work - Step 3 in the Terminal__

* __git switch main__

* __git pull__ your branch is now updated

---


Check also my protocol in the DS neue fische bootcamp from day 5: [protocol](https://github.com/neuefische/hh-data-21-3-daily-review/blob/main/protocols/protocol_day5.md)