# GitCommond
记录使用的Git 命令

## 一、添加、修改、删除以及查看本地git的用户名和邮箱
1、添加 用户名，邮箱
```
$ git config --global user.name "your name"
$ git config --global user.email "yao@emial.com"
```
2、修改
  2.1、覆盖方式-修改
   ```
   $ git config --global user.name "your name"
   $ git config --global user.email "yao@emial.com"
   ```
   2.2、替换方式-修改
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
  4.1、查看所有的
  ```
    $ git config --list
  ```
  4.2、查看指定信息
  ```
  $ git config user.name (查看‘姓名’)
  $ git config user.email（查看‘邮箱’）
  
  ```
