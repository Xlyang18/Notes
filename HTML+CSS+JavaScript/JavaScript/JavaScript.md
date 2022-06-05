# JavaScript

## 目录

*   [简介](#简介)

*   [用法](#用法)

*   [JavaScript引入方式](#javascript引入方式)

*   [书写语法](#书写语法)

*   [变量](#变量)

*   [数据类型](#数据类型)

*   [运算符](#运算符)

## 简介

*   &#x20;javascript说互联网上最流行的脚本语言，可用于HTML和web

*   &#x20;JavaScript是脚本语言

    *   是一种轻量化的编程语言

    *   是可以插入HTML页面的编程代码

    *   可由所有浏览器解释并执行

## 用法

*   javascript脚本代码必须位于\<script>与\</script>标签之间

*   javascript脚本代码可被放置在HTML页面的\<body>标签内

## JavaScript引入方式

1.  内部脚本：将JS代码定义在HTML页面中

    在HTML中，JavaScript代码必须位于\<script>标签内

    ```html
    <script>
        alert("hello JS");
    </script>
    ```

2.  外部脚本：将JS代码定义在外部JS文件当中，然后引入到HTML页面当中

    *   外部文件：demo.js

        ```html
        alert("hello JS");
        ```

    *   引入外部文件

        ```html
        <script src="demo.js"></script>
        ```

        注意⚠️：

        1.  外部脚本不能包含\<script>标签

        2.  \<script>标签不能自闭合

## 书写语法

1.  区分大小写：变量名、函数名以及其他一切东西都是区分大小写的

2.  美航结尾的分号可有可无

3.  注释书写的规范：

    *   单行注释：

        ```html
        // 注释内容
        ```

    *   多行注释：

        ```html
        /*
        注释内容
        注释内容
        */
        ```

4.  大括号代表代码库

    ```html
    if(count){
      alert(count);
    }
    ```

## 变量

*   javascript中使用var关键字来声明变量

    var的作用域为全局变量；变量可以重复定义

    ```html
    var test = 20;
    test = "张三";
    ```

*   javascript是一门弱类型的语言，变量可以存放不同类型的值

*   ECMAScript 6 新增了let关键字来定义变量，它的用法类似于var，但是所声明的变量，只在let关键字所在的代码块内有效，且不允许重复声明

*   ECMAScript 6 新增了const关键字，用来声明一个只读的常量。一旦声明，常量的值就不能被改变

## 数据类型

JavaScript中分为：原始类型和引用类型

五种原始类型：

*   number：数字（整数、小数、）

*   string：字符、字符串（单双引号均可）

*   boolean：布尔值（true、false）

*   null：对象为空

*   undefinde：当声明的变量为初始化时，该变量的默认值为undefined

***

*   使用typeof运算符可以获取数据类型

    ```html
    <script>
        alert(typeof age);
    </script>
    ```

## 运算符

*   基本与java语法中的运算符相似

*   特殊规则：

    1.  "==" 和 "===" 的区别（"=="会进行类型转换，"==="不会进行类型转换）

        *   "=="会判断两边需要比较的数据的类型是否一致

            *   如果不一样，则会进行类型之后

            *   再去比较

            ```html
            <script>
                var age1 = 20;
                var age2 = "20";
                
                alert(age1==age2); // 返回结果为true
            </script>
            ```

            ***

        *   "==="会判断类型是否一样，如果不一样，直接返回false

            *   类型一样则再会去比较两个数据是否相同

            ```html
            <script>
                var age1 = 20;
                var age2 = "20";
                
                alert(age1===age2); // 返回结果为false
            </script>
            ```

***

*   类型转换：

    *   其他类型转换为number：

        1.  string：按照字符串的自勉之，转为数字，如果字面值不是数字，则转为NaN，一般使用parseInt()

        2.  boolean：true转为1，false转为0

            ```html
            <script>
                var str1 = +"20"; // 在字符串类型上面加正负号，可以转换为数字类型（不常用）
                
                var str2 = "20";
                alert(parseInt(str2)); // 使用parseInt方法（常用的主流方法）
                
                var flag = +false;
                alert(flag); // 此处转换为数字 0
            </script>
            ```

    *   其他类型转换为boolean：

        1.  number：0和NaN转换为false，其他的数字转为true

        2.  string：空字符串转为false，其他的字符串转为true

        3.  null：false

        4.  undefined：false
