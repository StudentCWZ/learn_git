# 第十四讲 Git裸库与Git submodule
## Git裸库
没有工作区的Git仓库(一般在服务器端)
- 创建裸库命令
```
git init --bare # 没有工作区
```
## Git submodule
项目的相互协作(多模块开发-项目的依赖)
- 举例
-- 准备工作  
1.在GitHub上创建仓库git_parent和git_children  
2.在本地创建仓库git_parent和git_children  
3.在本地创建的仓库git_parent新建文件parent.txt,将修改纳入暂存区，并进行提交  
4.配置远程仓库git_parent信息  
5.将本地的git_parent提交推送到远程git_parent  
6.在本地创建的仓库git_children新建submodule.txt，将修改纳入暂存区，并进行提交  
7.配置远程仓库git_children信息  
8.将本地的git_children提交推送到远程git_children  
9.在本地创建的仓库git_childern新建hello.txt，将修改纳入暂存区，并进行提交  
10.将本地的git_children提交推送到远程git_children  
11.执行git submodule命令，将子依赖拉到主项目  
12.将文件修改纳入暂存区，接着进行提交    
13.如果git_childern发生变化，git_parent也随之变化 
- git submodule命令
```
git submodule git@github.com:gitlecture/git_children.git my module
```
- 拉取git_children更新
```
git pull # 在git_parent/mymodule目录下
```
- 拉取所有依赖子模块的所有更新
```
git submodule foreach git pull 
```
- 如果一个项目包含着submodelue，进行git clone操作的时候，默认情况下是不会把submodelue的代码克隆下来，需要手工的去执行一次
```
git clone git@github.com:gitlecture/git_parent.git parent2 # 克隆
git submodule init # submodelue初始化
git submodule update --recursive # 进行子模块更新
```
- 进行git clone操作时候，使用后面加参数将所有子模块的更新全部克隆下来
```
git clone git@github.com:gitlecture/git_parent.git parent3 --recursive
```
- 删除submodule(命令组合)
```
# 1.将submodule从缓存区删除
git rm --cached mymodule
# 2.将submodule的实体文件从工作区删除
rm -rf mymodule
git add .
git commit -m 'remove submodule'
git push
# 3.将.gitmodule目录删除
rm .gitmodules
git add .
git commit -m 'remove submodules'
git push
```

