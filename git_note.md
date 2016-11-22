#git NOTE
---

## 配置git
- git config --global user.name "狄睿鑫"
- git config --global user.email "diruixin@chmiot.net"
- git config --list

## 创建仓库
- cd 地址
- mkdir learnGit
- cd learnGit
- git init  

## 添加文件
- touch a.txt  
- git add a.txt  
- git commit -m "init repo"  
- git status 查看状态


## 操作文件
### 修改文件
- vim a.txt 修改文件内容
- git diff 查看文件差别
- git log 查看历史记录
- cat README.md  查看文件内容

### 版本回退
- git reset --hard HEAD^  返回至上一个版本
- git reset --hard HEAD^^ 返回至上两个版本
- git reset --hard HEAD~n 返回至前n个版本
- git reset --hard 版本号  返回至某个版本
- git reflog 获取版本号

### 删除和恢复文件
- rm a.txt  删除
- git checkout -- a.txt 恢复文件
- git rm --cached a.txt 只从暂存区删除，工作区保留

### 重命名文件
- mv a.txt b.txt

### 暂存区
- git stash

## 远程仓库
### 关联远程仓库
1. 注册Github账号
2. 创建SSH KEY。命令：ssh-keygen  -t rsa –C “youremail@example.com”
	- id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人
3. 登录github,打开” settings”中的SSH Keys页面，然后点击“Add SSH Key”,填上任意title，在Key文本框里黏贴id_rsa.pub文件的内容
4. 在Github上创建仓库后，复制仓库的http地址或SSH地址
5. 在本地仓库运行命令： git remote add origin 远程仓库地址
6. 把本地仓库的内容push至远程仓库，命令：git push -u origin master （首次加上-u参数）

### 从远程仓库下载文件
- git fetch
- git merge

### 再次push远程仓库
- git add
- git commit -m "注释"
- git push origin master

### 克隆远程仓库
1. 登录Github
2. 把需要克隆的仓库的HTTP地址复制下来
3. 在本地执行命令： git clone 远程仓库地址

## 分支
### 创建与合并分支
- git branch name 创建分支
- git checkout name 切换分支
- git checkout -b name 创建并切换分支
- git branch 查看分支
- git merge name 合并某分支到当前分支
- git branch -d name 删除分支
- git merge --no-ff -m "注释" name  禁用Fast forward模式 合并分支



----------

## 工作区和暂存区
- 工作区：就是你在电脑上看到的目录，比如目录下testgit里的文件(.git隐藏目录版本库除外)。或者以后需要再新建的目录文件等等都属于工作区范畴。

- 版本库(Repository)：工作区有一个隐藏目录.git,这个不属于工作区，这是版本库。其中版本库里面存了很多东西，其中最重要的就是stage(暂存区)，还有Git为我们自动创建了第一个分支master,以及指向master的一个指针HEAD。

　　我们前面说过使用Git提交文件到版本库有两步：

- 第一步：是使用 git add 把文件添加进去，实际上就是把文件添加到暂存区。

- 第二步：使用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支上。	
