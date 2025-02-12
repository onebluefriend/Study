# CDSN 

[Git基本使用（很详细）-CSDN博客](https://blog.csdn.net/qq_45796592/article/details/128953729?ops_request_misc=%7B%22request%5Fid%22%3A%2260c942b2cdca6ac00897d863c19769ca%22%2C%22scm%22%3A%2220140713.130102334.pc%5Fall.%22%7D&request_id=60c942b2cdca6ac00897d863c19769ca&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~hot_rank-1-128953729-null-null.142^v101^pc_search_result_base2&utm_term=git&spm=1018.2226.3001.4187)

---

[Typora基础设置、MarkDown语法_markdown异或符号-CSDN博客](https://blog.csdn.net/zzh45828/article/details/105883083)

[Typora常用命令和必备设置_typora命令-CSDN博客](https://blog.csdn.net/Zhao_Water/article/details/112724826)

[Typora基本使用&Markdown基本语法（从入门到精通，精炼且详细）-CSDN博客](https://blog.csdn.net/weixin_51350847/article/details/136557560)

------------------------------------------------------------------------------------------------------------------------------

[【Linux】Linux常用命令60条（含完整命令语句）_linux必学的60个命令-CSDN博客](https://blog.csdn.net/wzk4869/article/details/132855372)

[Linux必学的60个命令(整理)-CSDN博客](https://blog.csdn.net/cnkernel/article/details/4573623?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-4-4573623-blog-132855372.235^v43^pc_blog_bottom_relevance_base3&spm=1001.2101.3001.4242.3&utm_relevant_index=7)

---

[Vim编辑器完全指南：命令模式、编辑与末行模式操作详解-CSDN博客](https://blog.csdn.net/blood_Z/article/details/125064927?ops_request_misc=%7B%22request%5Fid%22%3A%221b001bce9f47df7fa5c5f99c685db044%22%2C%22scm%22%3A%2220140713.130102334.pc%5Fall.%22%7D&request_id=1b001bce9f47df7fa5c5f99c685db044&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~hot_rank-1-125064927-null-null.142^v101^pc_search_result_base2&utm_term=vim命令&spm=1018.2226.3001.4187)

[Vim的最全命令总结（Linux）_vim命令-CSDN博客](https://blog.csdn.net/2301_79695159/article/details/140323426?ops_request_misc=%7B%22request%5Fid%22%3A%2242ce8c68bb0b1bdefd4f53fee859ab04%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=42ce8c68bb0b1bdefd4f53fee859ab04&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-140323426-null-null.142^v101^pc_search_result_base2&utm_term=vim命令&spm=1018.2226.3001.4187)

---

# 在Windows上面使用Linux的命令--使用git20250212

```bash
#切换分支	switch 是 Git 2.23 版本引入的专门用于切换分支的命令，语法更加简洁明了
git checkout <目标分支名>
git switch <目标分支名>
#新建并切换到新分支
git checkout -b <新分支名>
git switch -c <新分支名>

#将新分支推送到远程仓库
git push -u <远程仓库别名> <新分支名>
#-u 选项（--set-upstream 的简写）：用于建立本地分支和远程分支的关联，之后再进行推送时，就可以直接使用 git push 而无需再指定远程仓库和分支名。
#<远程仓库别名>：通常默认是 origin，它是克隆远程仓库时 Git 自动为远程仓库设置的别名。
#<新分支名>：你在本地创建的新分支的名称。


#当你想切换到远程分支对应的本地跟踪分支时，需要指定完整的远程分支名，一般格式为 origin/<远程分支名>。例如，切换到远程 origin 仓库的 develop 分支对应的本地跟踪分支：
git checkout origin/develop
git switch origin/develop

#在本地查看远程分支列表
git branch -r
#删除本地分支
git branch -d <分支名>
git branch -D <分支名>	#强制删除

#使用 git push 命令删除远程分支
git push <远程仓库别名> --delete <远程分支名>
	<远程仓库别名>：通常默认是 origin，它是克隆远程仓库时 Git 自动为远程仓库设置的别名。
	<远程分支名>：要删除的远程仓库分支的
	#例如:下面两者等价
	git push origin --delete old-feature名称。
	git push origin :old-feature	#这里冒号前面为空，表示将一个空分支推送到 old-feature 分支，从而达到删除该远程分支的目的。
#删除远程分支后，本地仓库可能仍然保留着对该远程分支的跟踪信息。你可以使用以下命令清理本地的远程分支引用：
git remote prune origin
#删除远程分支后，你可以使用 git branch -r 命令查看远程分支列表，确认指定的分支是否已被成功删除：
git branch -r


拉取远程仓库main分支
git pull origin main
将本地仓库推送到远程仓库main分支

```

- 将本地仓库推送到远程仓库的 `main` 分支:

  - 查看当前本地仓库关联的远程仓库信息:

    ```bash
    git remote -v
    ```

  - 如果输出结果中没有显示远程仓库的地址，或者地址不是你想要关联的远程仓库地址，你可以使用以下命令来添加或修改关联：

    ```bash
    # 添加远程仓库关联
    git remote add origin <远程仓库地址>
    # 修改已有的远程仓库关联地址
    git remote set-url origin <远程仓库地址>
    ```

- ```bash
  git pull origin master #注意最后这是本地分支的名字
  ```



注意,在Linux中是区分大小写命令的,而git不区分.

- 命令后面加上`--help`可查看该命令的帮助信息, 如果是在命令前面加上`man`,该命令则比前者提供更加详细的信息(git中不能使用).

- 清屏命令`clear`,Window 中是`cls`.

- 查看配置

  ```bash
  git config -l
  
  #查看系统配置,
  git config --system --list
  #查看当前用户(global)配置
  git config --global --list
  ```

  

- 设置用户名与邮箱（用户标识，必要）

  ```bash
  git config --global user.name "ARonggit"  #名称
  git config --global user.email 1822076750@qq.com   #邮箱
  ```

- 在当前目录新建一个Git代码库

  ```bash
  git init
  ```

- 克隆远程仓库

  ```bash
  git clone <远程仓库地址> [本地目录名]
  git clone https://github.com/onebluefriend/first1.git
  
  #克隆远程仓库main分支里的东西到本地电脑:加上 "-b 分支名"
  git clone -b main https://github.com/onebluefriend/first1.git
  ```

- 关联远程仓库，需要使用 `git remote add` 命令将本地仓库与远程仓库关联起来

  ```bash 
  git remote add origin https://github.com/onebluefriend/first1.git
  ```


- 拉取远程仓库

  ```bash
  git pull <远程仓库名> <远程分支名>:<本地分支名>
  #如果省略 :<本地分支名>，则默认合并到当前所在的本地分支	
  git pull origin master
  
  #拉取 origin 远程仓库的 dev 分支并合并到本地的 feature 分支：
  git pull origin dev:feature
  
  #git pull命令是git fetch和git merge两个命令的组合,git fetch 从远程仓库下载最新的提交记录,git merge 将下载的提交合并到本地分支
  #如果想分步操作，可以先执行 `git fetch`，查看远程分支的更新情况，再手动执行 `git merge` 进行合并。
  # 从远程仓库下载最新提交记录
  git fetch origin main
  # 将下载的提交合并到本地的 main 分支
  git merge origin/main
  ```

- 提交远程仓库

  ```bash
  git push <远程仓库名> <本地分支名>:<远程分支名>
  #如果本地分支和远程分支名称相同，可简写为 git push <远程仓库名> <本地分支名>
  git pull origin master
  
  #假设你在本地有一个名为 feature-new 的分支，想要将其推送到远程仓库的 dev 分支，可使用如下命令：
  git push origin feature-new:dev
  ```

  

- 添加指定文件到暂存区

  ```bash
  git add <文件名>
  
  #添加所有修改（包括新增、修改和删除的文件）到暂存区
  git add .
  
  #添加当前目录下所有跟踪过的文件的修改到暂存区
  git add -u
  ```

- **基本提交命令**

  ```bash
  git commit -m "提交说明"
  #这里的`-m` 选项用于指定本次提交的说明信息，这个说明应该清晰地描述本次提交所做的更改，方便后续查看和理解提交历史。
  
  跳过暂存区直接提交，直接将工作目录中所有跟踪过的文件的修改提交到本地仓库
  git commit -a -m "提交说明"
  #这里的 `-a` 选项表示将所有跟踪过的文件的修改自动添加到暂存区并提交。
  ```

- 补充或修改最近一次提交

  ```bash
  #补充遗漏的修改到最近一次提交** 先把遗漏的修改添加到暂存区，然后使用以下命令将这些修改合并到最近一次提交中,执行该命令后，会弹出一个文本编辑器，你可以修改提交说明，保存退出后，最近一次提交就会被更新。
  git commit --amend
  
  #只修改最近一次提交的说明
  git commit --amend -m "新的提交说明"
  ```

- 查看提交历史 `git log` 

  ```bash
  git log
  #简洁的格式查看提交历史
  git log --oneline
  ```

  

- ```bash
  #为注释
  
  #查看指定文件状态
  git status [filename]
  
  #查看所有文件状态
  git status
  
  git add .                  #添加所有文件到暂存区
  git commit -m "消息内容"    #提交暂存区中的内容到本地仓库 -m 提交信息
  
  # 列出所有本地分支
  git branch
  
  # 列出所有远程分支
  git branch -r
  
  # 新建一个分支，但依然停留在当前分支
  git branch [branch-name]
  
  # 新建一个分支，并切换到该分支
  git checkout -b [branch]
  
  # 合并指定分支到当前分支
  $ git merge [branch]
  
  # 删除分支
  git branch -d [branch-name]
  
  # 删除远程分支
  git push origin --delete [branch-name]
  git branch -dr [remote/branch]
  
  *.txt        #忽略所有 .txt结尾的文件,这样的话上传就不会被选中
  ！!lib.txt     #但lib.txt除外
  /temp        #仅忽略项目根目录下的TODO文件,不包括其它目录
  tempbuild/       #忽略build/目录下的所有文件
  doc/*.txt    #会忽略 doc/notes.txt 但不包括 doc/server/arch.txt
  ```

- 设置本机绑定SSH公钥，实现免密码登录！（免密码登录，这一步挺重要的，码云是远程仓库，我们是平时工作在本地仓库！)

  ```bash
  ssh-keygen -t rsa -C "your_email@example.com"
  #ssh-keygen：这是一个在 Linux、macOS 等系统上用于生成 SSH 密钥对的工具命令，在 Windows 系统的 Git Bash 中也可以使用。
  #-t rsa：-t 选项用于指定要生成的密钥类型，rsa 表示使用 RSA 算法来生成密钥对。RSA 是一种广泛使用的非对称加密算法，常用于 SSH 认证。
  #-C "your_email@example.com"：-C 选项用于给生成的密钥添加一个注释信息，通常使用你的邮箱地址作为注释。这个注释信息主要是方便你识别不同的密钥，在查看公钥文件内容时会显示该注释。
  
  ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCuh+UMT3QX0qQUIlyEm7O9mQPsY436NDJRVW3hGbkv2Y+8pjtbhnsbSgWxQ3yiuHgaTh6EdpZpmCQPfuhG7NDPVGMBp5dbvi4HNf+gTAIBUE7HH5fqnwdfgMOYXWGrl/nuEMenUioMHItEsfr4UhiSvXAM41y+7nm8rCQ5cIbwJwfCPv37L5vs7HGeiTCADURbAbVvq44aZ4ljaMam3vQMr0IncMnjz06sR5WbHdmkAuC2D6NG5g1m+TM7H02WfDqKKX2ytgNe5qMYreDpb32miIPw58U3jSdd5w77+k8g3vRPxO1w3OC1Miwr55KPscpV6NXm2JlyTlCUCRyQHPVx7tctgRVs/93Q/LF6gK8FKVL8KDl7Wt5/nEgIEiv2+9bgL8/bQjOLOfWAHdAlxlR8ElCRfocXVT2yZJguz+dAaDpS0DZ8mc/WoCEOhzrjjN2UyP3cndBET4aBsFZf9nBCaN/a7XqxWny9+NsZCbfblApuqboFSINzlO1zQL+o8i0= 18220@ARong
  
  ```

- 错误

  ```bash
  本地仓库可能没有及时获取到远程仓库最新的分支信息，你可以使用 git fetch 命令来更新。
  
  #切换分支
  git checkout <目标分支名>
  #在本地仓库中，使用 git checkout -b 命令创建一个新分支并同时切换到该分支。
  git checkout -b new-feature
  #使用 git pull 命令从远程仓库拉取 main 分支的内容并合并到当前的 new-feature 分支。
  git pull origin main
  #当你在执行 git pull 或者 git merge 操作时遇到 fatal: refusing to merge unrelated histories 错误，这是因为 Git 默认情况下不允许合并两个没有共同历史的分支或仓库。
  #假设你要将远程仓库的 main 分支内容拉取到本地新分支并合并，可执行以下命令：
  git pull --allow-unrelated-histories origin main
  
  #查看本地仓库中存在哪些分支，可使用 git branch 命令
  git branch
  
  #想查看远程仓库中的分支情况，可以使用 git branch -r 命令，其中 -r 是 --remotes 的简写。
  git branch -r
  
  #使用 git branch -a 命令可以同时查看本地和远程仓库的分支信息，-a 是 --all 的简写。
  
  #查看已合并到当前分支的分支
  git branch --merged
  
  #当你执行 git pull origin main 出现 fatal: refusing to merge unrelated histories 错误提示时，这是因为 Git 默认情况下不允许合并两个没有共同历史的分支或仓库
  git pull --allow-unrelated-histories origin main
  #执行该命令后，Git 会尝试合并远程 main 分支和本地当前分支的内容。不过，由于两者历史无关联，可能会产生大量的合并冲突。
  ```

  

# vim

注意:光标所在的位置,其实是后面那个词的位置,因为光标没办法移动到最后.即我们所说的8,代码中是7一个道理,因为是从0开始算起.一般是小后大前

- 进入命令模式 `:`, 按下`esc`取消, 命令模式下才能进行退出等命令操作.
  - **`i` 在光标位置前面插入,如果此时按下`esc`则光标会往前移动,  `I` 在最前面插入**
  - **`a` 在光标位置后面插入(即光标会往后面条一格),如果此时按下`esc`则光标会往前移动,  `A` 在最前面插入**
  - `o` 在光标下新建一行插入, `O` 新建上一行插入
  - `:q` 不保存退出, **`q!` 不保存且强制退出**.
  - `:w` 保存, `w!` 强制保存, `w filename` 另存到filename.
  - **`:wq` 保存并退出.**
  - `x` 删除光标所在位置的单词.(注意,一个词的位置是在光标的后面,也就是说,`ab/c`这个光标代表的是c,而不是b)
  - `ctrl+v+方向键+y` 复制光标所选内容(前一个), `yw`复制整个单词
  - `yy`复制光标所在一整行,`nyy` 复制n行,`y+Enter` 复制光标所在一整行和下一行.
  - `p` 粘贴(光标所在位置的后面(后一个),如果是整行的则是在下面新建一行), `P` 粘贴到光标前面
  - `dd` 删除所在行,之后如果使用`p` 则是剪切.
  - `u` 撤销最近修改,`U` 撤销当前行所有编辑.
  - `ctrl+r` 恢复.
  - `:n` 跳到第n行
- 在vim编辑器中临时设置行号 `set nu`,  关闭行号`set nonu`.
  - 永久显示行号,修改vim配置文件vimrc，如果没有此文件可以创建一个``vim ~/.vimrc`

