### 1.git和github简介
git是一个本地用于代码管理、代码更新、代码回退、轨迹标识综合一体的工具，基于C语言编程开发，这个软件在程序员中应用非常广泛。使用这个软件以后，能够对代码的更新和管理有很大的帮助。

git现在支持主流的三大操作系统，Liunx、Windows、Mac OS X。但是安装后的管理环境均通过基于Liunx的命令行进行相关的代码管理操作，一般命令行均需要以git开头。如下

```
# 添加git到当前库
git add readme.txt
```

github是基于git的一个社区，可以把git想象成是一个本地版的代码管理工具，而github则是一个云端的代码管理工具，通过ssh密钥的结合，则可以根据git本地库对github进行云端同步代码管理。

#### 1.1 git的应用环境

当出现一个场景，如果我的代码存储在本地的电脑中，我安装了git本地客户端，那实际上仍然是不稳妥的，现在我有两类方式来保存我的代码文件备份，并实时记录我的每一次对代码的操作，那么现在我有两个办法实现：

**基于办公环境**

- 通过git与本地一台24小时持续开机的服务器进行通信，并且均配置好git客户端，然后每一次代码的更新，都同步备份在24小时的服务器一份。这是工作环境配置的最佳选择，原因是工作环境的代码一般由于企业秘密性，不能公开。那么sourcetree则是一个最佳选择。原因很简单，sourcetree的操作，都是中文，一般除了首次配置以外，不需要命令行。

**基于自用环境**

- 假如我的日常代码学习，希望能够有一个和外部程序员交流的机会，同时希望我的代码公开以后，如果有人访问，那么可以指导我进行更新和修改。那最佳的选择，就是类似于github和码云作为互联网备份服务器。这样我的代码是公开的，我也可以进行相关的非工作用代码公开和日常管理工作。而且，自用环境下的代码管理，可以让你更随意的修改和学习掌握git和github的工作思路。

本次，这里重点讲解github的使用和git的相关配置。作为一个初级程序员，有必要学习和掌握github的使用方法的重要原因是，这里是一个全世界最大的同性恋交友社区（手动狗头）。能够学习到别人的非常多的优秀代码，假如，你想不断更新自己的知识体系的话。

++网上有句话说的是，如果不会github的使用，甚至不使用这个平台。那么自己是一个假程序员。++

#### 1.2 git的相关环境搭建

##### git的下载
 经过测试，下载速度比较慢，可以根据系统选择对应的版本，这里以windows版本举例：

下载地址：https://git-scm.com/downloads

安装方法：https://www.cnblogs.com/wj-1314/p/7993819.html

#### 1.3 github的注册工作

目前，github不需要翻墙即可使用。注册相关的流程如下：

https://www.cnblogs.com/cxq0017/p/9636083.html

**相关准备工作即通过以上方法实现完成。**


### 2. git环境的配置

安装好git以后，桌面上会出现相关的图标。双击运行以后，在运行界面单击右键可以进行主题、字体等一些基础设置。然后后进入到很熟悉的git环境界面。

#### 2.1 在你的非C盘下新建一个git目录

新建这个目录的目标是为了放置你后期所有的本地代码，所有的代码都会从git文件夹中进行上传同步到github中去。


新建好以后，那么就通过Linux命令定位到当前文件夹目录下，以下展示Linux命令行方式对文件夹的新建删除：

