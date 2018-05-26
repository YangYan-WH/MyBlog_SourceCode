---
title: HTML
date: 2018-05-22 22:26:00
tags:
---
> Hypertext Markup Language，简称HTML，用来结构化Web网页及其内容的标记语言，HTML由一系列的元素组成，我们可以使用它来封装，包装或标记内容的不同部分，使其以某种方式显示，或以某种方式执行。 

**HTML元素** 
1. 元素的主要由以下几个部分组成  
2. 开始标签（open tag）
3. 结束标签（closing tag）（空标签没有结束标签）
4. 内容（content）
5. 元素（element）—— 开始标记+结束标记+内容 = 元素  

**常用标签简介**  
- ``<html><head></head><body></body></html>``  HTML文档基本结构标签  

- ``<style></style> <link rel="stylesheet" type="text/css" href="theme.css" />``样式标签，前者是内部样式，后者是外部样式且属于空标签  

- ``<h1></h1>  ~~   <h6></h6>``  标题标签 ，从一级标题到六级标题  

- ``<p></p>`` 段落标签  
- ``<main></main> <header></header> <footer></footer>`` 语义化标签，区分文档内容  

- ``<ul></ul>`` 无序列表，通常配合``<li></li>``使用  
    ```
    <ul>
        <li></li>
        <li></li>
        <li></li> 
    </ul>
    ```
- ``<ol></ol>``有序列表，配合``<li></li>``使用
    ```
    <ol>
        <li></li>
        <li></li>
        <li></li>
    </ol>
    ```
- ``<img src="xxx">`` 图片标签，空标签，可替换标签，src输入地址可以显示图片  

- ``<iframe src="xxx" name=“”></iframe>`` 页面嵌套标签  

- ``<a href="xxx"></a>`` 超链接标签，页面跳转（HTTP GET请求），下有a标签几种用法  
    - ``<a href="#"></a>`` 点击锚点不发出请求  
    - ``<a href="javascript:;"></a>`` 标签中存在伪协议标签，点击后不进行任何操作iframe 和 a 结合使用  
    属性见 MDN https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a  
    ``` 
    <iframe name=xxx src="#"></iframe>
    <a target=xxx href="www.qq.com"></a> //点击a标签，会在iframe处打开网页
    ```    
- ``<form action="" ></form>``  表单标签，页面跳转（HTTP POST请求）  
属性见MDN https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/form  

- ``<label><input type="xxx" ></label>`` 表单输入标签  
    - type="text"   文本输入框  
    - type="password"  密码输入框  
    - type="checkbox" 多选框  
    - type="radio" 单选框  同一个name的radio，只能选一个  
    - type="date" 日期选择  
    - type="submit" 提交按钮  
    input属性见MDN https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input  
- ``<button></button>`` 输入标签 ,与input的区别是，input为空标签  
    如果一个form只有一个button且没有写类型，那么button会自动变为submit提交按钮  

- ``<table><table>`` 表格标签，用于页面展示表格  
    - ``<caption></caption>`` 可选元素，用于展示表格标题  
    - ``<thead></thead>`` 可选元素，表示表格第一部分  
    - ``<tfoot></tfoot>`` 可选元素，表示表格最后部分  
    - ``</tbody></tbody>`` 表示表格主体部分  
    - ``<tr></tr>`` 表格中的行  
    - ``<td></td>`` 表格中的数据，通常包裹在``<tr></tr>``之间，表现为列  
