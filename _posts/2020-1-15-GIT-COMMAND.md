---
layout: post
title:  Helpful git Commands
---

push new branch

git push -u origin branch-name 


Git pull wants you to either remove or save your current work so that the merge it triggers doesn't cause conflicts with your uncommitted work. Note that you should only need to remove/save untracked files if the changes you're pulling create files in the same locations as your local uncommitted files.

rename Branch

git branch -m <new_name>


Remove your uncommitted changes

Tracked files

``git checkout -f``

Untracked files

``git clean -fd``

Save your changes for later
Tracked files
git stash

Tracked files and untracked files

``git stash -u``

Reapply your latest stash after git pull:

``git stash pop``

Changing the Last Commit: git commit --amend  is a convenient way to modify the most recent commit 
or append the files in same comments

 ``git commit --amend``

``git commit --amend -m "an updated commit message"``


**Git Rebase**

git status
 
git remote -v
 
git fetch upstream 
 
git rebase upstream/master

git status

git add Jenkinsfile


git rebase --continue

git diff master Jenkinsfile
 
git diff upstream/master Jenkinsfile
 
git push -f


 

-- 

   