```bash
# 展示当前路径下的文件列表
$ ll
total 37
-rw-r--r-- 1 dell 197121 29251 May 20 08:34 Adaboost算法代码学习.md
-rwxr-xr-x 1 dell 197121  3910 Oct 19  2018 K均值聚类代码案例.py*
-rw-r--r-- 1 dell 197121    93 May 30 14:44 readme.txt

dell@dell-PC MINGW64 /d/git/learngit (master)
# 新建一个machineleanrn的文件夹
$ mkdir machineleanrn

dell@dell-PC MINGW64 /d/git/learngit (master)
# 查看是否新建成功
$ ll
total 37
-rw-r--r-- 1 dell 197121 29251 May 20 08:34 Adaboost算法代码学习.md
-rwxr-xr-x 1 dell 197121  3910 Oct 19  2018 K均值聚类代码案例.py*
drwxr-xr-x 1 dell 197121     0 May 30 15:50 machineleanrn/
-rw-r--r-- 1 dell 197121    93 May 30 14:44 readme.txt

dell@dell-PC MINGW64 /d/git/learngit (master)
# 访问该文件夹
$ cd machineleanrn/

dell@dell-PC MINGW64 /d/git/learngit/machineleanrn (master)
# 列表展示新建文件夹下是否有文件
$ ls

dell@dell-PC MINGW64 /d/git/learngit/machineleanrn (master)
# 展示当前文件夹的绝对路径
$ pwd
/d/git/learngit/machineleanrn

dell@dell-PC MINGW64 /d/git/learngit/machineleanrn (master)
# 返回上一层文件夹
$ cd ..

dell@dell-PC MINGW64 /d/git/learngit (master)

# 删除原来新建的文件夹，这个命令慎重使用，注意路径地址
$ rm -rf machineleanrn

dell@dell-PC MINGW64 /d/git/learngit (master)

# 查看是否删除成功
$ ll
total 37
-rw-r--r-- 1 dell 197121 29251 May 20 08:34 Adaboost算法代码学习.md
-rwxr-xr-x 1 dell 197121  3910 Oct 19  2018 K均值聚类代码案例.py*
-rw-r--r-- 1 dell 197121    93 May 30 14:44 readme.txt

```

配置好主体文件夹后，那么就需要配置版本库，最好按照你自己的工作或者学习分类进行不同库的提前配置，这样方便后期管理，比如你正在学习的是Linux bash shell和python两个语言，那么就最好建议新建两个库进行不同的代码管理。

那么，什么是版本库呢？

#### 2.2 git的版本库的配置

什么是版本库呢？版本库又名仓库，英文名repository，你可以简单理解成一个总代码目录，这个目录里面的所有文件都可以被Git管理起来，每个文件的修改、删除，Git都能跟踪，以便任何时刻都可以追踪历史，或者在将来某个时刻可以“还原”。

这里说明一点，如果你要想你的代码被版本库进行管理，那么，最重要的首要工作，就是需要将文件添加到库。

同时，这个库的名称，为了方便管理，最好在新建的时候就配置好，同时，在github新建库的时候，最好同本地的库的名称完全一致。这样能够做到一一对应。当然，不一一对应新建库，也是可以的。

##### 2.2.1 新建一个文件夹作为git版本库的准备文件夹

```bash
# 新建一个Linux_shell的文件夹作为版本库
dell@dell-PC MINGW64 /d/git
$ mkdir Linux_shell

dell@dell-PC MINGW64 /d/git
$ ll
total 4
drwxr-xr-x 1 dell 197121 0 May 30 16:27 Linux_shell/
drwxr-xr-x 1 dell 197121 0 May 30 15:55 learngit/
```

##### 2.2.2 git init 命令让普通文件夹变成版本库

要想让普通的文件夹变成一个版本库，肯定是需要配置一些命令，让这个文件夹和其他的文件夹看起来不一样。具体操作如下使版本库生效：

```bash
# 访问到计划建设为版本库的文件夹目录下，然后运行git init 命令
dell@dell-PC MINGW64 /d/git
$ cd Linux_shell/

dell@dell-PC MINGW64 /d/git/Linux_shell
$ pwd
/d/git/Linux_shell

dell@dell-PC MINGW64 /d/git/Linux_shell
$ git init
Initialized empty Git repository in D:/Git/Linux_shell/.git/
```
瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），细心的读者可以发现当前目录下多了一个.git的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。

如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用
```bash
ls -ah
```
命令就可以看见。

##### 2.2.3 git add 命令让普通文件添加到版本库

```bash
dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ touch readme.txt

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ ls
readme.txt

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ vim readme.txt

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git add readme.txt
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git add readme.txt

```

这里特别说明一下，任何文件，就算在windows下，你拷贝到了Linux_shell目录下，版本库不会自动识别这里有一个新文件进入库目录并且自动同步到云端。因此，我们需要添加操作，做了这个添加操作以后，就能够让git识别——哦，这里有一个新的文件添加进来了。

