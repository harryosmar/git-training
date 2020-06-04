# git-training

![git commit flow](https://github.com/harryosmar/git-training/blob/master/git-commit-flow-v2.png)

## Branches


#### Create branch

![create branch](https://github.com/harryosmar/git-training/blob/master/create_branch.png)

```
// update current master branch
(master) $ git pull origin master

// create the new branch from updated master
(master) $ git checkout -b feature/my_branch

// Switched to a new branch `feature/my_branch`, then push it to github
(feature/my_branch) $ git push origin feature/my_branch

// create the new branch from `feature/my_branch`
(feature/my_branch) $ git checkout -b feature/my_branch_v2

// Switched to a new branch `feature/my_branch_v2`, then push it to github
(feature/my_branch_v2) $ git push origin feature/my_branch_v2
```

#### Switch branch

![switch branch](https://github.com/harryosmar/git-training/blob/master/switch_branch.png)

```
// switch to branch feature/1
(master) $ git checkout feature/1

// Switched to branch 'feature/1'
(feature/1) $ 

// switch back to branch master
(feature/1) $ git checkout master

// Switched to branch 'master'
(master) $ 
```

#### Merge update between branches

![merge branch](https://github.com/harryosmar/git-training/blob/master/merge_branch.png)

```
// update current master branch
(master) $ git pull origin master

// create the new branch from updated master
(master) $ git checkout -b feature/my_branch

// in the new branch, create file with name `hello.txt` and content "Hello World", file status `untracked`
(feature/my_branch) $ echo "Hello World" >> hello.txt

// change file status to `staged`
(feature/my_branch) $ git add hello.txt

// commit file with `staged` status, this commit mark `hello.tx` file so it's belongs to `feature/my_branch`
(feature/my_branch) $ git commit -m "add hello.txt file"

// switch back to branch master
(feature/my_branch) $ git checkout master

// merge FROM `feature/my_branch` TO `master`, so master will also has `hello.tx` file 
(master) $ git merge feature/my_branch
```

#### Tagging/Release

![tagging](https://github.com/harryosmar/git-training/blob/master/tagging.png)

```
// create tag `v1.0.0` from `master` branch
(master) $ git tag -a v1.0.0 -m "First release"

// switch to tag `v1.0.0`
(master) $ git checkout v1.0.0

// push tag `v1.0.0` to github
(master) $ git push origin v1.0.0

// create new branch from tag `v1.0.0`
((HEAD detached at v1.0.0)) $ git checkout -b feature/bugfix

// Switched to a new branch 'feature/bugfix', contains the same commits with tag `v1.0.0`
(feature/bugfix) $
```
