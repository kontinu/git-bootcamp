# Cheat Sheet



# ----------------------------------------------------------------- #
REFERENCES
# ----------------------------------------------------------------- #

http://ndpsoftware.com/git-cheatsheet.html

# ----------------------------------------------------------------- #
BASIC
# ----------------------------------------------------------------- #

# create a new git repo
` git init`

# to check the status of your files
` git status`

# ----------------------------------------------------------------- #
NEW FILES
# ----------------------------------------------------------------- #

# remove all untracked files and directories
` git clean -df`

# add new file to staging
` git add <filename>`

# remove new file from staging - file is no longer tracked
` git rm --cached <filename>`

# rename or move a staged file
` git mv <oldfile> <newfile>`

# commit staged files to local repository
`git commit -m 'commit message'`

# ----------------------------------------------------------------- #
MODIFIED FILES
# ----------------------------------------------------------------- #

# add modified file to staging
`git add <filename>`

# undo changes made to modified file in workspace
`git checkout <filename>`

# remove file from staging - but the workspace file is still modified
`git reset HEAD <filename>`

# there are modifed files in workspace and staging that need to be reverted back to the last commit
`git reset --hard`

# if you have made mulitple commits, but the last few were bad and you want to rollback to a previous commit
`git log`
`git reset --hard <commit-sha1>`

# ----------------------------------------------------------------- #
REMOTES
# ----------------------------------------------------------------- #

# you created a remote on github and want to link it to your local repository
`git remote add origin <name-of-remote>`

# view all of your remotes
`git remote -v`

# you want to push changes from your master branch up to github
`git push origin master`

# you want to merge changes into your current branch from the remote branch named master
`git pull origin master`

# you pushed a lot of bad commits to github that you want to rollback
`git log`
`git reset --hard <commit-sha1>`
`git push -f origin master`

# ----------------------------------------------------------------- #
STASH
# ----------------------------------------------------------------- #

# you made some changes but are not ready to commit - so stash the changes
`git stash save 'enter a message here'`

# you are ready to work on your stashed files
`git stash list`
`git stash apply stash@{<some number>}`

# you want to clear out all of your stashed changes
`git stash clear`

# ----------------------------------------------------------------- #
BRANCHES
# ----------------------------------------------------------------- #

# view all branches, verbose output
`git branch -av`

# view local vs remote branches on origin
`git remote show origin`

# create a new local branch
`git branch <branch-name>`

# switch to a different branch
`git checkout <branch-name>`

# create a new remote branch with the same name as local
`git push origin <branch-name>`

# create a remote branch with a different name than the local branch name
`git push origin <local-branch>:<remote-branch>`

# a teammate creates a branch and pushes to github.  you want to get that branch but use a new branch name instead
`git fetch origin`
`git branch --track <local-branch> origin/<remote-name>`

# you want to delete a local branch
`git branch -d <local-branch>`

# you want to delete a remote branch
`git push origin :<remote-branch>`