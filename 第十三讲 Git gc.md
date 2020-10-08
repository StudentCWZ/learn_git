# 第十三讲 Git gc 
## git 垃圾收集
1. `git`垃圾收集主要用于做一些文件压缩，将分散在不同地方的文件给合并到一起，对一些对象通过一些手段将其所占体积减少。(`git gc`实际开发中使用很少，因为很多时候`git`后台自动运行)
2. 进入本地仓库
```
cd repository_name
```

3. 进入`refs`目录
```
cd refs
```

4. 进入`heads`目录
```
cd heads
ls
cat branch_name # 查看本地分支内容
```

5. 进入`remotes/origin`目录
```
cd remotes/origin
cat branch_name # 查看远程分支内容
```

6. 进入`tags`目录
```
cd tags
cat v1.0 # 查看标签内容
```

7. 运行`git gc`命令
```
git gc    # 文件压缩(git gc实际上把refs目录下的所有文件被打包到pached-refs目录下，增加新的提交信息，则该信息还是在refs的目录下)
```

8. `git`每次提交的对象保存到`.git/objects/info的packs`文件中(进行压缩后`.git/objects/info/packs`文件会被压缩到`.git/objects/pack`)


