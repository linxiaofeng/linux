# git

分布式版本控制系统

### 安装git
ubuntu使用`sudo apt-get install git`安装git

安装完成后，配置git
```
$ git config --global user.name "Your name"
$ git config --global user.email "email@email.com"
```

### 创建版本库
使用`git init`把目录变成git仓库

### 文件操作

使用`git status`查看当前状态

使用`git add <file>`向暂存区中添加文件

使用`git commit -m 'log'`将暂存区文件添加到版本库中

使用`git diff <file>`查看文件的修改情况

使用`git rm <file>`删除文件

### 日志操作

使用`git log`查看提交日志

使用`git reflog`记录每次命令

### 版本控制操作

使用`git checkout -- <file>`撤销工作区的修改，恢复到暂存区或版本库一致的状态

使用`git reset HEAD <file>`可以撤销暂存区中的修改

使用`git reset --hard VERSION`回滚，`VERSION`可以为`哈希值`、`HEAD^`上一版本、`HEAD^^`上上版本、`HEAD~100`往上100个版本

### 分支操作

使用`git checkout -b BRANCH_NAME`创建并切换分支，等效于`git branch BRANCH_NAME`创建分支和`git checkout BRANCH_NAME`切换分支两个命令

使用`git branch`列出所有分支

使用`git merge NAME`将NAME位置合并到当前分支

使用`git branch -d NAME`删除NAME分支

### 工作区暂存操作
使用`git stash`将工作区的修改保存

使用`git stash list`查看暂存的工作区修改

使用`git stash pop`将暂存的工作区修改，恢复到工作区，等效于`git stash apply`+`git stash drop`

### github操作

使用`git remote add origin REMOTE_REPOSITORY_URL`将本地版本库与github中的版本库相关联

使用`git remote rm origin`删除github上的origin版本库

使用`git push origin master`将本地版本库内容推送到github远程库中

使用`git pull`将远程库中内容拉取到本地库中

使用`git clone URL`将远程库中内容克隆到本地库中

