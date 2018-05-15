---
title: HTTP
date: 2018-05-13 22:13:09
tags:
---
## HTTP简介  
  Berners-Lee 李爵士发明第一个服务器，第一个浏览器，第一个网页。
    - URI分为URL和URN，一般使用URL作为网址
    - HTTP协议用于两个电脑之间传输内容
  - HTML主要用来做页面跳转

### URL
  ![pics](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/HTTP.PNG)

### Server + Client + HTTP
  ![pics](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/request.png)
  - 浏览器负责发起请求
  - 服务器在80端口接受请求
  - 服务器负责返回内容（响应）
  - 浏览器负责下载响应内容

### 请求与响应
```
*curl -s -v -H "XXX: xxx" -- "https://www.baidu.com"  
//请求内容为
GET / HTTP/1.1
Host: www.baidu.com
User-Agent: curl/7.54.0
Accept: */*
XXX: xxx

//响应内容为
HTTP/1.1 200 OK
Accept-Ranges: bytes
Cache-Control: private, no-cache, no-store, proxy-revalidate, no-transform
Connection: Keep-Alive
Content-Length: 2443
Content-Type: text/html
Date: Tue, 10 Oct 2017 09:14:05 GMT
Etag: "5886041d-98b"
Last-Modified: Mon, 23 Jan 2017 13:24:45 GMT
Pragma: no-cache
Server: bfe/1.0.8.18
Set-Cookie: BDORZ=27315; max-age=86400; domain=.baidu.com; path=/

<!DOCTYPE html>
<!--STATUS OK--><html> <head> 后面太长，省略了……
```
```
*curl -X POST -s -v -H "Frank: xxx" -- "https://www.baidu.com"
//请求的内容为
POST / HTTP/1.1
Host: www.baidu.com
User-Agent: curl/7.54.0
Accept: */*
Frank: xxx

//响应的内容为
HTTP/1.1 302 Found
Connection: Keep-Alive
Content-Length: 17931
Content-Type: text/html
Date: Tue, 10 Oct 2017 09:19:47 GMT
Etag: "54d9749e-460b"
Server: bfe/1.0.8.18

<html>
<head>
<meta http-equiv="content-type" content="text/html;charset=utf-8"> 后面太长，省略了……
```

  **请求的格式为**  
  1 动词 路径 协议/版本  
  2 Key1: value1  
  2 Key2: value2  
  2 Key3: value3  
  2 Content-Type: application/x-www-form-urlencoded  
  2 Host: www.baidu.com  
  2 User-Agent: curl/7.54.0  
  3   
  4 要上传的数据  

  **响应的格式为**  
  1 协议/版本号 状态码 状态解释  
  2 Key1: value1  
  2 Key2: value2  
  2 Content-Length: 17931  
  2 Content-Type: text/html  
  3  
  4 要下载的内容  


*注意事项*  
* 请求对多包含四部分,最少包含三部分(第四部分为空)
* 第三部分永远是回车(`\n`),用来分割
* 动词有GET POST PUT PATCH DELETE HEAD OPTIONS 等
* 路径包括[查询参数],但不包括[锚点]
* 如果没有写路径,默认路径为/
* 第2部分中的Content-Type标注了第4部分的格式

#### 用chrome发送请求  
1. 打开network  
2. 地址栏输入网址
3. 在network查看request,点击[view source]
4. 可以看到请求的前三部分
5. 请求的第四部分,那么在FormData 或 Payload里面可以看到  

#### 用chrome查看响应
1. 打开network
2. 输入网址
3. 选中第一个响应
4. 查看Response Header.点击[view source]
5. 可以查看响应的前两部分
6. 查看Response 或者 Preview,可以响应的第4部分

![pics](https://raw.githubusercontent.com/YangYan-WH/MyBlog_SourceCode/master/pics/myBlog_pics/Http-network.png)