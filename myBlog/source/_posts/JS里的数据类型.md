---
title: JS里的数据类型
date: 2018-06-20 19:23:13
tags:
---
## JS里的数据类型  
  Javascript共有7种数据类型  
1. **数字 number ** 
    0b二进制  011八进制  0x十六进制  
  
2. **字符串 string**  
    - 用 `' '`或 `" "` 包含,通常只用一种  
    - 符号通常需要进行转义,如  
        `'\''` 单引号  
        `\n'`  回车  
        `\t`   制表符  
        `'\\'` 斜杠  
    - 多行字符串  
    ```
        var s='12345 \
                67890';
        var s1='12345' +
                '67890';
        通常情况会使用第二种
    ```
3. **布尔 boolean**  
    && 与  
    || 或  
4. **Symbol**  
    现在不需要深入了解  
5. **null**  
6. **undefined**
    null undefined都表示什么都没有  
    - 变量没有赋值,通常使用undefined
    - 有一个对象object,现在没有赋值,通常使用null
    - 有一个非对象,现在没有赋值,通常使用undefined  
7. **对象 object  哈希表**  
    number,string,boolean,null,undefined即简单类型(基本类型)  
    object对象(哈希表)即复杂类型由复杂类型,由简单类型组成  
    ```
    {
        name:'Yang',
        age:'18' //key可以不加引号,但是必须遵守标识符的规则
        '':'Yan' //空key表示Yan
    }
    ```
    *注意*  
    *JS有两个bug*  
        - *typeof null 为object*
        - *typeof function 为function*  


## 数据类型转换  

1. 转换为字符串  
    - obj.toString()  
    利用.toString(),null/undefined 会报错,object会获得[object object]
    - String()  
    ```
    String(1) //1
    String(true) //true
    String(function test(){})  //function test(){}
    String(null) String(undefined) // null undefined
    ```
    - Something + ''
    ```
    1+'' //1
    true + '' //true
    obj+'' // obj
    null/undefined + '' //null/undefined
    ```
    *通常我们使用加上空字符串(+'')来进行字符串转换*  

2. 转换为布尔值  
    - 常见两种转换方式Boolean() , !!true  
    - *通常我们使用!!()来进行字符串转换*
    - 需要注意的只有5个特殊值的布尔值是false  
        0 , NaN , '' , null , undefined  

3. 转换为数字  
    - Number('1') === 1  
    - parseInt('1',10) ===1  //转化为十进制  
    - parseFloat('1.23') ===1.23  
    - '1' - 0 ===1
    - +'1' === 1
    - parseInt('s') // 字符串转化为数字为NaN
    - parseInt('1s') // 1 ,取字符串前面的数字