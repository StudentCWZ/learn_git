# 第十一讲 Git refspec
## Git别名
- 配置别名
```
git config --global alias.br branch # 配置信息在~/.gitconfig文件下
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.unstage 'reset HEAD'
git config --global alias.ui '!git'
```
## Git refspec
### git push相关操作
- git push操作的完整命令
```
git push origin srcbranch:destbranch # 建议的git push命令
```
- 将本地分支推送到远程
```
git push --set-upstream origin branch_name # 将本地分支推送到远程(默认远程分支名与本地一样)
git push -u origin branch_name # 跟上一条命令一样效果
git push --set-upstream origin branch_name:branch_new_name # 将本地分支推送到远程并且远程分支名与本地所关联的分支不同名
# 如果不同名，则进行git push操作，则要执行以下命令
git push origin HEAD:branch_new_name # 尽可能同名(不同名无法简写git push命令)
```
### git pull相关操作
- git pull操作的完整命令
```
git pull origin srcbranch:destbranch
```
- 将远程分支拉到本地
```
git pull # 将远程所有分支改变都拉到本地
git checkout -b branch_name origin/branch_name # 创建跟远程分支同名的本地分支，并关联。
git checkout --track origin/branch_name分支来追踪 # 本地创建同名的branch_name分支来追踪origin/branch_name(与上一条命令意思完全一样)
```
- 删除远程分支
```
git push origin :branch_name # 将本地的一个空分支推送到远程某个分支(意味着删除远程的该分支)
git push origin --delete branch_name # 与上一个命令一样效果
```
- 重命名远程分支(步骤)  
1.删除远程分支  
2.本地重命名分支  
3.将本地重命名后的分支推送到远程

### HEAD文件相关内容
- HEAD标记  
1.HEAD文件是一个指向你当前所在分支的引用标识符，该文件内部并不包含SHA-1值，而是包含一个指向另外一个引用的指针。  
2.当执行git commit命令时，git会创建一个commit对象，并且将这个commit对象的parent指针设置为HEAD所指向的引用的SHA-1值。  
3.我们对于HEAD修改的任何操作都会被git reflog完整记录下来。  
4.实际上，我们可以通过对git底层命令symboic-ref来实现对HEAD文件内容的修改。
```
git symbolic-ref HEAD # 读取
git symbolic-ref HEAD refs/heads/branch_name # 写入
```

