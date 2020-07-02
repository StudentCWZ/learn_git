# 第九讲 远程与GitHub
## 远程版本库(GitHub)
- Github官网网址
```
url = 'https://github.com/'
```
- 注册账号  
1. 利用邮箱注册账号(公共仓库)
- 将本地仓库推送到GitHub上
```
# 1.初始化仓库
git init repository_name
# 2.配置信息 
git config --global user.name 'name'
git config --global user.email 'email'
# 修改配置的命令
git config --unset user.name
git config --unset user.email
# 3.修改文件
# 4.将修改纳入暂存区
# 5.进行提交
# 6.本地版本库推送
1) 对GitHub进行配置
2) 新建README.md进行说明，并提交到本地版本库
3) 现在网页上创建一个远程仓库
4) 推送到远程命令
```
- 本地版本库推送
```
git remote add origin https://github.com/repository_name.git # 远程仓库的url
git push -u origin master # 将本地的master分支推送到远程
```

