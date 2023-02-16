## Initialize a Local Repository
In the CLI, navigate to file directory for this project
```shell
cd /Your-File-Path/Repository-Folder
```
Once we are in the correct folder, we need to initalize the repository with Git.

```shell
git init -b master
```
Now that we have our respository initialized, we need to go to [GitHub](https://github.com) and create our Remote repository if has not already been created.

** Creates Repository **

Finally, we need to link our workstation to the Remote Repository we just created. 

** Add verbiage about how to get the URL **
```shell
git remote add origin https://github.com/your-username/your-repository.git
```