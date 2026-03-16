# git_study
学习git的使用

# 工作区  --->暂存区--->本地仓库--->远程仓库

## 工作区  --->暂存区
git add .  添加所有文件到暂存区  （. 表示所有文件）。也可以指定文件名。git add 文件名  添加指定文件到暂存区
## 暂存区  --->工作区
git restore --staged .  恢复所有文件到工作区  （. 表示所有文件）。也可以指定文件名。git restore --staged 文件名  恢复指定文件到工作区


## 暂存区  --->本地仓库
git commit -m "提交信息"  提交到本地仓库
## 本地仓库  --->暂存区
git reset HEAD~1  回退到上一次提交的状态，将提交的内容放回暂存区 （需要重新 git add 和 git commit）

git reset --soft HEAD~1  回退到上一次提交的状态，将提交的内容放回暂存区（--soft 表示保留工作区和暂存区的修改）

git reset --hard HEAD~1  回退到上一次提交的状态，丢弃工作区和暂存区的修改


## 本地仓库  --->远程仓库
git push origin master  推送到远程仓库
## 远程仓库  --->本地仓库
## 场景1：提交错了代码到远程仓库，需要回退到之前的版本并强制推送
git log  查看提交历史，找到需要回退的commit id

git reset --hard <commit_id>  回退到指定的commit id（--hard 表示丢弃工作区和暂存区的修改）

git push origin master --force  强制推送到远程仓库

## 场景2：回退到指定版本
git log  查看提交历史，找到需要回退的commit id

git reset --hard <commit_id>  回退到指定的commit id

git reset --mixed <commit_id>  回退到指定的commit id，将修改放回工作区

git reset --soft <commit_id>  回退到指定的commit id，将修改放回暂存区

## 场景3：撤销已经推送的提交
git revert <commit_id>  撤销指定的提交，生成一个新的提交

git push origin master  推送到远程仓库

# 创建分支 （在本地仓库）
git branch 分支名  创建一个分支，分支名是分支的名称
git branch softdev  创建一个分支，分支名是 softdev





