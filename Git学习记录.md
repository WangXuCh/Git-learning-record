# Git学习记录

- 安装git

  ```
  sudo apt-get install git
  ```

- 初始化用户名、邮箱，保存用户名和密码，查看配置信息

  ```
  git config --global user.name wl
  git config --global user.email 614653847@qq.com
  git config --global credential.helper store
  git config --global --list
  ```

- 新建一个版本仓库

  ```
  # 新建
  git init <path>
  # 查看是否生成了.git文件
  ls -a or ls -al
  # 查看.git文件
  cd .git
  ls -altr
  ```

- 工作区、暂存区、本地仓库

  ```
  .git  .git/index  .git/objects
  未跟踪 Untrack     还未被git管理的文件
  未修改 Unmodified  被管理但内容没变化
  已修改 Modified    已经被修改的文件，还没添加到暂存区
  已暂存 Staged      已经修改并添加到暂存区的文件
  ```

  ![image-20240410114852935](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410114852935.png)

- 添加、提交文件

  ```
  git status 查看仓库状态
  git add    添加到暂存区
  git rm --cached <file>  取消暂存
  git commit 提交
  git commit -m "第一次提交"  提交
  git commit -am 相当于add和commit
  
  git add *.txt  将所有的txt文件添加到暂存区
  git add .      将当前目录所有文件添加到暂存区
  
  git log            查看提交记录
  git log --oneline  查看提交记录
  ```

![image-20240410130637578](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410130637578.png)

![image-20240410130934732](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410130934732.png)

- 回退到之前的版本

  ```
  git reset + --[soft or hard or mixed]
  1. git reset --soft  <版本id>  回退到某一个版本并保留工作区和暂存区的所有修改内容
  2. git reset --hard  <版本id>  回退到某一个版本并丢弃工作区和暂存区的所有修改内容 
  3. git reset --mixed <版本id>  回退到某一个版本并保留工作区修改内容，丢弃暂存区修改内容
  
  ls 查看工作区的内容
  git ls-files 查看暂存区的内容
  
  误操作
  git reflog 查看操作历史，找到误操作前的版本号
  然后使用git reset --hard <版本号>
  ```

  ![image-20240410132224802](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410132224802.png)

![image-20240410134912965](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410134912965.png)

![image-20240410135342269](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410135342269.png)

![image-20240410135521135](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410135521135.png)

- 查看差异

  ```
  git diff  默认比较工作区和暂存区的差异内容
  git diff HEAD  比较暂存区和版本库之间的差异  git diff --cached
  git diff <id> <id> 比较两个版本之间的差异内容
  git diff HEAD <id> 比较两个版本之间的差异内容
  git diff HEAD~ HEAD 比较当前版本与上一个版本之间的差异内容
  git diff HEAD^ HEAD 比较当前版本与上一个版本之间的差异内容
  git diff HEAD~n HEAD 比较当前版本与上n个版本之间的差异内容
  git diff <id> <id> <file_name> 比较两个版本之间<file_name>差异内容
  ```

- 从版本库中删除文件

  ```
  rm <file_name>      删除工作区的文件
  git add <file_name> 将暂存区中的文件删除
  
  or
  
  git rm <file_name> 同时删除工作区和暂存区的文件
  git rm --cached <file_name> 删除暂存区的文件
  
  最后记得提交 commit
  ```

- gitignore

  ```
  echo <file> .gitignore
  echo *.log .gitignore
  ```

- PULL AND PUSH

  ![image-20240410173802057](https://github.com/WangXuCh/Git-learning-record/blob/main/img/image-20240410173802057.png)

- 关联本地仓库和远程仓库

  ```
  git remote add origin git@github.com:WangXuCh/first-repo.git
  git branch -M main
  git push -u origin main
  git push -u origin main:main
  
  git pull
  git pull origin main
  
  fetch
  ```

  
































