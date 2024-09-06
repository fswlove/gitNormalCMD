# gitNormalCMD
git常用指令记录

## 仓库一般初始化流程  
**create a new repository on the command line：**  
echo "# 5263" >> README.md  
git init  
git add README.md  
git commit -m "first commit"  
git branch -M main  
git remote add origin git@github.com:fswlove/5263.git  
git push -u origin main  
**push an existing repository from the command line:**  
git remote add origin git@github.com:fswlove/5263.git  
git branch -M main  
git push -u origin main  

## ssh-keygen -t rsa –C “youremail@example.com”  
Window电脑生成公钥指令  

## cat **.pub >> .ssh/authorized_keys  

将pub附加到keys后面，注意不是单个">"(不会附加)；  

## git branch -vv  
查看所有分支信息、远程分支、最近提交一次提交信息；

## git branch -r  

列出所有远程跟踪分支；

## git branch -a  

列出所有本地和远程跟踪分支；  

## git ls-remote --heads  

获取远程仓库分支信息（当前clone仓库）；  

## git ls-remote --tags <远程仓库 可选>  

获取远程仓库标签信息；  

## git commit -m 'xxx'
提交已经add并追踪的修改，-m表示直接添加后面的提交注释；
如果没有-m，会弹出文本编辑，编辑好提交记录后，关闭编辑器，开始提交；

## git commit -a
不用单独add，直接提交所有改变的内容；

## git commit --amend  

修补上次提交，并覆盖原来的提交信息；  

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

## git fetch  --->git status
查看本地分支与远程分支是否有差异，在fetch后用status才可以，单独status查看不到差异

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

## git tag  
## git tag -l "v1.8.5*"  
查看标签  

## git show < 标签名 >  
查看标签信息  

## git tag -a < 标签名 > < -m 'message' >  
附注标签  

## git tag < 标签名 >  
轻量标签  

## git tag -a < 标签名 > < 校验和或部分校验和 >  
后期打标签，根据校验和  

## git push -u < 服务器名，如origin > < 分支名 >  
将分支与远程服务器名关联并推送，后期直接git push推送即可  

## git push < 服务器名，如origin > < 标签名 >  
推送单个标签  

## git push < 服务器名，如origin > --tags  
推送多个标签，将不在远程仓库上的标签全推送过去  

## git tag -d < 标签名 >  
删除本地标签  

## git push < remote > :refs/tags/< tagname >  
删除远程仓库标签：将冒号前面的空值推送到远程标签名，从而高效地删除它。  

## git push < remote > --delete < tagname >  
删除远程仓库标签；  

## git checkout < tagname >  
检出标签，会使你的仓库处于“分离头指针（detached HEAD）”的状态——这个状态有些不好的副作用：  
在“分离头指针”状态下，如果你做了某些更改然后提交它们，标签不会发生变化， 但你的新提交将不属于任  
何分支，并且将无法访问；  

## git checkout -b < 新分支名 > < tagname >  
检出标签并创建新分支  
