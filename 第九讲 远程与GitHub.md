# 第九讲 远程与 GitHub
## 远程版本库(GitHub)
1. [Github官网网址](https://github.com/)
2. 注册账号
3. 利用邮箱注册账号(公共仓库)
4. 将本地仓库推送到`GitHub`上
```
# 初始化仓库
git init repository_name
# 配置信息 
git config --global user.name 'name'
git config --global user.email 'email'
# 修改配置的命令
git config --unset user.name
git config --unset user.email
# 修改文件
# 将修改纳入暂存区
# 进行提交
# 本地版本库推送
(1) 对GitHub进行配置
(2) 新建README.md进行说明，并提交到本地版本库
(3) 现在网页上创建一个远程仓库
(4) 推送到远程命令
```

5. 本地版本库推送
```
git remote add origin https://github.com/repository_name.git # 远程仓库的url
git push -u origin master # 将本地的master分支推送到远程
```

