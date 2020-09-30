# GitCommond
记录使用的Git 命令
[Git-scm 文献](https://www.git-scm.com/)

## 一、添加、修改、删除以及查看本地git的用户名和邮箱
1、添加 用户名，邮箱
```
$ git config --global user.name "your name"
$ git config --global user.email "yao@emial.com"
```
2、修改
  
  2.1、 覆盖方式-修改
   ```
   $ git config --global user.name "your name"
   $ git config --global user.email "yao@emial.com"
   ```
   2.2、 替换方式-修改
   ```
   $git config --global --replace-all user.name "your name" （注意：‘--replace-all’这里是一个词组，分开失效）
   $git config --global --replace-all user.email "your@email.com"
   ```
3、删除
```
$git config --global --unset user.name "your name"
$git config --global --unset user.email "your@email.com"
```
4、查看
  
  4.1、 查看所有的
  ```
    $ git config --list
  ```
  4.2、 查看指定信息
  ```
  $ git config user.name (查看‘姓名’)
  $ git config user.email（查看‘邮箱’）
  
  ```
## 二、已经上传了git的项目，添加 忽略文件（.gitignore）,并删除远端库已经提交的 忽律文件
1、在根目录下创建一个文件 .gitignore, 并在文件中 加入需要忽略的文件/路径  
>   gitignore 语法：

    a>、//：注释  
    b>、fileName.suffix：忽略所有文件名为：fileName.suffix的文件  
    c>、*.html: 忽略所有生成Html文件  
    d>、！foo.html: 手动维护该 Html文件 不被忽略  
    i>、\*.[oa] :忽略所有 .o 和.a 文件  
    f>、abd ：忽略abd文件和abd目录  
    g>、abd/ ：只忽略abd目录，不忽略文件

    h>、abd  
       ！abd/  ：只忽略文件，不忽略abd目录

    g>、/abd ：只忽略当前路径下的abd文件和目录，子目录的abd不在忽略文件范围

2、使用命令 git rm -r –cached directory 来删除缓存
```
//移除 .idea目录的缓存
 git rm -r –cached .idea  
 
```
3、使用 命令 git commit -m "commit description" 和 git push <远程主机名> <本地分支名>  <远程分支名>

> **通过上面三部操作，就能实现标题 所要解决的问题**。


## 三 git push 相关操作

> git push的一般形式为：git push <远程主机名> <本地分支名>  <远程分支名>

1. 将本地的 master分支，推送到远程机origin 上对应的master分支  
   `git push origin master : refs/for/master`
2.  省略<远端分支名>:表示将本地分支推送到与之存在追踪关系的远程分支（通常两个名字相同）；如果远端不存在该分支，则会创建该新分支  
    `git push origin master`
3. 省略<本地分支名>：则表示删除指定的远端分支；因为这等同于推送一个空的本地分支到远程分支，等同于：git
   push origin --delete master  
   `git push origin : refs/rof/master`
4.  省略 <本地分支名>,<远端分支名>：则表示如果当前本地分支和远端分支存在追踪关系，则为本地分支和远端分支都可省略；将当前分支推送到origin主机的对应分支上  
    `git push origin`
5.  省略 <远程主机名>
    <本地分支名><远程分支名>：则表示如果当前分支只有一个远端分支，那么主机名都可以省略；  
    git push \[这叫做simple方式\]

6. 如果当前分支与多个主机存在追踪关系，则可以使用 -u
   参数指定一个默认主机，这样后面就可以不加任何参数使用git push

`git push -u origin master`

7. 当遇到这种情况就是不管是否存在对应的远程分支，将本地的所有分支都推送到远程主机，这时需要
   -all 选项

  `git push --all origin`

8. 强行将本地代码覆盖到 远端分支  
   `git push --force origin ` git push的时候需要本地先git
   pull更新到跟服务器版本一致，如果本地版本库比远程服务器上的低，那么一般会提示你git
   pull更新，如果一定要提交，那么可以使用这个命令。
9. git push 的时候不会推送分支，如果一定要推送标签的话那么可以使用这个命令  
   `git push origin --tags`



`查看远端 存在分支 git branch -r 或者 git branch -a`


