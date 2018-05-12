---
title: 命令行
date: 2018-05-11 22:53:41
tags:
---
# 常用命令简介
- ls 罗列当前目录包含的文档  
- cat 查看文档内容  
- mv 重命名文档or移动文档  
- touch 创建文档  
 
在Git Bash中我们可以利用帮助文档查看命令解释,例如 ls --help
## ls  
```
$ ls --help
Usage: ls [OPTION]... [FILE]...
List information about the FILEs (the current directory by default).//列出文件信息(默认为当前目录)
```
```
ls -a, --all    do not ignore entries starting with   //表示会列出隐藏的文件
```
```
ls -l  use a long listing forma  //表示使用长列表格式
```
## cat
``` 
$ cat --help
Usage: cat [OPTION]... [FILE]...
Concatenate FILE(s) to standard output //将文档的内容输出
```
## mv
```
$ mv --help
Usage: mv [OPTION]... [-T] SOURCE DEST
 or: mv [OPTION]... SOURCE... DIRECTORY
 or: mv [OPTION]... -t DIRECTORY SOURCE...
Rename SOURCE to DEST, or move SOURCE(s) to DIRECTORY //重命名或者移动文件
```
## touch
```
$ touch --help
Usage: touch [OPTION]... FILE...
Update the access and modification times of each FILE to the current time.  //改变文件更新时间
A FILE argument that does not exist is created empty, unless -c or -h is supplied. //创建文件
```

## explainshell.com
  除了以上命令,我们还可以在 explainshell.com 进行命令功能的查询  
  
  例 echo '1' > 1.txt 创建一个内容为字符串1,名字为1.txt的文件
  ![explainshell](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/explainshell_1.png)