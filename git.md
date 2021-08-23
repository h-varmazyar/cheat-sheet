# Git Cheet sheat
This cheat sheet contains some of important Git commands.

## Table of Contents
- [Setup Git](#setup-git)
- [Setup & Init Repo](#setup-init-repo)
- [Stage & snapshot](#stage-snapshot)
- [Branch & merge](#branch-merge)
- [Inspect & compare](#inspect-compare)
- [Tracking path changes](#tracking-path-changes)
- [Ignoring patterns](#ignoring-patterns)
- [Share & update](#share-update)
- [Rewrite history](#rewrite-history)
- [Temporary commits](#temporary-commits)
### Setup git
configuring user information used across all local repositories.

set a name that is identifiable for credit when review version history
```
git config --global user.name “[firstname lastname]”
```

set an email address that will be associated with each history marker
```
git config --global user.email “[valid-email]”
```

set automatic command line coloring for Git for easy reviewing
```
git config --global color.ui auto
```

### Setup & init Repo
Configuring user information, initializing and cloning repositories

initialize an existing directory as a Git repository
```
git init
```

retrieve an entire repository from a hosted location via URL
```
git clone [url]
```

### Stage & snapshot
Working with snapshots and the Git staging area

show modified files in working directory, staged for your next commit
```
git status
```

add a file as it looks now to your next commit (stage)
```
git add [file]
```

unstage a file while retaining the changes in working directory
```
git reset [file]
```

diff of what is changed but not staged
```
git diff
```

diff of what is staged but not yet commited
```
git diff --staged
```

commit your staged content as a new commit snapshot
```
git commit -m “[descriptive message]”
```

### Branch & merge
Isolating work in branches, changing context, and integrating changes

list your branches. a * will appear next to the currently active branch
```
git branch
```

create a new branch at the current commit
```
git branch [branch-name]
```

switch to another branch and check it out into your working directory
```
git checkout
```

merge the specified branch’s history into the current one
```
git merge [branch]
```

show all commits in the current branch’s history
```
git log
```

### Inspect & compare
Examining logs, diffs and object information

show the commit history for the currently active branch
```
git log
```

show the commits on branchA that are not on branchB
```
git log branchB..branchA
```

show the commits that changed file, even across renames
```
git log --follow [file]
```

show the diff of what is in branchA that is not in branchB
```
git diff branchB...branchA
```

show any object in Git in human-readable format
```
git show [SHA]
```

### Tracking path changes
Versioning file removes and path changes

delete the file from project and stage the removal for commit
```
git rm [file]
```

change an existing file path and stage the move
```
git mv [existing-path] [new-path]
```

show all commit logs with indication of any paths that moved
```
git log --stat -M
```

### Ignoring patterns
Preventing unintentional staging or commiting of files

Save a file with desired paterns as .gitignore with either direct string
matches or wildcard globs.
```
logs/
*.notes
pattern*/
```

system wide ignore patern for all local repositories
```
git config --global core.excludesfile [file]
```

###   Share & update
Retrieving updates from another repository and updating local repos

add a git URL as an alias
```
git remote add [alias] [url]
```

fetch down all the branches from that Git remote
```
git fetch [alias]
```

merge a remote branch into your current branch to bring it up to date
```
git merge [alias]/[branch]
```

Transmit local branch commits to the remote repository branch
```
git push [alias] [branch]
```

fetch and merge any commits from the tracking remote branch
```
git pull
```

### Rewrite history
Rewriting branches, updating commits and clearing history

apply any commits of current branch ahead of specified one
```
git rebase [branch]
```

clear staging area, rewrite working tree from specified commit
```
git reset --hard [commit]
```

### Temporary commits
Temporarily store modified, tracked files in order to change branches

Save modified and staged changes
```
git stash
```

list stack-order of stashed file changes
```
gti stash list
```

write working from top of stash stack
```
git stash pop
```

discard the changes from top of stash stack
```
git stash drop
```

updating...

## Resources
(#https://education.github.com/git-cheat-sheet-education.pdf)
