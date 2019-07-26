svn 集中式 版本管理   用户操作同一个仓库

git 分布式版本管理       用户可以相互读取



git init 生成的.git文件夹  即仓库

git三大区

工作区(working directory)   包含.git文件夹的目录

仓库

​	暂存区(stage/index)  临时存储区域

​	版本库(repository)

​	

git管理的是文件 不是目录，如果文件夹里没文件，不会被管理



添加文件到版本库的步骤   重点

1。往工作区中创建（修改）文件

创建文件 git init

2.添加到暂存区：

​	git add  文件路径  	把文件夹下的所有添加修改转到暂存区

​	git add . 		添加所有修改到暂存区

3.从暂存区提交到版本库：git commit -m "备注"

最好备注写详细点



如果不写 -m  回车会进入vim编辑界面，

 按i进入编写。 可编写多条备注   。1.xxxx；2.xxxx;   每条备注用分号隔开

退出方法：

1.按esc退出编辑状态

2.同事按下shift+:   接着输入q(退出不保存) 或wq（退出并保存）

提交多个文件时，可用这种方法编写多条备注



辅助命令 git status 查看状态

三大状态

untracked 未被追踪（新文件、从未添加进版本库）

unstaged  未添加暂存区（有修改、以前添加到版本库）暂存区的文件内容被修改了（所以 git add）

uncommitted  	未提交到版本库（在暂存区、绿色）

.  当前目录 	..父级目录

### 建立本地仓库与远程仓库的连接

方式1：适用于先有本地仓库 ，后有远程仓库的情况

格式：git remote add 远程仓库名（名字自己起默认origin） 远程仓库地址

例如： git remote add origin git@github.com:Annair483/H5-zza.git

输入  git remote -v  查看是否连接成功

方法2:克隆（适用于先有远程库，后有本地仓库的情况）

格式：`git clone 远程仓库地址`

如果没有本地仓库，clone下来后 输入  cd 文件夹，效果为创建本地仓库 然后把clone下来的文件放进本地仓库里

如果有本地创库clone下来后要先推到本地仓库 git add .  然后 git commit -m""  在执行下面步骤



远程仓库名 origin



先 git push origin master 

如果git push origin master报错git pull...  before pushing again

因为远程跟本地不一样 要先拉取pull再push

pull的时候如果,提示fatal: refusing to merge unrelated histories 

解决方法：git pull origin master --allow-unrelated-histories



显示远到近的提交命令 git  log  从近到远显示



创建分支  转到分支  在分支修改后   确定无误后与master合并分支



HTTPS要输入用户名密码  ssh协议比较安全且传输速度比较快

要创建ssh key

email地址最好写自己注册的地址

github set  ssh钥匙设置  的title最好写英文  且能识别是哪台电脑

如果2个开发者push同一个文件 会发生冲突 会让你先pull  然后报错  (master|MERGING)  必须解决冲突保存好才能进行下一步 git add .   git commit -m ""    git push  推送不用每次都做  但本地的操作 每次都要 add .   commit



## 版本回退

默认  版本库和 暂存区回退

--hard 三大区都回退

master（专人管理，一般人不能随便改）

会设开发分支 dev，  后面进的在最新版本开发分支上开设自己的分支

遇到bug 创建分支 返回没写到bug的版本，改完后再合并



## 过滤