##### 2.2.4 git commit -m 命令为新增的文件做补充说明

当任何一次代码文件的新增，代码文件的内容增删改，那么都需要告诉服务器端，你大概做了什么骚操作，这样方便后期查询修改的内容梗要。

```bash
dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git commit -m "新增说明文件"
[master (root-commit) b3b695c] 新增说明文件
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
```

因此，好的习惯是，当你操作了一次添加文件或者改动文件的时候，那么你就需要添加一个补充说明，告诉自己和别人，自己干了什么改动。

这时候，我们在git本端的工作假设就已经做完了。下一步，我们想将这个写好的说明文件 readme.txt 同步到github云端。



### 3.github的相关配置

假设你已经注册好了github账号，这时候，你已经进入到github的首页了。首页看起来非常的晦涩难懂，因为英文不好啊。


#### 3.1 GitHub 基本概念

上面认识了 GitHub 的基本面貌之后，你需要了解一些 GitHub 的基本概念，这些概念是你经常会接触并遇到的。

##### Repository

仓库的意思，即你的项目，你想在 GitHub 上开源一个项目，那就必须要新建一个 Repository ，如果你开源的项目多了，你就拥有了多个 Repositories 。

##### Issue

问题的意思，举个例子，就是你开源了一个项目，别人发现你的项目中有bug，或者哪些地方做的不够好，他就可以给你提个 Issue ，即问题，提的问题多了，也就是 Issues ，然后你看到了这些问题就可以去逐个修复，修复ok了就可以一个个的 Close 掉。

#####  Star

这个好理解，就是给项目点赞，但是在 GitHub 上的点赞远比微博、知乎点赞难的多，如果你有一个项目获得100个star都算很不容易了！

#####  Fork

这个不好翻译，如果实在要翻译我把他翻译成分叉，什么意思呢？你开源了一个项目，别人想在你这个项目的基础上做些改进，然后应用到自己的项目中，这个时候他就可以 Fork 你的项目，这个时候他的 GitHub 主页上就多了一个项目，只不过这个项目是基于你的项目基础（本质上是在原有项目的基础上新建了一个分支，分支的概念后面会在讲解Git的时候说到），他就可以随心所欲的去改进，但是丝毫不会影响原有项目的代码与结构。

#####  Pull Request

发起请求，这个其实是基于 Fork 的，还是上面那个例子，如果别人在你基础上做了改进，后来觉得改进的很不错，应该要把这些改进让更多的人收益，于是就想把自己的改进合并到原有项目里，这个时候他就可以发起一个 Pull Request（简称PR） ，原有项目创建人就可以收到这个请求，这个时候他会仔细review你的代码，并且测试觉得OK了，就会接受你的PR，这个时候你做的改进原有项目就会拥有了。

#####  Watch

这个也好理解就是观察，如果你 Watch 了某个项目，那么以后只要这个项目有任何更新，你都会第一时间收到关于这个项目的通知提醒。

#####  Gist

有些时候你没有项目可以开源，只是单纯的想分享一些代码片段，那这个时候 Gist 就派上用场了！

#### 3.2 如何配置github，ssh key的功用

既然要确保本地git和github能够通信，那么肯定需要一个通信协议方式来连接双方。github可以基于ssh网络协议来进行通信。那么，建立好通信桥梁，是我们能够同步git代码到云端的必备条件。

这里需要准备两个东西

- 你注册git的用户名
- 你注册git使用的邮箱

使用这个这两个东西，就可以在本地git操作生成两个key了，一个是公钥，一个私钥。公钥的作用就是用来git和github进行通信的工具，同时，为了确保每次提交的内容让机器识别确实是你本人提交的。那么就需要公钥信息来核对是否是本人提交的内容。

##### 3.2.1 如何生成公钥和私钥和配置公钥

**第1步**：创建SSH Key。在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key：

```bash
$ ssh-keygen -t rsa -C "youremail@example.com"
$ ssh-add id_rsa.pub
```

执行用户确认的相关命令：
```bash
 $ git config --global user.email "you@example.com"
 $ git config --global user.name "Your Name"
```

