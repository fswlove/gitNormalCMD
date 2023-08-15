# gitNormalCMD
git常用指令记录

## git branch -vv  
查看所有分支信息、远程分支、最近提交一次提交信息；

## git commit -m 'xxx'
提交已经add并追踪的修改，-m表示直接添加后面的提交注释；
如果没有-m，会弹出文本编辑，编辑好提交记录后，关闭编辑器，开始提交；

## git commit -a
不用单独add，直接提交所有改变的内容；

## git branch < 分支名 >  
创建分支

## git checkout < 分支名 >  
切换到分支

## git remote add < 远程仓库 > < url >  
为远程仓库增加链接

## git remote remove < 远程仓库 >
删除远程仓库链接

## git remote show < 远程仓库 >
查看远程仓库信息

## git checkout < 分支名 > <文件名> < 文件夹/** >
从指定分支，导入合并指定的文件名、文件夹内容

## git clone --bare my_project my_project.git
从my_project 中复制除一个裸仓库my_project.git，用来搭建git服务器仓库

##  scp -r my_project.git user@git.example.com:/srv/git
将my_project.git 复制到服务器上

## git clone user@git.example.com:/srv/git/my_project.git
从服务器上克隆一个仓库

## git gc
垃圾清理回收，压缩
