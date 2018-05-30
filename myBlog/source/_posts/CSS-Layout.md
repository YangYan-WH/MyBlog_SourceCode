---
title: CSS Layout
date: 2018-05-29 21:51:35
tags:
---
# CSS布局 

## 左右布局 
1. **利用浮动** 
    <font size="2">html</font>
    ```
    <div class="main clearfix">  <!-- 父元素需要清除浮动 -->
        <div class="left">left</div>
        <div class="right">right</div>
    </div>
    ```
    <font size="2">css</font>
    ```
    .clearfix::after{
        content:'';
        display:block;
        clear:both;
    }
    .left{
        float:left;
        width:50%;
        background-color:red;
    }
    .right{
        float:right;
        width:50%;
        background-color:green;
    }
    ```
2. **利用绝对定位**  
    <font size="2">html</font>
    ```
    <div class="main">
        <div class="left">left</div>
        <div class="right">right</div>
    </div>
    ```
    <font size="2">css</font>
    ```
    .main{
        position:relative;
    }
    .left{
        position:absolute;
        width:50%;
        left:0;
        background-color:red;
    }
    .right{
        position:absolute;
        width:50%;
        right:0;
        background-color:green;
    }
    ```
3. **利用行内块元素**  
    <font size="2">html</font>  
    ```
    <div class="main">
        <div class="left">left</div>
        <div class="right">right</div>
    </div>
    ```
    <font size="2">css</font>
    ```
    *{
        padding: 0;
        margin: 0;
    }
    .left{
        display:inline-block;  <!-- 中间会有间隙,我们用负margin清除间隙-->
        width:50%;
        margin-right: -6px;
        background-color:red;
        vertical-align: top;
    }
    .right{
        display:inline-block;
        width:50%;
        margin-right: -6px;
        background-color:green;
        vertical-align: top;
    }
    ```

## 左中右布局  
1. **利用浮动**  
    <font size="2">html</font>
    ```
    <div class="main clearfix">     <!-- 父元素需要清除浮动 -->
        <div class="left">left</div>
        <div class="middle">middle</div>
        <div class="right">right</div>
    </div>
    ```
    <font size="2">css</font>
    ```
    .clearfix::after{
        content:'';
        display:block;
        clear:both;
    }
    .left{
        float:left;
        width:33%;
        background-color:red;
    }
    .middle{
        float:left;
        width:33%;
        background-color:blue;
    }
    .right{
        float:left;
        width:33%;
        background-color:green;
    }
    ```
2. **利用绝对定位**  
    <font size="2">html</font>
    ```
    <div class="main">
        <div class="left">left</div>
        <div class="middle">middle</div>
        <div class="right">right</div>
    </div>
    ```
    <font size="2">css</font>
    ```
    .main{
        position:relative;
    }
    .left{
        position:absolute;
        top:0;
        left:0;
        width:33%;
        background-color:red;
    }
    .middle{
        position:absolute;
        top:0;
        left:33%;
        width:34%;
        background-color:blue;
    }
    .right{
        position:absolute;
        top:0;
        right:0;
        width:33%;
        background-color:green;
    }
    ```
3. **利用行内块元素**  
    <font size="2">html</font>
    ```
    <div class="main">
        <div class="left">left</div>
        <div class="middle">middle</div>
        <div class="right">right</div>
    </div>
    ```
    <font size="2">css</font>
    ```
    //行内块元素元素间会有间隙
    .left{
        display:inline-block;
        width:33%;
        background-color:red;
    }
    .middle{
        display:inline-block;
        width:33%;
        background-color:blue;
    }
    .right{
        display:inline-block;
        width:33%;
        background-color:green;
    }
    ```
  

## 水平居中  
1. **行内元素(inline)水平居中**  
    <font size="2">html</font>
    ```
    <div class="main">
        <span class="center">居中</span>
    </div>
    ```
    <font size="2">css</font>
    ```
    //行内元素的父元素添加text-align:center;
    .main{
        width:100px;
        height:100px;
        text-align:center;
        border:1px solid red;
    }
    ```
2. **块元素水平(block)水平居中**  

    - 利用margin居中  

        <font size="2">html</font>
        ```
        <div class="main">
            <div class="center">居中</div>
        </div>
        ```
        <font size="2">css</font>
        ```
        //块元素添加宽高,并设置`margin:0 auto`;水平居中
        .main{
            width:100px;
            height:100px;
            border:1px solid green;
        }
        .center{
            width:50px;
            height:50px;
            margin:0 auto;
            border:1px solid red;
        }
        ```
    - 利用绝对定位  

        <font size="2">html</font>
        ```
        <div class="main">
            <div class="center">居中</div>
        </div>
        ```
        <font size="2">css</font>
        ```
        //块元素添加宽高,left设置(离左边的距离-本身的宽度/2)
        .main{
            width:100px;
            height:100px;
            border:1px solid green;
            position:relative;
        }
        .center{
            width:50px;
            height:50px;
            border:1px solid red;
            position:absolute;
            top:0;
            left:25px;
        }
        ```
## 垂直居中  
1. **行内元素(inline)垂直居中** 
    - 利用line-height   
        <font size="2">html</font>
        ```
        <div class="main">
            <span class="center">居中</span>
        </div>
        ```
        <font size="2">css</font>
        ```
        //设置行内元素的父元素的height和line-height相同
        .main{
            width:100px;
            height:100px;
            line-height:100px;
            border:1px solid red;
        }
        ```
    
2. **块元素(block)垂直居中 ** 
    - 利用父元素padding上下相等  
        <font size="2">html</font>
        ```
        <div class="main">
            <span class="center">居中</span>
        </div>
        ```
        <font size="2">css</font>
        ```
        .main{
            background:red;
            font-size:16px;
            padding-top:50px;
            padding-bottom:50px;
        }
        ```
    - 利用绝对定位  
        <font size="2">html</font>
        ```
        <div class="main">
            <div class="center">居中</div>
        </div>
        ```
        <font size="2">css</font>
        ```
        .main{
            border:1px solid red;
            position:relative;
            width:100px;
            height:100px;
        }
        .center{
            position:absolute;
            width:50px;
            height:50px;
            top:0;
            right:0;
            bottom:0;
            left:0;
            margin:auto;
        }
        ```
    - 利用负margin  
        <font size="2">html</font>
        ```
        <div class="main">
            <div class="center">居中</div>
        </div>
        ```
        <font size="2">css</font>
        ```
        //top&right设置为父元素的一半,块元素的负margin设置为其宽高的一半
        .main{
            background:red;
            position:relative;
            width:100px;
            height:100px;
        }
        .center{
            position:absolute;
            width:60px;
            height:60px;
            top:50px;
            right:50px;
            margin-top:-30px;
            margin-right:-30px;
        }
        ```
## 其他小技巧  
    待补坑......

