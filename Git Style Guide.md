# Git Style Guide

## Purpose
Define a style guide for using version control with Git, specifically for use with Ignition. This includes naming for repositories, default branches, feature branches, commit messages, and pull request messages, among other things.

## Quick Reference
### Repository Setup
| Name | Default |
| :---: | :---: |
| Name | `my-repository-name` |
| Description | `A Brief description of the repository` (not empty) |

### Branches
| Name | Default Name |
| :---: | :---: |
| Default Branch | `main` |
| Development | `dev` |
| Release | `release` |
| Feature | `feature/my-new-feature` |
| Bug Fix | `bugfix/my-bug-fix` |

### Commits
| Name | Default Name |
| :---: | :---: |
| Commit Message | `Brief Commit Description` |

### Merges
| Name | Default Name |
| :---: | :---: |
| Merge Type | Squash (recommended) <br> or Merge Commit |

---

## Repository Setup
Setting up a repository can look different depending on if one is forking an existing repo, or if using a template. These are general guidelines that can be adjusted per project specifications.

### Owner
- Select whether the owner of the repository should be yourself or belong to an organization

### Repository name
`my-repository-name`

- A unique name should be chosen for new repositories (GitHub ensures uniqueness). The name should be lower case with dashes separating words and should be reasonably clear what the repo is to be used for.

- Good repo names: `ignition-database-frontend`, `this-client-test-env`, `exchange-dev`, `erics-first-repo`
- Bad repo names: `test`, `test-2`, `repothatneedsdelimiters`

### Description
`Required`

- The description should expand on the name of the repo and provide a high level purpose for the codebase. Another engineer looking at this repo description should understand at a high level what to expect to see in the codebase.

### Public vs. Private
`Public` or `Private` is acceptable

- This is up to the owner and depends on the intention for the repo. It is important to note that "public" on the On Prem GitHub server is still only public to the internal Inductive Automation team. No projects on the On Prem GitHub server cannot be shared or made available to the external "Public". Private will only be seen by you.

#### Good public repositories
- Quickstart Project
- Collaborative projects
- Helpful team resources

#### Good private repositories
- Repos to learn git
- Testing repositories
- Repos that don't follow the style guide :triumph:

### Add a README file
Recommend `true` (`false` is acceptable)

- Having a readme for documentation of your project is crucial, but adding it to the initial repo is not required. It can instead be added from VSCode on your initial commit.

### Add .gitignore
`None` (`<any>` is acceptable)

- Gitignore files are important to ignore files that do not need to be tracked. It is recommended not to add a .gitignore from VSCode on your initial commit.

---

## Branches
All branches should be lower-case with dashes separating new words. In certain cases, slashes can be used to separate branch names.

### Deleting Merged Branches
After merging a feature into another branch, the feature branch should be deleted. It is recommended that branches on GitHub be set to automatically delete after a Pull Request is merged.

### Default Branch
Main: `main`

- There should be no commits on this branch. Instead, use `dev` or a feature branch.
- Historically, `master` was used, but has fallen out of favor in recent years. `main` is highly the recommended default branch name. 

Development: `dev`

Release: `release`

### Feature Branches
`feature/my-new-feature`

- Feature branches should begin with `feature/` then have a short (1-4 words) description of the feature with the words separated by dashes (`-`)

### Bug Fix Branches
`feature/my-new-feature`

- Feature branches should begin with `bugfix/` then have a short (1-4 words) description of the bug fix with the words separated by dashes (`-`)

---

## Commits
Each commit should contain a message (`git commit -m "<Commit message here>"`). These messages are required by Git and should contain a brief description of what is contained in the commit. If one is not provided, a vim document will appear in the console asking for a commit message (or `:q` if you'd like to quit).

Some prefer to prepend `Feature:` or `Chore:` before their commit message. This can be used to give a quick categorization to each commit for someone visually searching through commit messages.

> :memo: **_Note_**: If it's difficult to sum up your work in a brief commit message, that could be an indicator that you're trying to fit too much into a single commit. Consider breaking up the work into more than one commit.

### Good commit messages
- `Feature: Developed motor faceplate`
- `Chore: Cleaned up messy code in myScripts/general`
- `Fixed broken binding on 'Main Views/plant'`
- `End of day commit: Halfway through my-feature`

### Bad commit messages
- `Added style class and applied it to my view and added docstrings to myScripts/general` 
  - Too many features in one commit
- `Built screens` 
  - Not descriptive enough

---

## Merges
- All merges must be done through a Pull Request on GitHub
  - This allows teammates to review work before merging and keeps everyone aligned on tasks
- Different types of merges exist. Recommended merge styles are:
  - **Merge Commit**: Used to merge branches with few commits
  - **Squash and Merge**: Used to merge branches with many commits. This option essentially makes a commit with a list of each commit in the feature branch as the default description.