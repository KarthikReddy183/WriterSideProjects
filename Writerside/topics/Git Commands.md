# Topic title

## Git commands and it's usages 



## Commit message command
`git commit -m "android"`

## Git command to check the commit ID
`git log`

## What is the use of amend command 
git commit --amend

## Git command to squash multiple commit into one
git rebase -i HEAD~2 -> 2 is for two commits, number can be changed based on requirement
Also when we enter sqaush mode, make sure to pick which commit you want as parent and all children must be marked with 's' instead of 'pick'

## Git command to create a patch for changes made recently without committing the changes
`git diff > name_of_file.patch` -> [https://stackoverflow.com/questions/5159185/how-to-create-a-git-patch-from-the-uncommitted-changes-in-the-current-working-di ](https://stackoverflow.com/a/15438863/22389280) 


## Git command to create a patch of a commit
`git format-patch -1  commit id`
`git format-patch -1 HEAD`
## The -1 flag indicates how many commits should be included in the patch
https://stackoverflow.com/questions/6658313/how-can-i-generate-a-git-patch-for-a-specific-commit 


## Git command to check the status of changes
`git status`
`git status .` -> ## To check the modified files from current directory

## Git command to add all the files which has been changed 
`git add .`

## Git command to undo the last commit done and get back to original changes 
`git reset HEAD~`

`https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git`

## Git command to fetch from a specific branch 
`git fetch origin branch name`


## Git command to apply a patch 
`git apply name-of-file.patch`
https://stackoverflow.com/questions/2249852/how-to-apply-a-patch-generated-with-git-format-patch

## Git commnad to check if there are any errors before applying a patch 
git apply --check a_file.patch

## Git command to restore the original version of a file which has been modified
`git restore filename`

## Git command to remove or force remove untracked file which have not been added yet 
`git clean -f`

## Git command to revert an applied patch 
`git apply -R file name`
`https://stackoverflow.com/questions/34400885/how-can-i-remove-an-applied-git-patch`