你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，由于这个Key也不是用于军事目的，所以也无需设置密码。

如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。


**第2步**：登陆GitHub，右上角打开“settings--SSH and GPG key--SSH key --New SSH key”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容，然后点击保存即可。

id_rsa.pub可以通过notepad++或者其他文本编辑器打开复制。

当然，GitHub允许你添加多个Key。假定你有若干电脑，你一会儿在公司提交，一会儿在家里提交，只要把每台电脑的Key都添加到GitHub，就可以在每台电脑上往GitHub推送了。

最后友情提示，在GitHub上免费托管的Git仓库，任何人都可以看到喔（但只有你自己才能改）。所以，不要把敏感信息放进去。


##### 3.2.2 在github新建一个远程库用于和本地库同步

进入到你自己的github首页
```bash
https://github.com/yourname
```

然后点击右上角的加号--New repository,新建名称最好保持与本地库刚刚新建的库名称一致。
然后在新建成功后的页面有如下几段代码：

```bash
# 或从命令行推送现有存储库
…or push an existing repository from the command line
git remote add origin https://github.com/zhang0838/Linux_shell.git
git push -u origin master
```

这就是我们需要在本地执行的两段代码。那么我们复制到本地git环境进行执行。

```bash
dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git remote add origin https://github.com/zhang0838/Linux_shell.git

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 259 bytes | 259.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/zhang0838/Linux_shell.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

执行完毕后，你就会发现，本地的这个库的所有文件，都同步到了github中。特别说明一点，github的文档默认格式是支持markdown的，markdown的语法熟悉了非常的方便，非常好用。

**首次执行的时候，会提示要求输入用户名和密码。**

##### 3.2.3 假设我现在对git本地文件内容，添加了一些补充说明如何二次同步呢

首先，应该去查看更新的内容的差异点在哪儿

```bash
dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ vim readme.txt

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git diff readme.txt
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory
diff --git a/readme.txt b/readme.txt
index ddc2a5f..264fd7e 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1 +1,2 @@
 这是一个测试文件
+这是文件的更新内容部分

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
```

然后，我们需要查看当前该文件的git状态

```bash
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
这时候，提示我们没有任何文件进行更新操作。那么说明我们当前修改的内容还没有同步到本地库，更不要说更新到远程github库了。

```bash
# 这里添加的时候会报警，先不要管，继续重复上次的代码
dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git add readme.txt
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory

dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git add readme.txt

```

然后，我们需要对我们添加到库的更新文件进行补充说明

```bash
dell@dell-PC MINGW64 /d/git/Linux_shell (master)
$ git commit -m "更新说明文件的具体内容"
[master 14c7273] 更新说明文件的具体内容
 1 file changed, 1 insertion(+)
```

最后，我们需要将我们修改的内容提交到云端同步。

```bash
$ git push origin master
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 340 bytes | 340.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/zhang0838/Linux_shell.git
   b3b695c..14c7273  master -> master
```

会同步提示你，文件同步内容成功，这时候，我们再次去github查看的时候，那么readme.txt文件已经同步更新了最新的内容。

最后查看一下当前git状态

```bash
$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```
提示已经上传成功,没有任何文件需要commit。


至于，文件回退等更多操作的学习，请参见附录，附录写的非常的好，对初学者非常的友好。



##### 故障1解决方案

当对当前文件push的时候，输入以下代码的时候报错：

```bash
git push -u origin master
To https://github.com/zhang0838/Git_learn.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/zhang0838/Git_learn.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

```

解决方案如下：

```bash
$ git pull --rebase origin master
warning: no common commits
remote: Enumerating objects: 19, done.
remote: Counting objects: 100% (19/19), done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 19 (delta 2), reused 18 (delta 1), pack-reused 0
Unpacking objects: 100% (19/19), done.
From https://github.com/zhang0838/Git_learn
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> origin/master
First, rewinding head to replay your work on top of it...
Applying: 添加小白适合阅读的git和github使用教程
```
将云端的文档和本地库文档全部合并。





###### 附录：本文重点参考如下
```python
# 写得非常好
https://www.liaoxuefeng.com/wiki/896043488029600
```