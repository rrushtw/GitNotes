# Git commands
Here is my notes while learning Git

### Getting & Creating Projects
| Command | Description |
| ------- | ----------- |
| `git clone https://github.com/[username]/[repository-name].git` | Clone with HTTPS |
| `git clone git@github.com:[username]/[repository-name].git` | Clone with SSH |
| `git remote set-url origin [https/ssh]` | Update link |
| `git remote set-url --push origin [https/ssh]` | Update push link |

```bash
//WARNING: First commit your current changes, or you will lose them.
//Then run the following commands from the top folder of your Git repository:
git rm -r --cached .
git add .
git commit -m "fixed untracked files"
```

### Basic Snapshotting
| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [File Path]` | Stage a file |
| `git restore [File Path]` | Discard changes in a file |
| `git restore --staged [File Path]` | Unstage a file |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file-name.txt]` | Remove a file (or folder) |

```bash
//Stage all new and changed files
git add .
git add -A
git add --all

//Discard all changes
git checkout [TheSameBranch]
git checkout -- .
git restore .

//Unstage all files
git restore --staged .
```

### Branching & Merging
| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git rebase [branch name]` | Rebase current branch onto a branch |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git merge (--no-ff) [branch name]` | Merge a branch into the active branch |
| `git merge (--no-ff) [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Create Branch
| Command | Description |
| ------- | ----------- |
| `git branch [branch name]` | Create a new branch base on current branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
```bash
//Create a new branch base on [branch name] which default is current branch
git checkout -b [New branch] [branch name]
```

### Delete Branch
| Command | Description |
| ------- | ----------- |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
```bash
//Delete a branch which doesn't exist but show in list
git branch -rd [branch name]
```

### Sharing & Updating Projects
| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --tags` | Push all tags to remote |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |

### Undo
| Command | Description |
| ------- | ----------- |
| `git tag -d [tagname]` | Delete a local tag |
| `git push origin --delete [tagname]` | Delete a remote tag |
| `git reset --hard [ID]` | Discard all change to this commit |
| `git reset --soft [ID]` | Keep all change and reset onto this commit |

### Inspection & Comparison
| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

## Deal with git bash editor mode
1. press "i"
2. edit message
3. press "ESC"
4. write ":wq"
5. press enter

## Deal with list
1. press "q" to exit

## Change folder with git bash
```bash
//Change to [Path]
cd /[Path]

//Example: Change current path into C:\myGit\
cd /c/myGit/
```

## Set UTF-8 display for git
```bash
// Global setting for all you repositories
git config --global gui.encoding utf-8

// For one repository only
git config gui.encoding utf-8
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Credit
[Joshnh/Git-Commands](https://github.com/joshnh/Git-Commands)
[gitignore](https://stackoverflow.com/questions/11451535/gitignore-is-ignored-by-git)
[UTF-8](https://stackoverflow.com/questions/23151339/set-utf-8-display-for-git-gui-differences-window)

## License
[MIT](https://choosealicense.com/licenses/mit/)