# 第七讲  checkout 进阶与 stash
## checkout 进阶
1. 丢弃工作目录的变更
```
git checkout -- file
```

2. 从暂存区取消暂存
```
git reset HEAD file
```

3. checkout切换分支
```
git checkout new_branch # 切换分支
git checkout -b new_branch # 创建分支并切换分支
```

4. 利用checkout回退版本(HEAD处于游离状态)
```
git checkout commit_id # 此时指针处于游离状态
```

5. 接着利用下一命令可以将游离的指针，移到创建分支
```
git checkout -b new_branch 
```

6. 分支改名
```
git branch -m branch_1 branch_2
```

## stash
1. 将当前分支的所有修改临时保存起来
```
git stash
```

2. 查看所有保存状态
```
git stash list
```

3. 提交临时保存说明
```
git stash save 'message'
```

4. 将临时保存状态恢复出来，并把这个保存状态删除掉
```
git stash poo
```

5. 将临时保存状态恢复出来，不把这个保存状态删除掉
```
git stash apply
```

6. 手动删除
```
git stash drop stash@{number} 
```

7. 从任意一个临时状态恢复
```
git stash apply stash@{number}
```
