
# 常用操作：

## 分支基本操作(branch、checkout)：
- git branch dev  
创建分支
- git checkout dev  
切换分支
- git checkout -b dev  
在当前分支基础上建立一个新分支(dev)，并切换到新分支
- git branch -vv  
查看当前详细分支信息（可看到当前分支与对应的远程追踪分支）
- git branch -d dev  
删除本地分支(当然，删除之前必须切换到其他分支)
- git push origin --delete dev2  
git push origin :dev(推送空分支相当于删除)  
删除远程仓库分支
- git branch -a  
查看本地与远程仓库分支
- git branch -r  
查看远程仓库分支


## 远程仓库基本操作(remote)
- git remote -vv  
git remote -v  
查看当前远程仓库信息
- git remote add origin xxx.git
添加远程仓库
- git branch --set-upstream-to=origin/remote_branch  your_branch  
将本地分支与远程仓库分支关联起来


## 推送操作(push)
- git push <远程主机名> <本地分支名>:<远程分支名>
- git push  
将当前分支推送到默认主机(默认为origin)的对应分支上(已经关联)
- git push -u origin master  
将本地的master分支推送到origin主机，同时指定origin为默认主机，后面就可以不加任何参数。-u指定默认主机
- git push origin master  
将本地的master分支推送到origin主机的master分支。如果master不存在，则会被新建。 
- git push --all origin  
将所有本地分支都推送到origin主机


## 管理修改(主要针对当前工作没完成想修改以前的内容)
- git checkout -- file  
丢弃工作区修改
回退到暂存区（如果暂存区不为空）或版本库最新版本（暂存区为空，即commit之后没有add操作）
![3个场景](图片地址 ''图片title'')
- Git还提供了一个stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作  
git stash  
将当前工作区保存，先修复bug
 


# 注意事项：
- git中一个本地分支只能与远程主机的一个分支建立联系。
- git branch -vv 查看本地分支与远程分支的跟踪情况
- .git文件夹中的config文件中可看到远程分支的情况
- git clone的原理说明  
https://blog.csdn.net/Hungryof/article/details/86521835  
git clone默认会把远程仓库整个给clone下来，但只会在本地默认创建一个远程对应的HEAD(默认master)分支，其他分支是隐藏的。  
如果远程还有其他的分支，此时用git branch -a查看所有分支。  
此时若想让其他分支出现，可以  
git checkout -t origin/dev = git checkout -b dev origin/dev = git checkout dev 
上面的3个操作时一致的
参考来源:https://www.jianshu.com/p/0fe715a7fbb3

# git详细介绍

- 介绍git网站  
阮一峰：http://www.ruanyifeng.com/blog/2014/06/git_remote.html

- git结合实际，比较实用  
廖雪峰：https://www.liaoxuefeng.com/wiki/896043488029600

- git API网站  
易百教程：https://www.yiibai.com/git

