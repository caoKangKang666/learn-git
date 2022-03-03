## 本地操作

==git init==     初始化仓库

==git add .==    把全部文件提交暂存区

==git status==   查看状态

==git commit -m 'xxx'==    提交到本地仓库



每当修改文件，重新==git add .==重新提交



==git log== 查看提交过的版本

==git reset --hard HEAD^==  回退上一个版本  （回去之后，再通过git log查不到回退前的版本了，此方法返回不了）  可以用 ==git reflog==

==git reset --hard xxxxx==  通过版本号回退



## 远程库操作

上面全是在本地玩，操作完要提交github远程仓库，与别人共享。gitee也可以

（1）现在github/gitee上建立仓库

（2）把二者关联   ==git remote add origin https:xxxxxxxx==

   (3)  首次推送上来     ==git push -u origin master==

第一次会让输入用户名和密码



 (刚进公司需要问他们要仓库地址,克隆下拉)  ==git clone ...==

下载失败是因为仓库是私有，没权限。需要让公司分配权限。  离职的话，公司直接把权限收回就行了。



## 多人协作

写代码推送到远程库   git push origin master（简化：git push）   先pull一下，再push上传。因为别人可能在你之前提交了一些东西。

```javascript
git push -u origin master 命令将本地的master分支推送到origin主机

加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

git push，默认只推送当前分支

```

每天拉取最新的仓库     git pull   origin master （简化：git pull）



### 如果有冲突（改了同一个文件）

根据vscode提示，自己选择保留哪一部分代码。需要自己处理此冲突

处理完再重新 git add . ....

## 分支

分支用于新版本开发，老版本运行。  开发完合并到主分支。

==git branch -a==  查看所有分支

==git checkout -b aaa==  创建新分支aaa（影分身一版）

==git checkout  aaa==  切换到aaa

==git push origin aaa==  推送aaa分支到远程仓库的aaa分支

==git push origin master:aaa==  推送master到远程仓库的aaa分支





==git merge aaa== 需要站在主分支里使用该命令。 将其合并过来。 

==git branch -d xxx== 删除分支xxx

分支合并冲突：和上传冲突处理同理。



## 对于vue项目

默认创建了Git,不需要 git init。