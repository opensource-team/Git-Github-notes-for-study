一、Git
========


（一）概念
-------------------

### 1、Git是什么

Git是一个免费、开源的版本控制软件。

版本控制系统：是一种记录一个或若干个文件内容变化，以便将来查阅特定版本修订情况的系统。

系统具体功能：

（1）记录文件的所有历史变化

（2）随时可恢复到任何一个历史状态

（3）多人协作开发或修改

（4）错误修复

目的：通过Git管理GitHub托管项目代码

Git Bash：命令行模式

Git GUI：图形界面

### 2、Git与SVN对比

#### 2.1 SVN

SVN是集中式版本控制系统，版本库是集中放在中央服务器的，使用时需要首先从中央服务器得到最新版本下载到自己电脑上，使用后再把自己的成果推送到中央服务器。集中式版本控制系统必须联网才能工作。

SVN记录的是每一次版本变动的内容。

缺点：服务器单点故障、容错性差。

#### 2.2 Git

Git是分布式版本控制系统，没有中央服务器，每个人的电脑都是一个完整的版本库，工作时无需联网。【多人协作时，只需把各自的修改推送给对方，就可以互相看到对方的修改】

git将每个版本独立保存。




（二）基本原理
-------------

### 1、git工作区域

（1）工作区：就是你在电脑里能看到的目录。

（2）暂存区

（3）本地仓库

（4）远程仓库

![](https://github.com/Jericaran/Git-Github-notes-for-study/blob/master/images-folder/basicknowledge-5.png)



### 2、git的工作流程

（1）在工作目录中添加、修改文件

（2）将需要进行版本管理的文件放入暂存区域

（3）将暂存区域的文件提交到git仓库

![](https://github.com/Jericaran/Git-Github-notes-for-study/blob/master/images-folder/basicknowlegde-1.png)



### 3、Git管理的文件有三种状态：

已修改（modified）

已暂存（staged）

已提交（committed）



### 4、Git信息储存

 Git object组成：blob储存文件具体内容、tree（目录结构、文件权限、文件名）、commit上一个commit对应快照、作者、提交信息。

 HEAD、分支、普通的Tag可以简单的理解成是一个指针，指向对应commit的SHA1值

![](https://github.com/Jericaran/Git-Github-notes-for-study/blob/master/images-folder/basicknowledge-2.png)



更新⼯作区⽂件a.txt并add：运行 git add a.txt 将a.txt加⼊到索引区域，此时如上图所示， git在仓
库⾥⾯新建了⼀个blob object，储存了新的⽂件内容。并且更新了索引将a.txt指向了新建的blob
object。

![](https://github.com/Jericaran/Git-Github-notes-for-study/blob/master/images-folder/basicknowledge-3.png)  

![](https://github.com/Jericaran/Git-Github-notes-for-study/blob/master/images-folder/basicknowledge-4.png)



运⾏ git commit -m 'update'

\1. Git⾸先根据当前的索引⽣产⼀个tree object，充当新提交的⼀个快照。
\2. 创建⼀个新的commit object，将这次commit的信息储存起来，并且parent指向上⼀个commit，
组成⼀条链记录变更历史。
\3. 将master分⽀的指针移到新的commit结点。  





