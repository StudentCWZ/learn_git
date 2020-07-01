# 第二讲  Git入门指引
## Git简史
- Linux内核开源项目有着位数众多的参与者。一开始整个项目组使用BitKeeper来管理和维护代码。2005年，BitKeeper不再能免费使用，这就迫使Linux开源社区开发一套属于自己的版本控制系统。


- 自诞生于2005年以来，Git日臻成熟完善，它的速度飞快，极其适合管理大型项目，它还有着令人难以置信的非线性分支管理系统，可以应付各种复杂的项目开发需求。


- 众多的开源、非开源项目已经逐步由SVN迁移到Git。

## CVS、SVN与Git
-  集中式版本控制系统(CVCS)
-  分布式版本控制系统(DVCS)
- 有了Git，编程真正成了一种乐趣。


## Git、GitHub与GitLab
- Git是一个版本控制软件
- GitHub与GitLab都是用于管理版本的服务端软件
- GitHub提供免费服务(代码需公开)以及付费服务(代码私有)
- GitLab用于在企业内部管理Git版本库，功能上类似于GitHub


## Git设计目标
- 快速
- 简单(学习曲线陡峭)
- 高效存储
- 完全分布
- 满足大规模项目需要


## Git优点
- 本地建立版本库
- 本地版本控制
- 多主机异地协同工作
- 重写提交说明
- 有后悔药可以吃
- 更好用的提交列表
- 更好的差异比较
- 更完善的分支系统
- 速度极快


## Git的工作模式
- 版本库初始化   
1. 个人计算机从版本服务器同步
- 操作  
1. 90%以上的操作在个人计算机上  
2. 添加文件  
3. 修改文件  
4. 提交变更  
5. 查看版本历史等  
- 版本库同步  
1. 将本地修改推送到版本服务器

## Git基础
- 直接记录快照，而非差异比较
- 近乎所有操作都在本地执行
- 时刻保持数据完整性
- 多数操作仅添加操作
- 文件的三种状态  
1. 已修改(modified)  
2. 已暂存(staged)  
3. 已提交(committed)  

## Git文件状态
- Git文件  
已被版本库管理的文件
- 已修改  
在工作目录修改Git文件
- 已暂存  
对已修改的文件执行Git暂存操作，将文件存入暂存区
- 已提交  
将已暂存的文件执行Git提交操作，将文件存入版本库

## Git安装
- Linux(Ubuntu)
```
sudo apt-get install git
```
- Mac  
1. 安装命令行工具(如已安装Xcode，命令行工具会在首次启动Xcode时提示安装)  
2. homebrew
- 安装homebrew
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
- homebrew具体命令使用查询
```
brew help
```
3. macports
- Windows  
1. 通过msysGit(http://code.google.com/p/msysgit)。  
2. 完成安装之后，就可以使用命令行的git工具(已经自带了ssh客户端)了，另外还有一个图形界面的Git项目管理工具。  
3. 建议使用Git命令行，方便又快捷，GUI反而繁琐。  
4. 如果需要使用GUI，推荐使用SourceTree，拥有Mac与Windows版本；此外，Windows下还可以使用TortoiseGit。


## Git常用命令
- 获得版本库
```
git init # 版本库初始化(本地创建git版本库)
git clone # 克隆远程版本库
```
- 版本管理
```
git add # 将已修改的文件从工作区纳入到暂存区
git commit # 将暂存区文件提交到git本地版本库
git rm # 删除文件
```
- 查看信息
```
git help # 查看git命令使用
git log # 查看日志
git diff # 查看文件不同状态的差异
```
- 远程协作
```
git pull # 将远程版本库当中的文件拉到本地
git push # 将本地版本库当中的版本内容推送到远程
```








