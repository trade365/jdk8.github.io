# git命令

## git rebase和git merge

git rebase是将A分支按照线性的方式合并到B分支上，

A：c1->c2->c3->c4

B：c1->c2->c5->c6

在B分支上执行：git rebase A，则B分支会变成：

B：c1->c2->c3->c4->c5->c6

需要注意的是：c5和c6的commit id会发生变化，如果不希望c5和c6发生变化，则需要用git merge。

git merge是将A分支合并到B分支上，会生成一个新的提交点，新提交点继承了A和B两个分支，B分支会变成：

B：c1->c2->c3->c4->c7

​                ↓c5------->c6↑

c5和c6的commit id不会发生变化。

## git checkout

拉取远程分支dev_1到本地，将本地分支命名为dev_1.1：

git fetch origin dev_1

git checkout -b dev_1.1 origin/dev_1

## git cherry-pick

git cherry-pick -x commit_id

将commit_id这个提交合并到当前分支。
