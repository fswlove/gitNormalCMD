# gitNormalCMD
git常用指令记录

## git branch -vv  
查看所有分支信息、远程分支、最近提交一次提交信息；

## git commit -m 'xxx'
提交已经add并追踪的修改，-m表示直接添加后面的提交注释；
如果没有-m，会弹出文本编辑，编辑好提交记录后，关闭编辑器，开始提交；

## git commit -a
不同单独add，直接提交所有改变的内容；

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
