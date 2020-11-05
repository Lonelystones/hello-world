##### 初始化git本地仓库
`git init`

##### 修改文件时间属性到最新
`touch filename.suffix`

##### 查看可用配置列表
`git config --list`

##### 查看用户名和邮箱
`git config user.name`

`git config user.email`

##### 设置全局/局部用户名和邮箱
###### //--global参数表示全局，去掉则为单个仓库设置用户名
`git config --global user.name "username" `

###### //--global参数表示全局，去掉则为单个仓库设置邮箱
`git config --global user.email "email"` 

##### 将本地仓库与远程仓库关联 remoteAddr为远程仓库地址
`git remote add origin remoteAddr`

##### 添加文件到暂存区 git add [参数] [--] <路径>
###### //添加单个或多个指定文件
`git add filename1.suffix filename2.suffix`

###### //添加新文件(new)、和被修改的(modified)文件，**不包括**被删除的(deleted、)文件，`.`表示当前文件夹
`git add .`

###### //添加被修改的(modified)和被删除的(deleted)文件，**不包括**新文件，`.`表示当前文件夹
`git add -u .`

###### //添加所有变化的文件，`.`表示当前文件夹
`git add -A .`

##### 提交更改
###### //提交暂存区中的文件到版本库并添加备注
`git commit -m "备注信息"`

###### //将已追踪的文件添加到暂存区提交并添加备注（相当于`git add .`和`git commit -m ""`的结合）
`git commit -am "备注信息"`或者`git commit -a -m "备注信息"` //-a -m顺序不能改变