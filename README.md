# Basics of Git

## Table of Contents

- [Basics of Git](#basics-of-git)
  - [Table of Contents](#table-of-contents)
  - [Purpose](#purpose)
  - [How to use this repository](#how-to-use-this-repository)
  - [Course Contents](#course-contents)
  - [Overview](#overview)
    - [What is Git?](#what-is-git)
    - [Why do we use version control?](#why-do-we-use-version-control)
    - [Why is version control important?](#why-is-version-control-important)
  - [Terms](#terms)
  - [Common Git Commands](#common-git-commands)
    - [Example](#example)
  - [Common Shell Commands](#common-shell-commands)
    - [Example](#example-1)
  - [Objectives](#objectives)
  - [Requests? Issues?](#requests-issues)
    - [Cred](#cred)

## Purpose

Learn how to use version control with Git and Ignition.

## How to use this repository

This repo can be used as a manual to be read from top to bottom in order to learn the basics of git and gain intermediate strategies, or as a reference to be reminded of certain functions or strategies.

If you consider yourself new to git with Ignition, it may be useful to go through the [Git Ignition Lab](https://github.com/ia-eknorr/git-ignition-lab), which will give you a practical ideal of git version control for Ignition development.

## Course Contents

> [!TIP] Bullet points that are not hyperlinked are road-mapped for future development.

- [Git Ignition Lab](https://github.com/ia-eknorr/git-ignition-lab)
- [Basics of Git](https://github.com/ia-eknorr/ignition-version-control)
  - [Workstation Setup](Workstation%20Setup.md)
  - [Initialize a local repository](Initialize%20a%20Local%20Repository.md)
  - [Create a branch and push changes](Create%20a%20Branch%20and%20Push%20changes.md)
  - [Create a pull request](Create%20a%20Pull%20Request.md)
- [Branching Strategies](Branching%20Strategy.md)
- [Ignition Git Style Guide](https://github.com/ia-eknorr/ignition-git-style-guide)
- Intermediate Git
  - Resolving Merge conflicts
  - Intermediate commands
    - stash
    - reflog
    - reset

## Overview

### What is Git?

Git is a version control system that helps developers keep track of changes to their code over time.

### Why do we use version control?

It allows multiple developers to work on the same project simultaneously, tracks changes to source code and other files, and provides tools for managing different versions of files, merging changes, and rolling back changes when necessary. Git is widely used in software development and other version control tasks due to its speed, efficiency, and flexibility.

### Why is version control important?

Version control is important because it allows a team to (among many other things):

- Track all of the changes made to the project
- View who made changes
- Merge changes without overwriting other features
- Revert accidentally deleted work.
- Provide context into why a certain decision was made about the project and who made that decision

## Terms

| **Keyword** | **Description** |
| --- | --- |
| `Branch` | Pointer to a commit |
| `Cache` | Local memory intended to temporarily store uncommitted changes |
| `CLI` | Command Line Interface |
| `Commit` | Stores the current contents of the index in a new commit along with a log message from the user describing the changes |
| `Directory` | Folder in file system |
| `HEAD` | Pointer to the most recent commit on the current branch |
| `Index` | The cache where changes are stored before they are committed |
| `Local Repository` | Where you keep your copy of a Git repository on your workstation |
| `Main` | Default name of the first branch |
| `Merge` | Joining two or more commit histories |
| `Merge Request` | A GitLab-specific term to let others know that you’d like your branch merged with main. |
| `Pull Request` | GitHub-specific term to let others know about changes you've pushed to a branch in a repository. |
| `Remote Repository` | A repository where you push changes for collaboration or backup |
| `Stash` | Another cache, that acts as a stack, where changes can be stored without committing them |
| `Tracked/Untracked files` | Files either in the index cache or not yet added to it |
| `Upstream Repository` | A remote repository that you track |
| `Workstation` | Local copy of a Git repository |
| `Workspace` | Local copy of a Git repository |
| `Working tree` | Current branch in your workspace |

## Common Git Commands

| **Command** | **Description** |
| --- | --- |
| `add` | Track files |
| `branch` | Get list of branches in your remote repository and  |
| `checkout` | Create a new branch or switch to another |
| `clone` | Download the contents of a remote repository into a folder on you workstation |
| `commit` | Save your files to your local branch |
| `config` | Log workstation into GitHub |
| `remote` | Configure local repository to a remote server or list all currently configured remote repositories |
| `merge` | Merge a different branch with your current branch. |
| `pull` | Fetch and merge changes on your remote repository to your working directory |
| `push` | Send changes of the committed files on your branch to remote repository |
| `status` | List the files you’ve changed |

### Example

```bash
git status
git checkout my-branch
git pull origin main
```

## Common Shell Commands

| **Command** | **Description** |
| --- | --- |
| `cd` | Change directory |
| `ls` | List file in current working directory |
| `mkdir` | Make new directory |
| `pwd` | Print working directory |

### Example

```bash
cd /usr/local/bin/ignition
```

## Objectives

- [Workstation Setup](Workstation%20Setup.md)
- [Initialize a Local Repository](Initialize%20a%20Local%20Repository.md)
- [Create a Branch and Push changes](Create%20a%20Branch%20and%20Push%20changes.md)
- [Branching Strategy](Branching%20Strategy.md)
- [Create a Pull Request](Create%20a%20Pull%20Request.md)

---

**Next**: [Workstation Setup](Workstation%20Setup.md)

---

## Requests? Issues?

If you have any questions or notice something that doesn't look right, [open an issue](https://github.com/ia-eknorr/ignition-version-control/issues) or submit a pull request.

### Cred

Much inspiration for all of this was taken from [Design Group](https://github.com/design-group).
