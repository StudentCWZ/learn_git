# 第十五讲 Git subtree与Git cherry-pick
## Git subtree
- Git submodlue如果在主项目修改依赖项目会造成很多问题，Git subtree和Git submodlue解决问题一样，Git subtree可以解决针对双向修改  
1. 新建git_subtree_parent和git_subtree_children两个工程(远程仓库)，其中git_subtree_children是子工程。  
2. 在本地创建仓库git_subtree_parent和git_subtree_children   
3. 在本地创建的仓库git_subtree_parent新建文件parent.txt,将修改纳入暂存区，并进行提交   
4. 配置远程仓库git_subtree_parent信息  
5. 将本地的git_subtree_parent提交推送到远程git_subtree_parent中  
6. 在本地创建的仓库git_subtree_children新建children.txt，将修改纳入暂存区，并进行提交  
7. 配置远程仓库git_subtree_children信息  
8. 将本地的git_subtree_children提交推送到远程git_subtree_children  
9. 在本地创建的仓库git_subtree_children新建hello.txt，将修改纳入暂存区，并进行提交  
10. 将本地的git_subtree_children提交推送到远程git_subtree_children  
11. 在主项目关联子项目的远程库  
12. 执行git subtree命令，将子依赖拉到主项目
13. 如果git_childern发生变化，git_parent也随之变化  
14. 在主工程的git_subtree_parent/subtree目录下修改文件childern.txt,将修改纳入暂存区，并进行提交  
15. 将本地的git_subtree_parent/subtree目录下修改推送到远程git_subtree_parent中  
16. 将本地的git_subtree_parent/subtree目录下修改推送到远程git_subtree_children
- 在主项目关联子项目的远程库命令
```
git remote add subtree-origin git@github.com:gitlecture/git_subtree_children.git
```
- 执行git subtree命令
```
git subtree add --prefix=subtree subtree-orign master --squash # squash参数表示子项目的多次提交被压缩成一次提交
```
- 拉取git_subtree_children更新
```
git subtree pull --prefix=subtree subtree-origin --squash # squash也可以不用(注意：要是不用就所有subtree命令不用，要用就所有subtree命令都用)
```
- 将本地的git_subtree_parent/subtree目录下修改推送到远程git_subtree_parent中
```
git push
```
- 将本地的git_subtree_parent/subtree目录下修改推送到远程git_subtree_children
```
git subtree push --prefix=subtree subtree-origin master
```
- 将远程的git_subtree_children拉到本地git_subtree_children
```
git pull # 在git_subtree_children目录下
```
## Git cherry-pick
- 作用：将在一个分支的修改应用到另一个分支上(主要用于本地分支)
- 将一个分支的修改应用到另一个分支上(例如将在develop分支的修改应用于master分支)
```
git cherry-pick commit_id # 将其他分支的一个提交所做的修改应用到当前分支
```

