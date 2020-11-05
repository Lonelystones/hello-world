#### 初始化git本地仓库
`git init`

#### 修改文件时间属性到最新
`touch filename.suffix`

#### 查看可用配置列表
`git config --list`

#### 查看用户名和邮箱
`git config user.name`

`git config user.email`

#### 设置全局/局部用户名和邮箱
###### --global参数表示全局，去掉则为单个仓库设置用户名
`git config --global user.name "username"`

`git config --global user.email "email"` 

#### 将本地仓库与远程仓库关联 remoteRepoAdde为远程仓库地址
`git remote add origin remoteRepoAdde`

#### 取消与远程仓库的关联
`git remote rm origin` //rm可以用remove代替

#### 克隆远程仓库并建立关联 remoteRepoAdde为远程仓库地址
`git clone remoteRepoAdde`

#### 从远程分支中拉取代码`git pull <远程主机> <remote_branch>:<local_branch>`
###### 将当前远程分支同步到当前本地分支
`git pull`

###### 将指定远程分支同步到当前本地分支
`git pull origin master`

###### 将指定远程分支拉取到指定本地分支，比如：当前分支是dev，但是你想把远程master”同步”到本地master，但又不想使checkout切换到master分支，这时你就可以使用git pull origin master:master
`git pull origin master:master`

#### 添加文件到暂存区 git add [参数] [--] <路径>
###### 添加单个或多个指定文件
`git add filename1.suffix filename2.suffix`

###### 添加新文件(new)、和被修改的(modified)文件，不包括被删除的(deleted、)文件，`.`表示当前文件夹
`git add .`

###### 添加被修改的(modified)和被删除的(deleted)文件，不包括新文件，`.`表示当前文件夹
`git add -u .`

###### 添加所有变化的文件，`.`表示当前文件夹
`git add -A .`

#### 提交更改
###### 提交暂存区中的文件到版本库并添加备注
`git commit -m "备注信息"`

###### 将已追踪的文件添加到暂存区提交并添加备注（相当于`git add .`和`git commit -m ""`的结合）
`git commit -am "备注信息"`或者`git commit -a -m "备注信息"`

#### 推送更新git push <远程主机> <本地分支>:<远程分支>
###### 推送指定本地分支到远程主机的指定分支，与pull命令格式相仿
`git push origin master:master`
###### 如果省略远程分支名，则表示将本地分支推送到与之存在“追踪关系”的远程分支（通常两者同名），如果该远程分支不存在则会被创建
`git push origin master`
###### 如果省略本地分支名则表示删除指定远程分支，因为这等同于推送一个空的本地分支到远程分支，等同于`git push origin --delete master`
`git push origin :master` 等同于 `git push origin --delete master`
###### 如果当前本地分支与远程分支存在“追踪关系”，则本地分支和远程分支都可以省略
`git push origin`
###### 如果当前分支只有一个追踪分支，则远程主机名也可以省略
`git push`
###### 如果当前分支与多个主机存在“追踪关系”，则可以使用-u推送并指定一个默认主机，这样以后推送到相同主机的相同分支就可以不加任何参数使用`git push`
`git push -u origin master`