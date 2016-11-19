##http://brew.sh  (brew install git)
##https://git.io/brew-analytics(Further documentation)
##svn git的区别
```
svn:集中式
git:分布式
```
##git的基本配置及命令
```
查看git版本:
    git --version

配置git:
    git config --global user.name yuezhirui0802
    git config --global user.email yuezhirui0802@163.com

查看配置信息:
    git config --list

清屏:
    clear

改变目录
    cd(change directory)
使用gitbash切换盘符需要加cd cmd中直接盘符

初始化git仓库(表示当前文件夹下归git所管理)
    git init
创建目录
    mkdir gittest

删除目录
    rm -rf aa

在目录中创建文件
    touch 文件名.文件类型
查看文件目录
    ls
查看文件夹(包括隐藏文件)
    ls -al
打印文件目录
    pwd
命令行的编辑器
    vi 文件名
用i进入编辑,退出用esc然后:wq(保存退出):q(不用保存直接退出):q!(强制退出)
查看文件内容
    cat 文件名
向文件中写入内容,如果文件不存在则创建,如果多次写入则会覆盖原来的内容
    echo hello world > index.txt(将hello world 写入index.txt中)
    echo hello world >> index.txt(向index.txt文件中追加内容)
查看状态
    git status
    红色表示没有加入暂存区
加入暂存区
    git add index.txt (单一提交)
    git add . 或者-A (单一提交)
    绿色表示加入暂存区
将文件提交到历史区中
    git commit
显示提交到历史区的详细信息(查看git 的提交日志)
从工作区提交到历史区(一步到位),不支持首次提交
    git commit -a -m 'ok';

每次提交会产生一个版本号,存着对应的版本号,查找对应的版本号(显示当前的版本号)
    git log

代码比较
1)工作区和暂存区的比较
    git diff
2)工作区和历史区的比较
    git diff master
3)暂存区和历史区的比较
    git diff --cached
回到add.之前的操作
git reset HEAD 文件名   
git rm --cached 文件名
git checkout 文件名       :从暂存区回到工作区
git reset --hard 版本号   :回到过去
git reflog  :回到现在(查看之前的所有所有操作)
git reset --hard HEAD^   :回到head的上一个版本
git reset --hard HEAD^^   :回到head的上一个的上一个版本
链接远程仓库
git remote add 名字 地址
查看远程仓库地址
git remote -v
删掉远程仓库地址
git remote rm 名字
推送到远程仓库

git push -u origin master
git push origin master -u
     如果增加-u下次再提交到时候,就可以直接使用git push或gitpull
git push  origin master
如果线上有东西,需要先git pull,然后再git push

创建忽略文件
创建一个文件.gitignore 里面写上不想要的文件
下面文件git直接忽略
.idea
node-module
bower-components
修改了本地的文件和修改了线上的文件,改的是同一个文件
--为了防止pull时拉取线上的代码,覆盖掉本地内容,所以先要将本地的代码进行提交
--在拉取文件,拉去线上代码发现和本地冲突.此时不能自动合并,需要手动合并
修复冲突需要修改文件中=====<<<<<>>>>>>将此类符号删掉保留想要的内容即可

gh-pages(如果把代码提交到这个分支上,github会给这个地址可以直接访问这个项目)

git push origin gh-pages
创建分支:
git branch gh-pages
切换分支
git checkout gh-pages
删除分支
git branch -D gh-pages
查看分支
git branch
创建并切换这个分支
git checkout -b gh-pages
将线下的分支推送到线上
git push origin gh-pages
合并分支(在master合并gh-pages)
git merg gh-pages
一般情况下,我们会将开发的内容简历一个开发分支将代码提交到开发分支上,善变的时候合并master分支,并删除我们开发上的分支
```

##三个区
- 工作区 真实写代码的地方(开发项目时的目录)
- 暂存区/缓存区 把内容暂时保留一下(过度作用),将大妈暂存后,一起提交初一个版本,维护版本库
- 历史区/版本库 放到版本库中的东西永远不回丢失
>github 远程仓库(最终展示的内容是某一个版本)


## 作业提交
- 老师 -》 组长 -》 组员
## 老师
- 建立一个作业仓库
- 克隆线上代码到本地
可以将线上的代码直接复制到本地，并且会默认下载master分支，给我们一个origin默认的远程地址
## 组长负责fork老师的仓库