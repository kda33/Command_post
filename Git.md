# Git commands
##### Remote git repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git remote -v
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
##### Time machine
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git reflog
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
##### Git add and git commit
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git commit -am 'text'
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
##### Git Magic
###### To get the latest commit of your repository:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git log -1
(out) commit 18101e645ee3d9b1de302164bb31f907a8282349 (HEAD -> master, origin/master, origin/HEAD)
(out) Author: John Doe <john@doe.com>
(out) Date:   Mon Sep 25 16:29:48 2017 +0200
(out) 
(out)     Render magic in front page

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
###### That's great information but quite verbose. Trim it down to just get the hash from the last commit:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git log -1 --pretty=%H
(out) 18101e645ee3d9b1de302164bb31f907a8282349
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
###### You can even get a shorter version of the hash but I prefer the other one:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git log -1 --pretty=%h
(out) 18101e6
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### This command sets the author name and email address respectively to be used with your commits.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git config –global user.name “[kda33]”
git config –global user.email “[kda33@gmail.com]”
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command is used to start a new repository.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git init [repository name]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command is used to obtain a repository from an existing URL.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git clone [url]
git clone https://github.com/kda33/Terraform
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command adds a file to the staging area.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git add [file]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command adds one or more to the staging area.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git add *
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command records or snapshots the file permanently in the version history.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git commit -m “[ Type in the commit message]”
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command commits any files you’ve added with the git add command and also commits any files you’ve changed since then.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git commit -a
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command shows the file differences which are not yet staged.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git diff
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command shows the differences between the files in the staging area and the latest version present.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git diff –staged
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command shows the differences between the two branches mentioned.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git diff [first branch] [second branch]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command unstages the file, but it preserves the file contents.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git reset [file]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command undoes all the commits after the specified commit and preserves the changes locally.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git reset [commit]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command discards all history and goes back to the specified commit.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git reset –hard [commit]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command lists all the files that have to be committed.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git status
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command deletes the file from your working directory and stages the deletion.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git rm [file]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command is used to list the version history for the current branch.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git log
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command lists version history for a file, including the renaming of files also.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git log –follow[file]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command shows the metadata and content changes of the specified commit.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git show [commit]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command is used to give tags to the specified commit.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git tag [commitID]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command lists all the local branches in the current repository.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git branch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command creates a new branch.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git branch [branch name]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command deletes the feature branch.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git branch -d [branch name]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command deletes the remote feature branch.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git push origin --delete feature-branch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command is used to switch from one branch to another.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git checkout -b [branch name]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command sends the committed changes of master branch to your remote repository.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git push [variable name] master
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command sends the branch commits to your remote repository.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

git push [variable name] [branch]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command pushes all branches to your remote repository.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git push –all [variable name]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### This command fetches and merges changes on the remote server to your working directory.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git pull [Repository Link]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Undo changes in file app.py
##### File state reverted to previous commit
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git restore app.py
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
