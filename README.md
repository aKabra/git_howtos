git_howtos
==========

This document is licensed under Apache License, version 2.0 (see http://www.apache.org/licenses/LICENSE-2.0)
Use this documentation at your own risk. I am not liable for any loss from the use of this document.

These commands have worked for me for my little git use. I perodically visit this list to refresh my memory.

Git help


1) Add only modified files. Do not add new files.
>git add -u

2) To revert local add:
>git reset HEAD

This will revert all the changes from the commit


3) Add a specific file
>git add RELATIVE_PATH_TO_FILE


4) Commit changes added with "git add"
>git commit -m "COMMENTS ABOUT THIS COMMIT"<br>


5) To Push commited changes to the remote
>git push


6) Forget a modification to a file
>git checkout -f RELATIVE_PATH_TO_FILE


7) Forget all modification to a branch
>git checkout -f HEAD


8) Create a new branch from another branch:

Switch to the source branch
>git checkout SOURCEBRANCHNAME

Create a new branch from the current branch
>git branch NEWBRANCHNAME

Switch to the new branch
>git checkout NEWBRANCHNAME

Create the NEWBRANCHNAME on the remote
>git push -u origin HEAD


9) Delete remote branch
>git push origin :BRANCHNAMETODELETE


10) Remove stale branches from remotes
>git remote prune origin


11) Merge one branch into another
>git merge BRANCHTOMERGE


12) Setup upstream for a forked repo.

List the current remotes
>git remote -v

Output:<br>
origin  https://github.com/user/repo.git (fetch)<br>
origin  https://github.com/user/repo.git (push)

Set a new remote
>git remote add upstream https://github.com/otheruser/repo.git

Verify new remote
>git remote -v

Output:<br>
origin    https://github.com/user/repo.git (fetch)<br>
origin    https://github.com/user/repo.git (push)<br>
upstream  https://github.com/otheruser/repo.git (fetch)<br>
upstream  https://github.com/otheruser/repo.git (push)


13) To checkout a branch that exists on remotes and set tracking do
>git fetch<br>
>git checkout BRANCHENAME


14) Delete a local branch
>git branch -D BRANCHNAME

15) Store credentials so that yu do not need to type them in again (helps when two step authentication is used with github):
>git config credential.helper store<br>
>git pull (or another command that will prompt the password)<br>
>Username: type your username here<br>
>Password: type your password here

16) Forget all local commits into the BRANCHNAME branch and replace the branch contents with the contents of remote (for example, if you accidentally merged some branch into the master, but then want undo that and get the original master back): 
>git checkout BRANCHNAME<br>
>git fetch<br>
>git reset --hard origin/BRANCHNAME<br>

17) Housekeeping for a local repo. It often makes the .git folder much smaller. However, it also makes it impossible to undo accidental hard resets.
>git gc

18) Roll back last commit, delete it from history, and forget about all the changes in it.
>git reset --hard HEAD~1

19) You created a local repository and also created an empty remote repository (with url https://github.com/user/repo.git). Now you want to push your local repo to the empty remote, do this:
> git remote add origin https://github.com/user/repo.git

Now you can push and pull your local repo to the remote.
