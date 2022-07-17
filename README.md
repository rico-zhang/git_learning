# git配置
pwd 显示当前目录
ls 显示当前目录下的文件
ls -al显示文件详细信息
![配置全局user]("./imgs/git-config-1.png")
![其他配置命令]("./imgs/git-config-2.png")

#获取帮助
详细帮助

* git help <verb> 
* git <verb> --help
* man git-<verb>

简略帮助

* git <verb> -h

#第一个仓库
## 初始化 
初始化后会建立一个.git的隐藏文件夹

* git init  在已有的项目中初始化
* git init yourproject 初始化一个新的git项目

## 添加文件到暂存区
git add readme.txt 添加指定文件 多个文件或文件夹用空格分隔
git add -u 添加所有已被跟踪的文件到暂存区
## 查看状态
git status
## 提交 将暂存区的文件提交到仓库
git commit -m 'add readme.txt'
## 查看日志
git log

#git区域
![]("./imgs/git-area-1.png")


#重命名文件
1. 在工作区重命名  
 1.  mv readme.md readme.txt
 2.  git rm readme.md
 3.  git add readme.txt
 4.  git commit -m 'rename readme'

2. 使用git重命名
 1. git mv readme.md readme.txt
 2. git commit -m 'rename readme' 

> git reset --hard 重置暂存区与工作目录 

# 查看历史版本
* git log
* git log --oneline
* git log -n4
* git log --all
* git log --graph

* git branch -av 查看本地的分支
* git branch branchname 创建分支
* git checkout branchname 切换分支
* git check -b branchname 创建并切换分支 

#图形界面工具
gitk 打开图形界面工具
gitk --all 打开所有分支

#探秘.git目录
* HEAD ： 记录当前是在哪个分支上
* config ： 记录当前仓库的配置信息
* refs ：里面有heads(分支) 和 tag 两个文件夹
* objects ： 存放文件内容
* cat filename ： 可以产看文件内容
* git cat-file-t 哈希值 ：查看对象类型
* git cat-file-p 哈希值 ：查看文件内容

# commit tree blob
* commit :每次提交就产生一个commit对象
* tree：表示目录
* blob：表示文件

每次提交都记录了当时的一个快照
![]("./imgs/git-object-1.png")

#分支
* git branch -av 查看所有分支
* git branch 查看当前分支
* git branch -d branchName 删除分支
* git branch -D branchName 删除分支（强制删除）

# 修改提交信息
## 修改最近一次提交
git commit --amend
## 修改之前提交
比较麻烦 用到的时候看视频

# 合并提交
比较麻烦 用到的时候看视频

# 比较
默认比较全部文件的差异 命令后可以加 -- fielname 单独比较这一个文件的差异 可以添加多个文件 用空格隔开
## 比较暂存区与最近一次提交的差异
git diff --cached 
## 比较工作区与暂存区的差异
git diff
## 比较不同提交之间的差异
* git diff master temp --[filename] 比较master分支与temp分支最近一次提交的差异
* git diff 343522 24522 --[filename] 比较343522commit与24522commit的差异

#恢复
## 将暂存区恢复成最近一次提交
git reset HEAD --[filename]
## 将工作区恢复成和暂存区一样
git checkout --[filename]
## 将暂存区和工作区恢复成最近一次提交
git reset --hard

## 删除最近几次的提交，并且将暂存区和工作区恢复成这次提交
git reset --head 545643 

#删除文件
##方式1
1. rm readme.txt
2. git rm readme.txt
## 方式2
1. git rm readme.txt

# stash存储临时任务
* git stash 将工作区的变更临时存储
* git stash list 查看临时存储列表
* git stash apply 申请最近一次临时存储 不从列表中移除
* git stash pop 申请最近一次临时存储，并且将其从列表中删除

# 备份仓库
麻烦，用到的时候看视频


#本地往github同步
看视频