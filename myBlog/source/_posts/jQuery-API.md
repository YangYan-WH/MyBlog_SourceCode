---
title: jQuery API
date: 2018-07-31 10:50:16
tags:
---
> 实现一个jQuery的API
```
window.jQuery = ???
window.$ = jQuery

var $div = $('div')
$div.addClass('red') //可将所有div的class添加一个red
$div.setText('hi') //可将所有div的textContent变为hi
```

### 最终代码
```
    window.jQuery = function (nodeOrSelector) {
        let nodes = {}
        if (typeof nodeOrSelector === 'string') {
            let temp = document.querySelectorAll(nodeOrSelector)
            for (let i = 0; i < temp.length; i++) {
                nodes[i] = temp[i]
            }
            nodes.length = temp.length
        } else if (nodeOrSelector instanceof Node) {
            nodes = {
                0: nodeOrSelector,
                length: 1
            }
        }
        nodes.addClass = function (value) {
            for (let i = 0; i < nodes.length; i++) {
                nodes[i].classList.add(value)
            }
        }
        nodes.setText = function (text) {
            for (let i = 0; i < nodes.length; i++) {
                nodes[i].textContent = text
            }
        }
        return nodes
    }
```  

### 第一步 获取传参 
1. 声明一个对象  
    `let nodes = {}`
2. 判断传入参数的类型
    1) 如果传参的类型为 *字符串* ,则返回一个*伪数组*对象,伪数组的value是通过该参数获取到的节点,length是获取到的节点数量;
    ``` 
    if (typeof nodeOrSelector === 'string') {
        let temp = document.querySelectorAll(nodeOrSelector)
        for (let i = 0; i < temp.length; i++) {
            nodes[i] = temp[i]
        }
        nodes.length = temp.length
    } 
    ``` 
    2) 如果传参的类型是 *节点* , 则返回一个*伪数组*对象,伪数组的value就是参数,length为1;
    ``` 
    else if (nodeOrSelector instanceof Node) {
        nodes = {
            0: nodeOrSelector,
            length: 1
        }
    }
    ``` 

### 第二步 添加API 
   1. **addClass**
   将获取到的节点nodes遍历,并添加类名为参数value
``` 
   nodes.addClass = function (value) {
        for (let i = 0; i < nodes.length; i++) {
            nodes[i].classList.add(value)
        }
    }
``` 
   2. **setText**
   将获取到的节点nodes遍历,并设置内容为参数text
``` 
   nodes.setText = function (text) {
        for (let i = 0; i < nodes.length; i++) {
            nodes[i].textContent = text
        }
    }
``` 

### 第三步 返回节点
   `return nodes`

### 小结 
> 在写API的过程中,尤其需要注意的地方是第一步 获取参数 ,当传参是字符串时,我们根据字符串利用浏览器DOM获取到的几点nodes是一个伪数组,那么当参数是node时,我们同样要返回一个伪数组,此时需要我们自己构造一个伪数组{value,length:1},最后不要忘了return nodes