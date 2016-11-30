### Work in branch
Make a branch as follows.
```
$ git branch branchname
$ git checkout branchname
$ git push origin branchname
```
Can see local/remote branches as</br>
```
$ git branch
$ git branch -r
```
Merge</br>
```
$ git checkout master
$ git merge branchname
$ git branch -d branchname
```
### Restoration
- `git reset HEAD^` is useful for canceling the latest commit that has not yet been pushed. The working tree is reserved.</br>
- `git revert HEAD` is useful for canceling the latest commit that has been pushed.</br>
- `git reset --hard ORIG_HEAD` is useful for canceling the current merge.</br>
