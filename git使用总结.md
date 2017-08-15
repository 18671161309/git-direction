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

