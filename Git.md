# Git

![img](https://gitee.com/Fantasy2001/images/raw/master/Markdown/Git/git.jpg)



## Git配置

``` git
//设置用户名与邮箱，使用 --global 保存全局，
//想在某个特定项目中使用其他名字可以不是用 --glbal
git config --global user.name "username"
git config --global user.email test@qq.com

//查看已有的配置信息
git config --list

//使用当前目录作为 Git 仓库,初始化仓库
git init			//初始化仓库

//纳入版本控制，提交
git add 文件名			//添加至暂存区 git add . 新增修改的都加入缓存
git commit -m "注释"	//将暂存区内容添加到仓库中

//从现有 Git 仓库中拷贝项目
git clone  <repo> <directory>

/*
repo:Git仓库
directory：本地目录
*/
```

### 提交与修改

|    命令    |                  说明                  |
| :--------: | :------------------------------------: |
|  git add   |            添加文件到暂存区            |
| git status |  查看仓库当前的状态，显示有变更的文件  |
|  git diff  | 比较文件的不同，即暂存区和工作区的差异 |
| git commit |          提交暂存区到本地仓库          |
| git reset  |                回退版本                |
|   gir rm   |             删除工作区文件             |
|   git mv   |        移动或重命名工作区的文件        |

### 提交日志

|       命令        |                 说明                 |
| :---------------: | :----------------------------------: |
|      git log      |           查看历史提交记录           |
| git blame  <file> | 以列表形式查看指定文件的历史修改记录 |

### 远程操作

|    提交    |                    说明                    |
| :--------: | :----------------------------------------: |
| git remote |                远程仓库操作                |
| git fetch  |              从远程获取代码库              |
|  git pull  |             下载远程代码并合并             |
|  git push  | 上传远程代码并合并（git push -f 强推覆盖） |

### 分支管理

``` git
git branch		//查看所有分支及当前所在分支
git branch (branchname)		//创建分支，创建分支确认其他分支有提交
git branch -d (branchname)	//删除分支
git checkout (branchname)	//切换分支
git merge (branchname)		//合并分支
```

### Git远程仓库（Github）

``` git
//添加一个新的远程仓库
git remote add [shortname] [url]
//修改远程仓库地址
git remote set-url origin [url]

//生成密钥
ssh-keygen -t rsa -C "youremail@example.com"
//验证是否连接成功
ssh -T git@github.com
//查看当前配置有哪些远程仓库
git remote
//添加一个远程仓库命名为 origin
git remote add origin git@github.com:githubname/cangkuname.git
//查看所有远程仓库
git remote
//查看指定远程仓库地址
git remote -v
//删除
git remote rm 远程仓库名
//推送
git push -u origin master
```

### HTTPS 远程仓库

```git
//初始化本地仓库
git init
//查看仓库当前的状态，显示有变更的文件
git status
//提交所有文件至暂存区
git add .
//提交至本地仓库
git commit -m "注释"
//查看历史提交记录
git log
//查看所有的分支
git branch

//添加一个新的远程仓库
git remote add origin [url]
//修改之前先从远程仓库拉下来进行版本统一。main 是远程仓库的分支
git pull origin main
//上传到远程仓库的 main 分支
git push -u origin main

注意！！！
//电脑重启后需要删除远程仓库后再添加才可以 push or pull
//如果提交至非主分支，本地仓库必须建该分支
```

### git 回退版本

```Git
//查看版本编号
git log
//可以查看所有分支的所有操作记录（包括已经被删除的 commit 记录和 reset 的操作）
git reflog
//回退至目标版本，但目标版本之后提交都不存在了
git reset --hard 版本编号
//把暂存区中的文件拉回工作区
git checkout 文件名
//回退版本可能会出现比远程仓库版本低的情况，就需要进行强制推送
git push -f

//revert 与 reset 不同，该指令会生成一个新版本
git revert -n 版本号
//^^^这里可能会出现冲突，那么需要手动修改冲突的文件。而且要git add 文件名。
git commit -m "版本号"
//推送
git push
```

### pull & fetch

> 与git pull相比git fetch相当于是从远程获取最新版本到本地，但不会自动merge。如果需要有选择的合并git fetch是更好的选择。效果相同时git pull将更为快捷;

```Git
git fetch origin master		
//取回 origin 主机的 master 分支，取回后会返回一个FETCH_HEAD
git log -p FETCH_HEAD		//该版本的更新内容
git merge FETCH_HEAD 		//合并版本

git pull origin master		//就 master 分支更新取回，并与本地指定分支合并。
```



### git clone浅拷贝

> 该指令只clone最近的一次commit。项目里面的文件会被完整地被下载下来，但是历史不能完全保留。因此，如果不关系项目的历史，那就完全可以使用浅拷贝来完成clone。这样可以结局get clone慢的问题。

```Git
git clone --depth=1 https://(吧啦吧啦……)
```

