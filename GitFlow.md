# Git Flow Notes
Here is my notes while learning Git flow

## Initialize
gitflow | git
--------|-----
`git flow init` | `git init`
&nbsp; | `git commit --allow-empty -m "Initial commit"`
&nbsp; | `git checkout -b develop master`


## Features
### Create a feature branch
gitflow | git
--------|-----
`git flow feature start MYFEATURE` | `git checkout -b feature/MYFEATURE develop`

### Share a feature branch
gitflow | git
--------|-----
`git flow feature publish MYFEATURE` | `git checkout feature/MYFEATURE`
&nbsp; | `git push origin feature/MYFEATURE`

### Get latest for a feature branch
gitflow | git
--------|-----
`git flow feature pull origin MYFEATURE` | `git checkout feature/MYFEATURE`
&nbsp; | `git pull --rebase origin feature/MYFEATURE`

### Finalize a feature branch
gitflow | git
--------|-----
`git flow feature finish MYFEATURE` | `git checkout develop`
&nbsp; | `git merge --no-ff feature/MYFEATURE`
&nbsp; | `git branch -d feature/MYFEATURE`

### Push the merged feature branch
gitflow | git
--------|-----
_N/A_ | `git push origin develop`
&nbsp; | `git push origin :feature/MYFEATURE` _(if pushed)_

## Releases
### Create a release branch
gitflow | git
--------|-----
`git flow release start 1.2.0` | `git checkout -b release/1.2.0 develop`

### Share a release branch
gitflow | git
--------|-----
`git flow release publish 1.2.0` | `git checkout release/1.2.0`
&nbsp; | `git push origin release/1.2.0`

### Get latest for a release branch
gitflow | git
--------|-----
_N/A_ | `git checkout release/1.2.0`
&nbsp; | `git pull --rebase origin release/1.2.0`

### Finalize a release branch
gitflow | git
--------|-----
`git flow release finish 1.2.0` | `git checkout master`
&nbsp; | `git merge --no-ff release/1.2.0`
&nbsp; | `git tag -a 1.2.0`
&nbsp; | `git checkout develop`
&nbsp; | `git merge --no-ff release/1.2.0`
&nbsp; | `git branch -d release/1.2.0`

### Push the merged feature branch
gitflow | git
--------|-----
_N/A_ | `git push origin master`
&nbsp; | `git push origin develop`
&nbsp; | `git push origin --tags`
&nbsp; | `git push origin :release/1.2.0` _(if pushed)_

## Hotfixes
### Create a hotfix branch
gitflow | git
--------|-----
`git flow hotfix start 1.2.1 [commit]` | `git checkout -b hotfix/1.2.1 [commit]`

### Finalize a hotfix branch
gitflow | git
--------|-----
`git flow hotfix finish 1.2.1` | `git checkout master`
&nbsp; | `git merge --no-ff hotfix/1.2.1`
&nbsp; | `git tag -a 1.2.1`
&nbsp; | `git checkout develop`
&nbsp; | `git merge --no-ff hotfix/1.2.1`
&nbsp; | `git branch -d hotfix/1.2.1`

### Push the merged hotfix branch
gitflow | git
--------|-----
_N/A_ | `git push origin master`
&nbsp; | `git push origin develop`
&nbsp; | `git push origin --tags`
&nbsp; | `git push origin :hotfix/1.2.1` _(if pushed)_

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Credit
[JamesMGreene/gitflow-breaksown.md](https://gist.github.com/JamesMGreene/cdd0ac49f90c987e45ac)

## License
[MIT](https://choosealicense.com/licenses/mit/)