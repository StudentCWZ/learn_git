# 第十三讲 Git gc 
## git垃圾收集
- git垃圾收集主要用于做一些文件压缩，将分散在不同地方的文件给合并到一起，对一些对象通过一些手段将其所占体积减少。(git gc实际开发中使用很少，因为很多时候git后台自动运行)
- 进入本地仓库
```
cd repository_name
```
- 进入refs目录
```
cd refs
```
- 进入heads目录
```
cd heads
ls
cat branch_name # 查看本地分支内容
```
- 进入remotes/origin目录
```
cd remotes/origin
cat branch_name # 查看远程分支内容
```
- 进入tags目录
```
cd tags
cat v1.0 # 查看标签内容
```
- 运行git gc命令
```
git gc # 文件压缩(git gc实际上把refs目录下的所有文件被打包到pached-refs目录下，增加新的提交信息，则该信息还是在refs的目录下)
```
- git每次提交的对象保存到.git/objects/info的packs文件中(进行压缩后.git/objects/info/packs文件会被压缩到.git/objects/pack)


