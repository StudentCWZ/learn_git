# 第八讲  标签与diff
## Git标签
- 新建标签，标签有两种：轻量级标签(lightweight)与带有附注标签(annotated)
- 创建一个轻量级标签
```
git tag v1.01
```
- 创建一个带附注的标签
```
git tag -a v1.02 -m 'release version'
```
- 查看所有标签
```
git tag
```
- 查找标签(模糊查找和精确查找)
```
git tag -l 'v1.0'
```
- 删除标签
```
git tag -d tag_name
```
- git blame命令(定位文件修改的信息)
```
git blame file # 可以查看该文件所有修改者信息
```
## diff
### 系统自带的diff
- 系统自带diff对比文件差别
```
diff file_1 file_2 
```
- 详细系统自带diff对比文件差别
```
diff -u file_1 file_2
```
### Git中diff
- 进行工作区与暂存区之间的文件差别对比(暂存区文件作为原始文件)
```
git diff # 比较的是暂存区与工作区文件之间的差别。(将工作区文件修改，暂存区不动，进行差异性比较。)
```
- 进行工作区与特定commit_id之间文件的差别比较(版本库的文件作为原始文件)
```
git diff commit_id
```
- 进行工作区与最新的提交之间文件的差别比较(版本库的文件作为原始文件)
```
git diff HEAD 
```
- 进行暂存区与某一特定commit_id之间文件的差别比较(版本库的文件作为原始文件)
```
git diff --cached commit_id
```
- 进行暂存区与最新的提交之间文件的差别比较(版本库的文件作为原始文件)
```
git diff --cached
```

