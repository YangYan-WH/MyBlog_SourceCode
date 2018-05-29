---
title: CSS Layout
date: 2018-05-29 21:51:35
tags:
---
# CSS布局 

## 左右布局 
1. **利用浮动** 
    
    html
    ```
    <div class="main clearfix">  <!-- 父元素需要清除浮动 -->
        <div class="left">left</div>
        <div class="right">right</div>
    </div>
    ```
    css
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

    html
    ```
    <div class="main">
        <div class="left">left</div>
        <div class="right">right</div>
    </div>
    ```
    css
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

    html
    ```
    <div class="main">
        <div class="left">left</div>
        <div class="right">right</div>
    </div>
    ```
    css
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