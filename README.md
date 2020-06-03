# git-training

![git commit flow](https://github.com/harryosmar/git-training/blob/master/git-commit-flow-v2.png)

## Branches


- Create branch from `master` branch

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

- Switch branch

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

- merge update between branches

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
