[主页](https://wugongxi.github.io/#!index.md "主页")

##git 相关命令整理

git remote update origin --prune  更新远程分支列表
git 切换分支：git checkout -b 2.2.0 origin/2.2.0
git 查看所有分支：git branch -a
git branch -r       #查看远程所有分支

git branch           #查看本地所有分支

git branch -a       #查看本地及远程的所有分支，如下图

git fetch   #将某个远程主机的更新，全部取回本地：

git branch -a  #查看远程分支

git branch  #查看本地分支：

git checkout 分支 #切换分支：

git push origin -d 分支名  #删除远程分支

git branch -d 分支名  #删除本地分支

git remote show origin  #查看远程分支和本地分支的对应关系

git remote prune origin #删除远程已经删除过的分支



