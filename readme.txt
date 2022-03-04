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
