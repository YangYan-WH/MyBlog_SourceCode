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
    }
    .right{
        float:right;
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
        left:0;
    }
    .right{
        position:absolute;
        right:0;
    }