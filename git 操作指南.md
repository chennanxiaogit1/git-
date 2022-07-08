1.撤回 工作区的修改 git checkout -- <flie>  即可回到最近一次 git add 的工作区状态

2.撤回 暂缓区的修改 git restore --staged <flie> 即可回到最近一次 git commit 的暂缓区状态

3.撤回 本地仓库的修改 git **revert**/reset [commit-id] 切换版本库  git revert建议使用(会生成一条新的记录而不是销毁之前记录)

4.删除文件  (暂缓区或者 版本库中都可以删除)  git rm <flie> 删除之后再用 git commit 做个记录



5.git switch -c <分支名>  创建并切换到新的分支上  git branch -d <删除的分支名>

6.要将分支合并通过在合并的主分支上使用 git merge <被合并的分支名>  合并分支时可能出现冲突,需要手动修改

 7.bug分支:先用git stash 将工作区的内容隐藏起来,再git switch -c bug分支，最后通过git stash pop将隐藏的内容重新显示出来, 使用git cherry-pick commit_id 将bug修复的内容添加到当前的分支上

8.git push <远程的仓库名> <本地的分支名> 将本地分支的内容推送到远程对应的分支上

9.一般要建立本地分支和远程分支的相关联

