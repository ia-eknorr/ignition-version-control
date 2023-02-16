## Push Local Repository
Get a list of all your available branches and current working branch.
```shell
git branch
```
If you are not on the correct branch, we need to create a new branch.
```shell
# Long way
git branch -c branch-name
git checkout branch-name

# Shorthand way to create and checkout a branch
git checkout -b branch-name
```
Now that we have a working branch, we can make edits to our files without affecting the master branch or remote repository.

** Edit file(s) **

Check Local Repository for any untracked changes
```shell 
git status
```
Add file(s) to be Tracked
```shell
# Single File
git add file-name.fileType

# Add all files
git add . 
```
Now that our files are being tracked, we need to commit those changes with a message. 
```shell 
git commit -m “Added code to files”

# Shorthand to add and commit 
git commit && git commit -m “Added code to files”
```

Once you've tracked your files and committed them, it is a good practice to verify a clean working tree.
```shell 
git status
```

If all is well, we can push the tracked changes to our Remote Repository.
```shell 
git push origin HEAD
```
