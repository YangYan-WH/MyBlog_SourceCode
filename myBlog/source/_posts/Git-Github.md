---
title: Git&Github
date: 2018-05-12 21:29:19
tags:
---
<!-- **准备:** Git Bash & Node.js & npm  
### 1. 安装Git Bash  
### 2. 安装并配置Node.js  
  打开Git Bash输入以下命令    
```
npm config set registry https://registry.npm.taobao.org/
npm config set loglevel http
npm config set progress false
```  
### 3. 安装并配置npm -->
## Git操作介绍  

*利用以下Git命令行前,已经将本地仓库与github仓库关联*

### 1. `git init`  
![pic](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/init.PNG)  
    1.1 进入相应的目录cd  
    1.2 对该目录进行仓库初始化,初始化后目录中出现.git的文件夹（*不要更改该文件夹*）  

### 2. `git add`  
![pic](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/add.PNG)  
    2.1 使用`git add+ '文件名' `,将该文件放入暂存区，或使用`git add .`将当前目录文件的变动放入暂存区  

### 3. `git commit`

* `git commit -v` 提交并显示文件的变动,按Esc后,输入:q!  
![pic](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/commitV.PNG)  

* `git commit -m '变动信息'` 提交变动及自定义的变动信息  

