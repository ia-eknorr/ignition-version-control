# Ignition Example
## Table of Contents
- [Ignition Example](#ignition-example)
  - [Table of Contents](#table-of-contents)
  - [Purpose](#purpose)
  - [Before Getting Started](#before-getting-started)
    - [Required](#required)
    - [Recommended](#recommended)
  - [Procedure](#procedure)
    - [Set up the Ignition Gateway](#set-up-the-ignition-gateway)
    - [Initialize Repository](#initialize-repository)
      - [Open the project on Visual Studio Code](#open-the-project-on-visual-studio-code)
      - [Log in to Github](#log-in-to-github)
      - [Add .gitignore file](#add-gitignore-file)
      - [Create a remote repository](#create-a-remote-repository)
      - [Initialize the local repository](#initialize-the-local-repository)
  - [Develop a New Feature](#develop-a-new-feature)
  - [How to Submit a Pull Request](#how-to-submit-a-pull-request)
  - [Additional Resources](#additional-resources)

## Purpose
This is a _Getting Started_ tutorial intended for those who are new or newer to Git version control with Ignition. By the end of this tutorial, you should have a basic understanding of how to set up Git with Ignition and the workflow to start tracking your codebase with Git. This is written like a lab, so follow along on your own, use the [IA Ignition Version Control Guide](https://inductive-git.ia.local/eknorr/version-control), and ask [@eknorr](https://inductive-git.ia.local/eknorr) (or on [slack](eknorr@inductiveautomation.com)) for help.
## Before Getting Started
  In order to perform version control on Ignition, ensure the following are properly set up or installed:

### Required
  - [Ignition](https://inductiveautomation.com/downloads/)
    - Either in a Docker container or installed on host
  - [Git](https://git-scm.com/downloads)
    - Installed on host

### Recommended
  - [Visual Studio Code](https://code.visualstudio.com/Download)
    - Highly recommended (VSCode setup guide coming soon!)
  - [GitHub](https://github.com) access
    - Log in via [Duo](https://ia.login.duosecurity.com/central/)
    - Search for "Github Enterprise (on prem)"
    - If Enterprise github is not available, ask your manager for access, and get started with a personal account for the time being
      - Do not put any IA material on your personal GitHub account. This is an exception made for training purposes only.

> :bulb: **_FAQ_**: What if I don't have access to the on prem Github Enterprise server yet?
>
> Ask your manager for access, and get started with a personal account for the time being. Do not put any IA material on your personal GitHub account. This is an exception made for training purposes only.

## Procedure
The goal of this exercise is to focus on version control and how it works with Ignition. That said, Ignition Quick Start project will be used as a starting place so there is something to add to a repository and version control. It is good to note that while this guide is used with Quick Start, the procedure is the same with a project where Quick Start isn't used. All references to the Quick Start project can be replaced with your project name. 

### Set up the Ignition Gateway
1. Commission and start the Ignition Gateway
2. After commissioning, select "Yes, Enable Quick Start"
   1. Naturally, this is not required for all implementations
   2. [Here](https://docs.inductiveautomation.com/display/DOC80/Quick+Start+Guide) is a guide to the Ignition Quick Start if needed

![Gateway Startup Page](images/IgnitionQuickStart.png)

### Initialize Repository 
#### Open the project on Visual Studio Code
1. Open VS Code and navigate to the project directory
   1. Select `File/Open...` and open the Ignition project
      1. Ex: `<ignition-install-path>/data/projects/quickstart`
2. In the VS Code `EXPLORER` tab, right click the project and select `Open in Integrated Terminal`
![Integrated Terminal](images/integrated_terminal.png)
   1. Within the terminal, verify you are in the correct directory by typing the command `pwd` (`P`rint `W`orking `D`irectory). This directory should be within the project name, `samplequickstart`.
      - For Mac the directory should be: `/usr/local/ignition/data/projects/samplequickstart`
      - For Windows the directory should be: `C://Program Files Inductive Automation/Ignition/data/projects/samplequickstart`
#### Log in to Github
Login to Github with the integrated terminal by running the following commands:

```shell
git config --global user.name "YourUserName"

git config --global user.email "your@email.addr"
```

#### Add .gitignore file
1. At the top level of your directory, create and save a file named `.gitignore` with the following code:
    ```python
    # Ignition Resource Content
    ./resources/
    ```
    ![gitignore](images/gitignore.png)
   -  This will ignore all of Ignition's resource files, which frequently change and do not need to be version controlled

> :memo: **_Note_**: .gitignore files are very useful - it specifies intentionally untracked files that Git should ignore. These files will still exist on the gateway, and will not be removed, just will not be version controlled.
> 
> Although this example is Ignition specific, it is also possible to ignore any other type of file that shouldn't be tracked. You may want to also exclude:
>
> - `com.inductiveautomation.vision/`: if your project does not use vision, it is not needed.
> - `DS_Store`: if using a Mac, the `DS_Store` file contains your viewing preferences.
> - `*.code-workspace`: This will ignore your workspace files if using VS Code.
> - `.vscode/`: if using VS Code, this will ignore files created by VS Code.
> - `__pycache__/`, `.jython_cache`  and `.pytest_cache`: can be used to ignore caches made by python, jython and pytest.
> - `*.pyc`: will ignore the compiled byte code python files.

#### Create a remote repository
1. In the upper-right corner of any page on the GitHub web browser, use the  drop-down menu, and select New repository
2. Type a short, descriptive name for the new repository. 
   1. See the [IA Git Style Guide](https://inductive-git.ia.local/eknorr/git-style-guide#repository-setup-1) for help naming your repo
3. Select the "Create repository"

#### Initialize the local repository
1. Run the following commands in the integrated terminal:
    ```shell
    git init .
    git remote add origin <Your version control repository link>
    git add .
    git commit -m "Initial commit"
    git push -u origin master
    ```
2. About the commands:
- `git init`: 
  - `init` initializes the repository.
- `git remote add origin <Repository Link>`: 
  - `remote add` refers to adding a location where the work is stored. In this case, it is held remotely on GitHub.
  - `origin` is an alias for a particular repository. In this case, the link you have added.
  - `<Repository Link>` is the repository which will be herein referred to as `origin`. The link to your repository is is a combination of the github url, your username (or the organization the repo is made under), and the name of your repository. In the example, the url is: `https://inductive-git.ia.local/eknorr/git-ignition-example`.
- `git add .`:
  - `add .` adds the work you have done in the current directory to the staging area. Because the repository has no previous commits, this will be many Ignition files. The `.` is used to chose all changed files of the directory you are working in.
- `git commit -m "Initial commit"`:
  - `commit` is the command for committing your work. A commit is good to do regularly, it allows for going back to the exact state of your work at the time of the commit.
  - `-m "Initial commit"` adds a message to the commit. In this case, the message is "Initial commit". It is important to be specific when writing the messages as it becomes difficult to remember what each commit was for and can be confusing if there was ever a need to rollback to a specific commit.
  - Without the `-m` it will open a text editor with a file that you can type the message into.
- `git push origin main` allows for pushing all of the commits to the remote master.


You have just made and initialized a GitHub repository. To verify, you can go to your GitHub account and see the new repository. Below is an example

![Initial Commit on Repo](images/initial_commit.png)

---
## Develop a New Feature
Now that the repository has been initialized, it's time to add a new feature. 

- Create a new branch by typing this in the terminal: ```git checkout -b new_feature```.
  - The `checkout` command allows for navigating to a branch. This command can also be used switching to another branch. For example, to get to the master branch the command is ```git checkout master```.
  - The ```-b``` stands for branch. This creates the new branch.
  - ```new_feature``` is the name of your branch. 

- Open the Ignition Designer and make a new view called `example_view`.
  ![Creating a New View](images/new_view_ignition.png)

- Edit the background color, for this example the background has been changed to red.
  ![Edited View](images/edited_view.png)
- Once your new feature has been added, save in the Ignition Designer and return to your terminal.
- To see what you have edited, use the command `git status`. This will show you the status of all your work within the branch.
  - You should see a few files modified specifically in `com.inductiveautomation.perspective`. 

![Results from `git status`](images/git_status.png)

- We now need to add these changes to the remote repository. Start with this command `git commit -am "Added cool new feature"`. 
  - This is the `commit` command which we have done before but with the additional `-am`. The `a` stands for add. It removes the need for the `git add .` command we did earlier. The `m` stands for message.

- Use the command `git push origin HEAD` to push these changes in the commit to your remote repo. You should see in the terminal a new branch was created.
  - `HEAD` is the current branch. This command in full is to push to the remote branch, `new_feature`.
![Results from `git push origin HEAD`](images/new_branch_push.png)
  - You should be pushing to your remote branch anytime you are done working on the branch, whether you are going to work on a different branch or are done working for the day. This allows other people to pick up where you left off without the chance of doubling up on work.

## How to Submit a Pull Request

Pull requests are used when you want to add your code into the master branch. This allows for a review of your work and to get the team on board with the changes that are about to be added. To put in a pull request perform the below steps.

- Push your latest changes to the remote branch.
- Go to the `Pull requests` tab within GitHub.
![Pull Request Page](images/pull_request_page.png)
- Select `New pull request`
- Select the branch you want to add your code to. This is usually the master branch. Then select the name of your branch. We should see an arrow pointing from `new_feature` to `master`.
- ![New Feature to Master](images/feature_to_master.png)
- Add a short description containing the purpose of the pull request. This will allow your reviewers to know what the purpose of the request is.
- Select the drop down on the green button that says `Create Pull Request` and select `Create Draft Pull Request`.
  - It is good practice to make a draft pull request first because it allows for you to review the changes you want to pull into the other branch. Make sure the pull request only has the changes directly relating to the branch. In other words, do not try to merge code involving the renaming of a variable when the branch is intended for only merging documentation.

- **Common Errors:** The goal of the pull request is to only have intended changes present. This means there should not be a change in the files that you did not alter. The only exception to this are the `resource.json` files.
  - **Unneeded File:** Sometimes Git will pick up a file that is not needed. For example, binary files. It is best to remove them while your file is still a draft. To do so, use the command ```git rm --cached file_name```.
    - ```rm``` stands for "remove". `cached` removes the file from the staging area. This means it will not be included in both the commit or the push. 
  - **Merge Conflict:** Sometimes when trying to merge, there will be a conflict. This is because what is in the current branch and master are not the same. In order to choose which version you want, use this command: ```git pull origin branch_to_merge_with```. For example, ```git pull origin master``` will pull in all content from the master.
    - From here search the project for the characters ">>". This will show all conflicts. For every conflict, select whether you wand the HEAD or incoming version, save, and commit.
    - Push your code out with these newly resolved conflicts and look at GitHub to verify there are no more conflicts. 
  - **Missing File:** Sometimes you will accidentally delete a file you didn't mean to. To fix this, use the following command: ```git checkout origin/branch_to_merge_with path/to/deleted/file```. For example, ```git checkout origin/master ignition/script-python/Example/code.py``` will add back the master's version of `Example/code.py`.
  - **Reset to Previous Commit:** In the case you want to go back to a previous commit, find the commit you whish to go back to. Then use this command ```git reset <commit id>```. This would look something like: ```git reset e0b5ab11f1eeac6116b5a7abf4cbdf9b12f26990```. The commit id can be found by clicking the "commit" link in the right hand corner of the GitHub branch that would contain your commit.

- Once everything is in order, select "Ready for review". You will now have a pull request.
- Some pull requests will require a certain amount of reviews to merge into a branch. To do this, Select the gear in the right hand column next to "Reviewers." Select the people most appropriate for the review. They will be notified their review was requested.
  - ![Adding a Review Request](images/request_review.png)

## Additional Resources

[Inductive Automation's Version Control Guide](https://www.inductiveautomation.com/resources/article/ignition-8-deployment-best-practices#gitlab-example)

[Design Group's Version Control Guide](https://github.com/design-group/version-control)

[My Example](https://github.com/evelyn-stodghill/ignition_version_control)