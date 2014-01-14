git_howtos
==========
That's some howtos that I find useful for somebody who does not use git every day.

Git help
1) To revert local add:
git reset HEAD
This will revert all the changes from the commit

2) Create a new branch from another branch:
Switch to the source branch
>git checkout SOURCEBRANCHNAME

Create a new branch from the current branch
>git branch NEWBRANCHNAME

Switch to the new branch
>git checkout NEWBRANCHNAME

Create the NEWBRANCHNAME on the remote
>git push -u origin HEAD

3) Delete remote branch
>git push origin :BRANCHNAMETODELETE

4) Add a specific file
>git add RELATIVE_PATH_TO_FILE

5) Remove stale branches from remotes
>git remote prune origin

6) Merge one branch into another
>git merge BRANCHTOMERGE

7) Setup upstream for a forked repo.
List the current remotes
>git remote -v
origin  https://github.com/user/repo.git (fetch)
origin  https://github.com/user/repo.git (push)

Set a new remote
>git remote add upstream https://github.com/otheruser/repo.git

Verify new remote
>git remote -v
origin    https://github.com/user/repo.git (fetch)
origin    https://github.com/user/repo.git (push)
upstream  https://github.com/otheruser/repo.git (fetch)
upstream  https://github.com/otheruser/repo.git (push)

8) To checkout a branch that exists on remotes and set tracking do
>git fetch
>git checkout BRANCHENAME

9) Delete a local branch
git branch -D BRANCHNAME

10) Add only modified files. Do not add new files.
>git add -u

11) Commit changes and put them to remote
>git commit -m "COMMENTS ABOUT THIS COMMIT"
>git push


