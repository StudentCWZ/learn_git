# 第十二讲  Git远程标签  
## 远程标签
- 列出本地的所有标签
```
git tag
```
- 创建一个轻量级标签
```
git tag v1.0
```
- 创建带注释的标签
```
git tag -a v2.0 -m 'v2.0 released'
```
- 查看标签内容
```
git show v1.0
```
- 搜索标签
```
git tag -l 'v' # 利用通配符
```
- 推送标签到远程
```
git push origin v1.0
git push origin v1.0 v2.0 # 少数标签
git push origin --tags # 将标签 批量推送到远程
```
- 删除远程标签
```
git push origin :refs/tags/v1.0
git push origin --delete tag v1.0
```
- 将本地标签推送到远程的完整语法
```
git push origin refs/tags/v1.0:refs/tags/v1.0
```
- 只从远程拉取标签
```
git fetch origin tag v1.0
```
- 显示远程信息
```
git remote origin show
```
- 删除远程游离的分支
```
git remote prune origin # 通常删除分支后的操作
```
- 在缺省的情况下，refspec会被git remote add命令所自动生成，Git会获取远端上refs/heads下的所有引用，并将他们写到本地的refs/remotes/origin目录下。所以，如果远端上有一个master分支，本地就可以通过下面几种方式来访问它们的历史记录：
- 查看远程分支的历史记录(3种方式)
```
git log origin/matser
git log remotes/origin/master
git log refs/remotes/origin/master
```
- 将远程的某个分支的内容拉取到本地的新远程分支
```
git fetch origin master:refs/origin/mymaster
```
- 在本地创建新分支并追踪本地的远程分支
```
git checkout --track origin mymaster
```

