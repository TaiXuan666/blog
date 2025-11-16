# 一、 git的介绍

**git是一个分布式版本管理工具**

## 一.拉取代码

***第一种方式:***

```git
git init
```

```git
git remote add origin <远程仓库地址>
```

```bash
git pull origin main
```

***第二种方式:***

```git
git clone <远程仓库地址>
```



## 二.提交代码

***1.添加修改或删除的代码到暂存区***

```
git add <修改或删除文件>
git add . # 全部修改或删除的文件到暂存区
```

***2.将暂存区的内容提交至本地仓库并添加说明信息***

```
git commit -m "提交信息说明"
```

***3.推送内容到远程仓库*****

```
git push origin 本地分支名:远程分支名
```



## **三.全局设置**

***1.设置用户信息***

```git
git config --global user.name "AnEgg"
git config --global user.email "邮箱号"
```

***2.查看配置信息***

```
git config --list
```



## 四、git基本命令

***1.查看文件状态***

```git
git status 
```

***2.将文件的修改加入暂存区***

```
git add <修改文件或删除文件>
```

***3.将暂存区的文件取消暂存或者切换到指定版本***

```
git reset
git reset --hard 版本号 # 可以回溯到指定的版本
```

***4.将暂存区的文件修改提交到版本库***

```
git commit -m <说明信息>
# 当出现 fatal: cannot do a partial commit during a merge 可以使用-i参数解决只提交冲突文件
git commit -m <说明信息> -i 
```

***5.查看日志***

```
git log
```

***6.查看远程仓库***

```
git remote
git remote -v # 可以查看远程地址
```

***7.添加远程仓库***

```
git remote add <远程仓库别名> <远程仓库地址>
```

***8.从远程仓库克隆***

```
git clone <远程仓库地址>
```

***9.从远程仓库拉取***

```
git pull <远程仓库别名> <分支名>
```

***10.推送到远程仓库***

```
git push <远程仓库别名> <分支名>
# 当出现 fatal: refusing to merge unrelated histories,可以使用允许无关历史合并的方式解决
git push <远程仓库别名> <分支名> --allow-unrelated-histories
```

***11.查看远程分支和本地分支***

```
git branch -a # 列出所有分支
git branch # 查看所有本地分支
git branch -r # 查看所有远程分支
```

***12.创建本地分支***

```
git branch <分支名>
git checkout <分支名> # 可以切换分支
```

***13.合并分支到当前分支***

```
git merge <分支名>
```

***14.标签***

********说明：是用于标识提交历史中特定点的引用。它们常用于标记版本发布（如v1.0、v2.0等）。在Git中，标签可以是轻量的（lightweight）或附注的（annotated）。类似于某个时间段拍了一张照片,即使后面容貌发生了变化,还是可以通过照片查看当时的样子,标签是静态的但是分支是动态的。********

***1.列出已有的标签***

```
git tag
```

***2.创建标签***

```
git tag <标签名>
```

***3.将标签推送至远程仓库***

```
git push <远程仓库别名> <标签名>
```

***4.检出标签（新建一个分支来指向某个标签）***

```
git checkout -b <分支> <标签名>
```

