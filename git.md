### Work in branch
Create a branch as follows.
```
$ git branch branchname
$ git checkout branchname
```
Can see local/remote branches as</br>
```
$ git branch
$ git branch -r
$ git branch -a
```
Merge</br>
```
$ git checkout master
$ git merge branchname

```
Delete a local branch</br>
```
$ git branch -d branchname
```
Delete a remote branch</br>
```
$ git push origin --delete <branch_name>
```
### Restoration
- `git reset HEAD^` is useful for canceling the latest commit that has not yet been pushed. The working tree is reserved.</br>
- `git revert HEAD` is useful for canceling the latest commit that has been pushed.</br>
- `git reset --hard ORIG_HEAD` is useful for canceling the current merge.</br>
