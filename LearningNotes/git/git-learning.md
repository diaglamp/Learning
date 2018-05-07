#Git

`git remote`

`git prune`

`git fsck`

`git fetch`

`git gc`


##具体场景
###回滚远端错误merge
```
git reset --hard <commit_id>
git push origin HEAD --force
```
