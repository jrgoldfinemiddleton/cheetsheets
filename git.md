# Git Cheat Sheet #

## Getting help ##

Display manual page for a Git subcommand
```bash
man git-<subcommand>
```

## Configuring Git ##

Display active Git configuration
```bash
git config -l
```

## Creating local repositories ##

Create new repository inside current directory
```bash
git init
```

Create local repository from remote repository
```bash
git clone <repo-url>
```

Create local repository from remote repository in specific directory
```bash
git clone <repo-url> <local-path>
```

## Working with remote repositories ##

Display remote repositories
```bash
git remote -v
```

Add remote repository
```bash
git remote add <name> <repo-url>
```

Push commits in local branch to branch `master` of remote `origin`
```bash
git push origin master
```

Push commits in local branch to upstream branch of same name
```bash
git push
```

## Pulling remote branches ##

Fetch remote branch of same name and merge with local branch
```bash
git pull
```

Fetch all refs/tags from remote branch
```bash
git fetch
```

Apply changes from other commits, creating new commits
```bash
git cherry-pick <commit> ...
```

Stage changes from other commits, but don't create new commits
```bash
git cherry-pick -n <commit>
```

## Staging and committing files ##

Stage all files for commit recursively from current directory
```bash
git add .
```

Stage all files for commit recursively from path(s) specified
```bash
git add <path-pattern> ...
```

Stage and commit all changes
```bash
git commit -a
```

Commit staged changes with specified message
```bash
git commit -m '<commit-message>'
```

Amend most recent commit by incorporating staged files
```bash
git commit --amend
```

## Moving and cleaning files ##

Move or rename staged file or directory
```bash
git mv <source-path> <dest-path>
```

Reset index and working tree to specific commit, losing all later changes
```bash
git reset --hard <commit>
```

Delete files and directories not staged or committed
```bash
git clean -fd
```

Unstage file (doesn't delete it)
```bash
git reset HEAD <path>
```

Delete committed file or directory
```bash
git rm <path>
```

Delete staged file or directory
```bash
git rm -f <path>
```

Unstage file or directory or un-commit file but don't delete it
```bash
git rm --cached <path>
```

Restore file or directory as it was in most recent commit (loses its current changes)
```bash
git checkout <path> ...
```

Restore working space to most recent commit (all file changes are lost, but newly created files remain)
```bash
git checkout --
```

## Working with branches ##

Create new branch from current branch
```bash
git checkout -b <new-branch>
```

List local branches
```bash
git branch
```

Switch to another local branch
```bash
git checkout <branch>
```

Rename current branch
```bash
git branch -m <new-branch>
```

### Merging and rebasing ###

Create new commit in current branch by merging tips of current branch and specified branch
```bash
git merge <branch>
```

Reapply current commits after another branch/tip
```bash
git rebase <branch>
```

Rebase and resolve merge conflicts
```bash
git rebase <branch>

# check which files have conflicts
git status

# edit files and resolve conflicts
vim <file>

# stage fixed files
git add .

# complete rebase operation (don't forget this step!)
git rebase --continue
```

Interactively rebase all commits between HEAD and specified commit (allows for combining, splitting, or removing individual commits)
```bash
git rebase -i <commit>
```

## Tracking commit history ##

Display history of commits in current branch
```bash
git log
```