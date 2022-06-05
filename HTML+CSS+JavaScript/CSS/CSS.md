# CSS

## 目录

*   [什么是CSS？](#什么是css)

*   [CSS的导入方式](#css的导入方式)

*   [CSS选择器](#css选择器)

*   [CSS常用属性](#css常用属性)

    *   [文字属性](#文字属性)

    *   [字体属性](#字体属性)

    *   [颜色属性](#颜色属性)

    *   [背景相关属性](#背景相关属性)

    *   [盒子阴影和文字阴影](#盒子阴影和文字阴影)

    *   [边框属性](#边框属性)

    *   [内外边框属性](#内外边框属性)

## 什么是CSS？

*   CSS是一门用于控制网页表现的语言

*   CSS（Cascading Style Sheet）：层叠样式表

## CSS的导入方式

1.  内联样式：在标签内部使用style属性，属性值是css属性键值对

    ```html
    <div style="color:red">Hello CSS</div>
    ```

2.  内部样式：定义\<style>标签，在标签内部定义css样式

    ```html
    <style type="text/css">
      div{
        color:red
      }
    </style>
    ```

3.  外部样式：定义link标签，引入外部的css文件

    ```html
    <link rel="stylexheet" href="demo.css">

    ```

    demo.css:

    ```html
    div{
      color:red
    }
    ```

## CSS选择器

*   概念：选择器是选取所需设置样式的元素（标签）

*   分类

    1.  元素选择器

        元素名称{color:red;}

        ```html
        div{
          color:red;
        }

        <div>hello css1</div>
        ```

    2.  id选择器

        id属性值{color:red;}

        ```html
        #name{
          color:red;
        }

        <div id="name">hello css2</div>
        ```

    3.  类选择器

        .class属性值{color:red;}

        ```html
        .cls{
          color:red;
        }

        <div class="cls">hello css3</div>
        ```

## CSS常用属性

### 文字属性

*   font-style：取值

    作用：规定文字样式

    *   取值：

        normal：正常的，默认就是正常的

        italic：倾斜的

*   font-weight：取值

    作用：规定文字粗细

    *   取值

        bold：加粗

        bolder：加加粗

        lighter：细线，默认就是细线

*   font-size：取值

    作用：规定文字大小

    *   取值

        格式：font-size：30px;

        单位：px（像素pixel）

        注意点：通过font-size设置大小一定要带单位

*   font-family：取值

    作用：规定文字字体

    *   取值

        格式：font-family："楷体";

        注意点：

        1⃣如果取值是中文，需要用双引号或单引号括起来

        2⃣️设置的字体必须是用户电脑里面已经安装的字体

### 字体属性

*   text-decoration：取值

    作用：给文本增加装饰

    *   取值

        underline：下划线

        line-through：删除线

        overline：上划线

        nooe：什么都没有，常用的用途就是用于，去掉超链接的下划线

*   text-align：取值

    作用：设置文本水平对齐方式

    *   取值

        left：居左

        right：居右

        center：居中

*   text-indent：取值

    作用：设置文本缩进

    *   取值

        2em，其中em为单位，一个em表示缩进一个文字的宽度

### 颜色属性

*   color：取值

    *   取值

        1.  英文单词

        2.  rgb

        3.  rgba

        4.  十六进制

### 背景相关属性

*   background-color：取值

    作用：设置背景颜色属性

    *   取值

        1.  英文单词

        2.  rgb

        3.  rgba

        4.  十六进制

*   background-image：url（）的属性

    作用：用于设置背景图片

    *   注意点

        1.  图片地址必须放在url（）当中，地址可以为本地地址，也可以为网络的地址

        2.  如果图片的大小没有标签的大小大，就会自动在水平和垂直方向平铺来填充

        3.  如果网页上出现了图片，那么浏览器会再次发送请求获取图片

*   background-repeat：属性

    作用：用于控制背景图片的平铺方式

    应用场景：可以通过背景图片的平铺来降低图片的大小，提升网页的访问速度

    *   取值

        repeat：默认，在水平和垂直都需要平铺

        no-repeat：在水平和垂直都不需要平铺

        repeat-x：只在水平方向平铺

        repeat-y：只在垂直方向平铺

*   background-position：属性

    作用：用于控制背景图片的位置

    格式：background- position：水平风向 垂直方向；

    *   取值

        1.  具体的方位名词：

            水平方向：left center right

            垂直方向：top center bottom

        2.  具体像素：

            一定要写单位，即px

            具体的像素可以接受负数

### 盒子阴影和文字阴影

### 边框属性

*   边框就是环绕在标签宽度和高度周围的线条

*   格式（连写）

    border：边框宽度 边框样式 边框颜色

    *   注意点

        1.  连写格式中颜色属性可以忽略，忽略之后默认是黑色

        2.  连写格式中样式不能忽略，忽略后不能看到边框

        3.  连写格式中宽度不能忽略，忽略后还可以看到边框

*   分别单独设置四条边的边框

    border-top：边框宽度 边框样式 边框颜色

    border-right：边框宽度 边框样式 边框颜色

    border-bottom：边框宽度 边框样式 边框颜色

    border-left：边框宽度 边框样式 边框颜色

*   边框样式中常见取值

    border-style：取值

    solid 实线

    double 双实线

    dashed 虚线

    dotted 圆点

### 内外边框属性

1.  边框和内容之间的距离就是内边距

    *   格式

        1.  非连写：

            padding-top：值px

            padding-right：值px

            padding-bottom：值px

            padding-left：值px

        2.  连写：

            padding：上 右 下 左

            注⚠️：上右下左的取值省略规律同边框取值省略相同

    *   注意点：

        1.  给标签设置内边距之后，标签占有的宽度和长度会发生变化

        2.  给标签设置内边距之后，内边距也会有背景颜色

2.  标签与标签之间的距离就是外边距

    *   格式

        1.  非连写：

            margin-top：值px

            margin-right：值px

            margin-bottom：值px

            margin-left：值px

        2.  连写：

            margin：上 右 下 左

    *   注意点：

        1.  外边距的那一部分是没有背景颜色的

        2.  水平方向上，外边距可以叠加

        3.  在默认布局的垂直方向上，外边距不会叠加，会出现外边距合并，谁的外边距大就听谁的
