# 分支管理

## 查看远程分支

```
git branch -a
```

### 删除远程分支

Git 1.7.0 以后 ，删除远程分支：

```
git push origin --delete <branchName>
```

删除 tag：

```
git push orgin --delete tag <tagname>
```

### 重命名分支

If you want to rename a branch while pointed to any branch, do:

```
git branch -m <oldname> <newname>
```

If you want to rename the current branch, you can do:

```
git branch -m <newname>
```

A way to remember this, is `-m` is for "move" (or `mv`), which is how you rename files.

## Git 合并分支

查看分支：git branch或者git branch -v；可以用下面的命令来查看temp分支的从属关系信息，git config -l | grep 'branch\.temp'  。

　　A) 创建分支
　　git branch mystudygit1.0
　　
　　B) 切换分支
　　git checkout mystudygit1.0
　　
　　C) 删除分支
　　git branch -d mystudygit1.0  //如果该分支没有合并到主分支会报错或者git branch -D mystudygit1.0   //强制删除。
　　
　　D) 分支合并
　　比如，如果要将开发中的分支（develop），合并到稳定分支（master），首先切换的master分支：git checkout master。然后执行合并操作：git merge develop。如果有冲突，会提示你，调用git status查看冲突文件。解决冲突，然后调用git add或git rm将解决后的文件暂存。所有冲突解决后，git commit 提交更改。
　　例如：将acc2f69提交合并到当前分支
　　git merge acc2f69