# Git



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
|  git add   |             添加文件到仓库             |
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

|    提交    |        说明        |
| :--------: | :----------------: |
| git remote |    远程仓库操作    |
| git fetch  |  从远程获取代码库  |
|  git pull  | 下载远程代码并合并 |
|  git push  | 上传远程代码并合并 |

### 分支管理

``` git
git branch		//查看所有分支及当前所在分支
git branch (branchname)		//创建分支
git branch -d (branchname)	//删除分支
git checkout (branchname)	//切换分支
git merge (branchname)		//合并分支
```

### Git远程仓库（Github）

``` git
//添加一个新的远程仓库
git remote add [shortname] [url]

//生成密钥
ssh-keygen -t rsa -C "youremail@example.com"
//验证是否连接成功
ssh -T git@github.com
//查看当前配置有哪些远程仓库
git remote
//添加一个远程仓库命名为 origin
git remote add origin git@github.com:githubname/cangkuname.git
//删除
git remote rm 远程仓库名
//推送
git push -u origin master
```

