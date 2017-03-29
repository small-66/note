cd d:   进入d盘
cd ...   进入文件   
ls

## 下载
git clone 地址

## 查看状态   
git status

## 本地 提交 到 暂存区
git add 1.html
git add .    一次提交多个文件

## 暂存区 提交到 版本区
get commit -m "注释"

## 本地 提交 到版本区
git commit -a -m "注释"

## 查看提交是否成功
git log


## 对比
1 查看本地与暂存区域的区别
git diff
1 查看暂存区与版本区的区别
git diff --cached
3 查看本地与版本的区别
git diff master

## 撤销
1. 从 暂存区  撤销到 工作区（本地） 
git reset HEAD 1.html ----不改变代码
2. 工作区代码还原成 暂存区 或 版本区
git checkout -- 1.html  ---- 改变代码
3. 把最后一次提交的版本撤销  和本次提交到版本区的内容 合并为一个版本 
git commit -m "222" --amend 

## 删除
1. git rm 1.html 在暂存区删除（前提：本地要手动删除） 
2. git rm -f 1.html 删除工作区以及暂存区的文件
3. git rm --cached 1.html 只删除暂存区 不删除本地(同 git reset HEAD 1.html)

## 恢复
git reflog 快速查看历史版本记录，方便使用
1. 回滚指定文件 git checkout 文件名
2. 回滚指定版本文件  git checkout 版本号（前5位数） 文件名
3. 回滚整个版本所有的文件 git reset --hard 版本号

## 同步到远程仓库（github）
git push origin master


## 添加开发者
1. 先进入github项目
2. 点击 + new collaborator
3. 加开发伙伴
4. 等待伙伴确认（邮箱）
5. 有权限的伙伴，克隆地址
6. 进行开发

## 解决冲突
1. git fetch 现将远程仓库的代码拉取下拉
2. git diff master origin/master 查看版本库与远程的差异
3. git merge origin/master 版本库与远程的代码进行合并
4. 手动修改文件
5. git push origin master

## git config --global credential.helper store 
以后提交文件的时候输入的用户名和密码会被记录下来

## 如果没有别人的权限修改项目
1. fork下别人的项目
2. 自己的远程仓库会多一个项目
3. git clone
4. 该修改就修改，该push就push
5. 创建一个新的 new pull request
6. 等待别人回复

## 收到
1. 先查看别人修改了什么
2. 如果合适就合并： 点击：merge pull request按钮进行合并

## 分之
默认为master分支
1. 查看 git branch  当前分支会有*号
2. 查看没有合并的分支  git branch --no merged
3. 创建  git branch 分支名
4. 切换 git checkout 分支名
5. 快速创建并切换  git checkout -b 分支名
6. 合并     git merge 分支名
7. 删除合并过的     git -d 分支名
8. 删除没有合并过的   git branch -D 分支名
9. 







