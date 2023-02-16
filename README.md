# Basics of Git

## Overview
##### What is Git?
Git is a free and open-source version control system.
##### Why do we use version control?
It is used to manage changes to documents, computer programs, large websites, and other collections of information. 
##### Why is version control important?
Version control is important because it allows a team to collaborate by tracking all of the changes made to the project and who made those changes. It can also provide context into why a certain decision was made about the project and who made that decision. 

## [Software Requirements](Software%20Requirements.md)

## Terms
| **Keyword** | **Description** |
| --- | --- |
| `Directory` | Folder in file system |
| `CLI` | Command Line Interface |
| `Commit` | Stores the current contents of the index in a new commit along with a log message from the user describing the changes |
| `Cache` | Local memory intended to temporarily store uncommitted changes |
| `Index` | The cache where changes are stored before they are committed |
| `Branch` | Pointer to a commit |
| `Master` | Default name of the first branch |
| `HEAD` |  Pointer to the most recent commit on the current branch |
| `Merge` | Joining two or more commit histories |
| `Workstation` | Local copy of a Git repository |
| `Workspace` | Local copy of a Git repository |
| `Working tree` | Current branch in your workspace |
| `Tracked/Untracked files` | Files either in the index cache or not yet added to it |
| `Stash` | Another cache, that acts as a stack, where changes can be stored without committing them |
| `Local Repository` | Where you keep your copy of a Git repository on your workstation |
| `Remote Repository` | A repository where you push changes for collaboration or backup |
| `Upstream Repository` | A remote repository that you track |
| `Pull Request` | GitHub-specific term to let others know about changes you've pushed to a branch in a repository. |
| `Merge Request` | a GitLab-specific term to let others know that you’d like your branch merged with master. |

## Commands
#### Git
| **Command** | **Description** |
| --- | --- |
| `config` | Log workstation into GitHub |
| `remote` | Configure local repository to a remote server or list all currently configured remote repositories |
| `clone` | Download the contents of a remote repository into a folder on you workstation |
| `checkout` | Create a new branch or switch to another |
| `branch` | Get list of branches in your remote repository and  |
| `add` | Track files |
| `status` | List the files you’ve changed |
| `commit` | Save your files to your local branch |
| `push` | Send changes of the committed files on your branch to remote repository |
| `pull` | Fetch and merge changes on your remote repository to your working directory |
| `merge` | Merge a different branch with your current branch. |

#### Shell
| **Command** | **Description** |
| --- | --- |
| `pwd` | Print Working Directory |
| `cd` | Change Directory |

## Objectives
- [Connect workstation to GitHub](Connect%20your%20Workstation.md)
- [Initialize a Local Repository](Initialize%20a%20Local%20Repository.md)
- [Create a Branch and Push changes](Create%20a%20Branch%20and%20Push%20changes.md)
- [Create a Pull Request](Create%20a%20Pull%20%Request.md)
- [Review Changes and Merge to Master](Review%20Changes%20and%20Merge%20to%20Master.mdCreate%20a%20Pull%20%Request.md)
- [Version Control in Ignition](Ignition.md)
