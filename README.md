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

## git rm -r --cached < filename > < dirname >
删除仓库中缓存跟踪管理的文件，用来删除仓库里的文件；指令执行后，再调用commit可执行更改  

## git rm -r -n --cached < filename > < dirname >
预览将要删除的文件，不实际执行删除操作

**注：上述两条指令可用来删除误多加入仓库的文件，如果出现下述提示：**  
**fatal:pathspec 'filename' did not match any files**  
**可能原因有：1、文件不存在；2、在gitignore文件指定了该文件；**  
**修改gitignore文件后，快速更正仓库文件步骤：**  
**1、git rm -r --cached ./  先删除仓库所有文件**  
**2、更新gitignore文件**  
**3、git add ./  再添加所有文件**  
**4、最后执行commit和push指令**  

## git archive < 分支名 > < --format=tar.gz > --output=DirAndFilename.格式  
将项目打包，不含git管理信息，如果不指定format，默认输出tar格式  

## git bundle create master.bundle < dir >
带log信息的打包，但是不能切换分支；  
使用git clone master.bundle < dir >来解包分支
