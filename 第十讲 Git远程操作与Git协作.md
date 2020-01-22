# 第十讲 Git远程操作与Git协作
## Git远程操作
- 建立SSH安全连接  
```
# 1.配置远程
git remote add orgin git@github.com:repository_name/repository_name.git # 远程仓库SSH链接地址
git remote show orgin
# 2.把公钥放置远程
cd .ssh
ls
vi known_hosts
which ssh-keygen # 生成公钥
ssh-keygen # 生成公钥(敲入命令回车，要求输入密码连续两次回车)
ls id_rsa.pub # 进入公钥文件夹(把公钥粘贴放置GitHub中settings的Deploy keys上面)
# 3.把本地分支推送到远程
git push -u orgin master # 将本地的master分支推送到远程
```
- 查看所有远程仓库的别名
```
git remote show
```
- 查看远程仓库所有信息
```
git remote show repository_name
```
- 重命名远程仓库
```
git remote rename origin origin2
```
- 删除远程仓库
```
git remote rm origin
```
- 删除之后再次创建
```
git remote add orgin git@github.com:repository_name/epository_name.git
```

## 更新git
- 查看git版本
```
git --version
```
- 查看git的位置
```
which git
```
- 查看mac的系统环境
```
echo $PATH
```
- 修改环境目录
```
vi .zshrc
```
- 安装新版git
```
# 新增的git一般被安装在usr/local/git中 
```
## git协作

- 查看所有远程仓库的名字
```
git remote show
```
- 查看所有远程仓库的详细信息
```
git remote show remote_repository_name
```
- 关联远程(过程理解)
```
# 与远程关联之后，本地有一个master分支，还有一个origin/master分支(追踪着远程版本库的mater分支)
# 进行git pull操作，git会将远程的修改拉到本地，同时将origin/master分支的commit_id对应到远程master最新的那次提交,如果这种合并是可以直接合并，git会将远程的master分支直接合并到本地的master分支上。
# 进行git push操作，git会将本地的origin/master分支最新的commit_id指向本地的master分支上，将本地的master的分支内容push到远程
```

- 查看远程分支
```
git branch -a # 查看所有远程分支
git branch -av # 查看所有远程分支以及其最新的提交commit_id
```

## 拉取代码操作
- 拉取远程代码(克隆)
```
git clone repository_url_ssh
```
- 拉取远程代码并重命名仓库
```
git clone repository_url_ssh repository_new_name
```
## git pull与git fetch区别
- git fetch
```
git fetch # 一定会成功的(不执行合并操作，仅仅是将远程的修改拉到本地，更新本地的orgin/master)
git merge orgin/master # 将本地的orgin/master的修改merge到本地的master分支上
```
- git pull == git fetch + git merge

## 项目开发
1.Gitflow  
2.关于Git分支的最佳实践(基于Git分支的开发模型)  
(1).master分支(生产发布)--生产发布分支，变化非常不频繁的一个分支  
(2).test分支(测试)--供测试与产品人员使用的一个分支，变化不是特别频繁  
(3).develop分支(开发)--频繁变化的一个分支  
(4).hotfix分支(修复bug分支)--生产系统当中出现了紧急bug，用于紧急修复的分支


