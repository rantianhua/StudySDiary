# Git问题集 #
# 1.error:src refspec master does not match any #
## 问题产生 ##
- 用Git Shell新建一个仓库，将代码复制到该仓库下后初始化(git init),然后添加所有的文件到本地仓库(git add -A).
- 添加远程仓库(git remote add origin ...)
- 提交(git push -u origin master),然后报错。
## 产生原因 ##
原因是仓库目录中没有文件，就是我在操作过程中忘记把代码提交到本地仓库了。
## 解决办法 ##
用git commit ..将代码提交到本地仓库再进行push.

# 2. Updates were rejected because the tip of your current branch is behind#
## 问题产生 ##
- 我现在coding上新建一个项目（类似在github上新建一个项目），创建时带有README.md文件。
- 在本地创建一个仓库，添加要上传的文件，同时也创建了一个README.md文件。
- push报错
## 产生原因 ##
在服务器的仓库已经创建了README.md，在本地又创建了这个文件，在push之前因为没有把这两个相同文件合并，所以push的时候产生了冲突。
## 解决办法 ##
在push之前，先把服务器上的仓库pull下来并合并(git pull origin master，相当于更新本地仓库，然后再push。

# 1/22/2015 9:14:22 PM  #