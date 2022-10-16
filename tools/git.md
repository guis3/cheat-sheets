# Git Cheat-sheet

## Account Information

To connect your account through git.

```shell
git config --global user.name "username"
git config --global user.email "mail@email.com"
git config --gloabl user.passwd "password"
```

## Git Commands

### Create

COMMAND | DESCRIPTION
---|---
`git init` | Create a new local repository
`git clone https://github.com/user/repo` | Clone a remote repository

### Local Changes

COMMAND | DESCRIPTION
---|---
`git status` | List changed files
`git diff` | List changes done to files
`git add .` | Add all changes to next commit
`git add <file>` | Add changes from file to next commit
`git add -p <file>` | Add some changes from file to next commit
`git commit -m "commit message"` | Commit all changes

### Branching

COMMAND | DESCRIPTION
---|---
`git branch` | List all existing branches
`git checkout <branch>` | Switch current branch
`git branch <new-branch>` | Create a new branch based on the current branch
`git branch -d <branch>` | Delete a local branch

### Update & Publish

COMMAND | DESCRIPTION
---|---
`git remote -v` | List all remotes
`git remote show <remote>` | List info about a remote
`git remote add <remote> <url>` | Add new remote to repository
`git fetch <remote>` | Pull all changes from remote but dont merge into local repo
`git pull <remote> <branch>` | Pull all changes from remote and merge into the local repo
`git push <remote> <branch>` | Push all local commits to remote

### Merge & Rebase

COMMAND | DESCRIPTION
---|---
`git merge <branch>` | Merge branch into local repo
`git rebase <branch>` | Rebase your current local repo to branch
`git rebase --abort` | Abort a rebase
`git rebase --continue` | Continue a rebase after resolving conflicts

### Undo

COMMAND | DESCRIPTION
---|---
`git reset --hard HEAD` | Discard all local changes
`git checkout <file>` | Discard local changes for file
`git revert <commit>` | Revert a commit
`git reset --hard <commit>` | Reset HEAD pointer to previous commit & discard all changes since then
`git reset <commit>` | Reset HEAD pointer to previous commit & preserve all changes as unstaged changes
`git push <remote> <branch>` | Reset HEAD pointer to previous commit & preserve all uncommitted changes