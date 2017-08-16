##git教程

###安装Git

>windows版的Git,从[这里](https://git-for-windows.github.io)进行下载，然后按默认安装完成。在开始菜单里找到"git->Git Bash"就说明安装成功。

###创建版本库

>版本库又名仓库(repository),可进行版本管理的目录。
所以创建一个版本库，首先:

>     mkdir learngit  创建目录
>     cd learngit     打开目录
>     git init        初始化git

>完成本地创建git,此时当前目录多了一个.git的文件夹，无需我们手动去修改文件夹，不然容易把Git仓库给破坏。

>注意:如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见。

>####小结:
>
    1. 初始化一个Git仓库，使用git init命令。
    2. 添加文件到Git仓库,分两步:
       1. 使用密令git add <file>,注意，可反复多次使用，添加多个文件；
       2. 使用命令git commit,完成本地提交。


###其余命令建

1. git status命令可以让我们时刻掌握仓库当前的状态
2. git diff可以查看修改的内容
3. git log命令显示最近到最远的提交日志，如果先输入再多，可以加上--pretty==online参数。
4. git reset --hard HEAD~（数字）回退到历史版本
5. git reflog记录每一次的命令
6. git checkout --file修改全部撤销（修改工作区）
7. git reset HEAD 把暂存区的内容修改到工作区。
8. git rm用于从版本库删除文件。

###远程仓库

>需求:本地创建玩git仓库后，又想在GitHub创建一个Git仓库，使得两个仓库进行远程同步。

>     1. 在GitHub上创建好项目（名称最好和本地名称一致）
>     2. 在本地运行命令git remote add origin git@github.com:18671161309/git-direction.git进行关联
>     3. 把本地文件推送到Github运行git pish-u origin master

>碰到的问题:
>
>解决git error: failed to push some refs to 'git@github.com:

>出现这个错误是有远程文件并不在本地文件中，可以通过如下命令进行代码合并git pull --rebase origin master.

###分支管理

>每一次commit提交，git都会把它们串成一条时间线，这条时间线就成为一个分支（master分支），HEAD指向的就是当前分支。

>创建分支命令git checkout -b dev(命令加上-b参数代表切换)，相当于git branch dev->git checkout dev.

>查看当前分支git branch(该命令会列出当前所有分支)。

>合并分支，首先切换到要合并的分支，然后命令(gut merge dev)表示合并分支dev的内容。

>删除分支git branch -d dev（-d代表delete删除当前分支）

>Fast forward表示快速推进合并，在这种模式下删除分支会丢掉分支的信息，如果要强制禁用Fast forward模式，我们可以使用git merge --no-ff -m(加上描述合并信息)file

###BUG分支
>git stash（该命令是把当前工作储藏起来，等以后回复现场后继续工作），然后使用git stash pop回到工作现场。

>git branch -D <file>强制性删除文件

>查看远程库的信息git remote -v

>推送分支 git push origin master
>拉取远程分支git pull

>     注意:使用git pull碰到There is no tracking information for 
>     the current branch.Please specify which branch you want 
>     to merge with.
>     解决:git branch --set-upstream dev origin/dev

###标签管理
>git打标签，首先切换到需要打标签的分支上，然后git tag<name>就可以打一个新标签。用git tag查看所有标签。

