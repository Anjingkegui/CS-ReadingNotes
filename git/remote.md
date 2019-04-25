#### 1.

#### key

`ssh-keygen -t rsa -C "youremail@example.com"`

#### remote

`git remote add origin git@server-name:path-name/repo-name.git`

#### push

`git push -u origin master`

`git push --set-upstream origin master`

`-u` 参数还会将分支与远程分支关联起来

当然也可以手动关联远程分支 `git branch --set-upstream-to=origin/master master`

#### pull

#### branch

* `HEAD`严格来说不是指向提交，而是指向分支，分支才是指向提交的

![](/assets/2019424151.png)

* `git checkout -b dev` = `git branch dev` + `git checkout dev` 

`branch` 用来新建分支，`git branch -vv` 便于查看所有分支

`checkout` 用来切换分支，其实就是在改`HEAD` 的指向

* `git branch -d xx` 用来删除分支，`-D` 为强制删除

* `git merge` 命令用于合并指定分支到当前分支

master分支上的一次典型的合并

![](/assets/2019425103.png)

#### ![](/assets/2019425104.png)

说的

#### 冲突解决

修改那些冲突的文件

再正常add+commit就好

#### 协作

多人协作的工作模式通常是这样：

    首先，可以试图用`git push origin <branch-name>`推送自己的修改；

    如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；

    如果合并有冲突，则解决冲突，并在本地提交；

    没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

    如果`git pull`提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`。

#### rebase - 解决merge造成的混乱的历史记录



