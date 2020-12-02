# GitHub不完全使用指南

## 创建仓库

首先假定：

- 用户名usrname
- 仓库名tmp

### 全新的仓库

创建仓库步骤如下：

1. 首先在https://GitHub.com/new new一个repository，my_first_repository，会给出仓库地址https://GitHub.com/usrname/my_first_repository.git，记住这个地址，第7步会用到。

2. 本地创建项目文件夹，例如my_first_repository，并初始化git

   ```shell
   mkdir my_first_repository
   cd my_first_repository
   git init
   ```

3. 创建自己的项目文件，随意编辑内容，例如创建并编辑或复制一个py文件

   ```shell
   touch my_first_project.py
   ```

4. 将修改添加到本地缓存区

   ```shell
   git add my_first_project.py
   ```

5. 将缓存区内容提交到本地仓库

   ```shell
   git commit -m "first commit"
   ```

6. 创建主branch，main，即过去的master（BLM）

   参数`-M`表示move/rename a branch, even if target exists

   ```shell
   git branch -M main
   ```

7. 将本地仓库与远程仓库关联。最后一个参数url，就是第一步创建并需要记住的url。origin其实就是这个url的别名，所以可以随意取。

   ```shell
   git remote add origin https://GitHub.com/usrname/my_first_repository.git
   ```

   关于remote更多用法，可以参考[这里](https://zhuanlan.zhihu.com/p/144702363?from_voters_page=true)。

8. 提交本地仓库到远程仓库

   ```shell
   git push -u origin main
   ```

### 从其他远程仓库

完成第一步以后，打开以下链接：

https://GitHub.com/usrname/my_first_repository/import

*所以这个和fork有啥区别？*

## 编辑更新

### 从远程仓库克隆到本地

1. 克隆repository

   ```shell
   git clone https://GitHub.com/usrname/my_first_repository.git
   ```

2. 切换到下载好的本地仓库（其实就是个文件夹）

   ```shell
   cd my_first_repository
   ```

3. 创建一个新的branch，例如branch_name_2

   ```shell
   git branch branch_name_2
   ```

4. 将本地新建的branch，push到远程仓库，push完以后，在GitHub上应当能看到新的branch

   ```shell
   git push --set-upstream origin branch_name_2
   ```

### 编辑提交更改

1. 假定我们刚刚编辑/删除了my_first_project.py，并新建了一个文件，位于new_folder/index.html，提交更改之前，首先检查我们是否处于正确的branch

   ```shell
   git checkout pepsi
   ```

2. 将更改保存在本地缓冲区

   ```shell
   git add my_first_project.py
   git add new_folder/index.html
   ```

3. 将本地缓冲区更改提交到本地仓库

   ```shell
   git commit -m "my-message(e.g. delete my_*.py & create new_folder/index.html)"
   ```

4. 将本地仓库更改提交到GitHub远程仓库

   ```shell
   git push origin main
   ```

### 合并pull request

1. 检查并切换到主branch

   ```shell
   git checkout main
   ```

2. 合并branch

   ```shell
   git merge branch_name_2
   ```

3. 将本地更改提交到远程仓库

   ```shell
   git push
   ```

4. 删除本地branch

   ```shell
   git branch -d branch_name_2
   ```

5. 在GitHub上删除branch，branch_name_2。

## 同步本地仓库

将本地仓库更新到远程仓库有两种方式，`git fetch`和`git pull`，按照Git手册（[中文](https://training.github.com/downloads/zh_CN/github-git-cheat-sheet/)，[英文](https://training.github.com/downloads/github-git-cheat-sheet/)）的说法，

> 使用来自 GitHub 的对应远端分支的所有新提交更新你当前的本地工作分支。`git pull` 是 `git fetch` 和 `git merge` 的结合

> Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. `git pull` is a combination of `git fetch` and `git merge`



## 相关资源

Git book:https://git-scm.com/doc

GitHub lab:https://lab.github.com/











