# 第十六讲 Git rebase
## Git rebase
rebase：变基，意即改变分支的根基
rebase作用：从某种程度上来说，rebase与merge可以完成类似的工作，不过两者的工作方式有着显著的差异
- Git rebase操作
```
git checkout branch_name
git rebase branch_new_name
```
- Git merge操作和Git rebase操作的区别
两者结果内容一样，过程和操作方式完全不一样。Git rebase操作会修改提交历史，会让提交历史变成一条直线。
Git rebase原理：实际上是将一个分支的修改内容应用到里另外一个分支上，不断的应用，所以提交历史变成一条直线。
- Git rebase注意事项
1.rebase过程中也会出现冲突
2.解决冲突后，使用git add添加，然后执行如下命令：
```
git rebase --continue
```
3.接下来Git会继续应用余下的补丁
4.任何时候都可以通过如下命令终止rebase，分支会恢复到rebase开始前的状态
```
git rebase --abort
```
- Git rebase最佳实践
1.不要对master分支执行rebase，否则会引起很多问题
2.一般来说，执行rebase的分支都是自己的本地分支，没有推送到远程的版本库。


