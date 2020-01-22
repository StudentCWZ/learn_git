# 第四讲 Git添加、删除、修改与日志
## Git常用命令
- 创建文件(利用echo)
```
echo 'hello world' > file # 文件重定向
```

- 删除文件(git rm)
```
git rm file # 先删除文件并把这次修改纳入暂存区。
```
- 利用git rm删除文件可以利用以下两次命令恢复
```
git reset HEAD file # 将文件从暂存区回退到工作区
git checkout -- file # 将工作区的文件修改全部丢弃(未纳入暂存区的文件修改)
```

- 删除文件(系统命令rm)
```
rm file # 删除文件但并未把这次修改纳入暂存区
```
- 利用系统命令rm删除文件可以利用以下一条命令恢复
```
git checkout -- file # 将工作区的文件修改全部丢弃(未纳入暂存区的文件修改)
```


- 利用git mv进行文件重命名(实际意义:将原文件删除并创建一个新的和原文件一样的文件并把这次修改纳入暂存区)
```
git mv file file_1 # 先将文件进行重命名并把这次修改纳入暂存区
```
- 利用git mv进行文件重命名可以利用以下操作恢复
```
git reset HEAD file
git reset HEAD file_1
git checkout -- file
rm file_1
```


- 利用系统命令mv进行文件重命名(实际意义:将原文件删除并创建一个新的和原文件一样的文件并未把这次修改纳入暂存区)
```
mv file file_1 # 并未把这次修改纳入暂存区
```
- 利用系统命令mv进行文件重命名可以利用以下操作恢复
```
git checkout -- file
rm file_1
```

- 将当前目录以及当前目录子目录的所有文件同时纳入暂存区
```
git add .
```

- commit message提交错误进行修正
```
git commit --amend -m 'message_1' # 修正上一次的commit message
```

- 查看日志
```
git log -n # 查看最近n条日志
git log --pretty=oneline 日志以一行的简单方式呈现
```
- 获取帮助(获取config帮助)
```
git help config
git config --help
man git-config
```

