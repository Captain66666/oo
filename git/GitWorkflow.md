# Git Workflow

## Basics

Git分工作区 暂存区和版本库

- 工作区指电脑中能看到的目录
- 暂存区(stage/index) 一般存放在`.git`目录下的index文件中 所以暂存区有时也称作索引
- 版本库 工作区中的`.git`目录就是Git版本库

Git的模型实际上是指向更改快照的指针

## Branch Control

```shell
# 创建分支命令
git branch (branchname)
# 切换分支
git checkout (branchname)
# 合并分支
git merge

# 没有参数时 branch会列出你在本地的分支
git branch
# 立即创建新分支并立即切换到该分支下
git checkout -b (branchname)
# 删除分支
git branch -d (branchname)
# 将分支合并到现分支
git merge (branchname)
# 当出现冲突时 查看文件的不同
git diff
# 历史提交记录
git log
# 查看指定文件的修改记录
git blame <file>
# 为代码打上标签
git tag (content)
# 查看所有标签
git tag
# 改变分支的基
git rebase
```

## Conflict

##### merge conflict

出现冲突时 可以使用`git diff`命令查看不同

手动修复冲突后 再使用`git add`命令提交

提交完成后 使用`git merge --continue`继续之前的merge

##### pull conflict

`git pull`命令相当于将远程分支的修改同步到本地并合并 相当于`git fetch`+`git merge HEAD`

`git pull --rebase`命令相当于`git fetch`+`git rebase HEAD`

rebase的冲突的解决与merge冲突相似 最后的命令更改为`git rebse --continue`即可