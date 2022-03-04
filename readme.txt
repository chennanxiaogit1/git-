git的初始化
初始化一个Git仓库，使用git init命令。

添加文件到Git仓库，分两步：

1.使用命令git add <file>，注意，可反复多次使用，添加多个文件；
2.使用命令git commit -m <message>，完成。

git版本回退
（1）时光穿梭
1.HEAD指向的是当前的版本,使用git reset --hard commit_id 可以实现版本切换
2.git reflog可以命令历史  找到对应的commit_id
（2）暂缓区
1.git add 就是将文件添加到GIT仓库的暂缓区中
2.git commit 就是将暂缓区中的文件 提交到master分支上
（3）撤销修改
1.文件只是在工作区的修改  git restore file
2.文件添加到了暂缓区 git restore --staged <file>将其退回到工作区修改
（4）删除文件
1.git rm <file> 删除版本库中的文件 
2.git checkout -- <file>将版本库中的文件替换工作区中的文件(误删的情况下)

分支管理:
分支的基本命令:
git branch -b<name>删除分支   git switch -c <name>切换分支和创建  git merge <name>将分支合并到当前的分支上 

分支冲突:
当分支冲突的时候将其内容手动编辑为我们自己想要的内容再add commit 
bug分支：
1.当手头的工作还没有完成  先git stash下 然后创建bug分支 等bug修复之后 git stash pop
2.在master分支上修复的bug，想要合并到当前dev分支，可以用git cherry-pick <commit>命令，把bug提交的修改“复制”到当前分支，避免重复劳动。
feature分支：
丢弃一个没有被合并过的分支,可以通过git branch -D <name>强行删除

多人协作开发:
1.查看远程库信息，使用git remote -v；
2.本地新建的分支如果不推送到远程，对其他人就是不可见的；
3.从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交
4.在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；
5.建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；
6.从远程抓取分支，使用git pull，如果有冲突，要先处理冲突