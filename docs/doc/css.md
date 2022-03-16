> #### CSS 选择器及其优先级

| 选择器 | 格式 |   优先级权重     |
| ------------- | ------------- | ------------- |
| id选择器 | `#id` | 100 |
| 类选择器 | `#classname` | 10 |
| 属性选择器 | `a[ref=“eee”]` | 10 |
| 伪类选择器 | `li:last-child` | 10 |
| 标签选择器 | `div` | 1 |
| 伪元素选择器 | `li:after` | 1 |
| 相邻兄弟选择器 | `h1+p` | 0 |
| 子选择器 | `ul>li` | 0 |
| 后代选择器 | `li a` | 0 |
| 通配符选择器 | `*` | 0 |

- !important声明的样式的优先级最高
- 如果优先级相同，则最后出现的样式生效
- 继承得到的样式的优先级最低
- 通用选择器（*）、子选择器（>）和相邻同胞选择器（+）并不在这四个等级中，所以它们的权值都为 0
- 样式表的来源不同时，优先级顺序为：内联样式> 内部样式 > 外部样式 > 浏览器用户自定义样式 > 浏览器默认样式


> #### display的属性值及其作用

| 属性值 | 作用 |
| ------------- | ------------- |
| none | 元素不显示，并从文档流中移除。|
| block | 块类型。默认宽度为父元素宽度，可设置宽高，换行显示。|
| inline | 行内元素类型。默认宽度为内容宽度，不可设置宽高，同行显示。|
| inline-block | 默认宽度为内容宽度，可以设置宽高，同行显示。|
| list-item | 像块类型元素一样显示，并添加样式列表标记。|
| table | 此元素会作为块级表格来显示。|
| inherit | 规定应该从父元素继承display属性的值。|

> #### 了解重绘和重排吗，知道怎么去减少重绘和重排吗，让文档脱离文档流有哪些方法

DOM的变化影响到了预算内宿的几何属性比如宽高，浏览器重新计算元素的几何属性，其他元素的几何属性也会受到影响，浏览器需要重新构造渲染书，这个过程称之为重排，浏览器将受到影响的部分重新绘制在屏幕上 的过程称为重绘，引起重排重绘的原因有：
添加或者删除可见的DOM元素，

- 元素尺寸位置的改变

- 浏览器页面初始化，

- 浏览器窗口大小发生改变，重排一定导致重绘，重绘不一定导致重排，

- 减少重绘重排的方法有：

- 不在布局信息改变时做DOM查询，

- 使用csstext,className一次性改变属性

- 使用fragment

- 对于多次重排的元素，比如说动画。使用绝对定位脱离文档流，使其不影响其他元素

> #### CSS3弹性盒子

弹性盒子是CSS3的一种新布局模式。

CSS3 弹性盒（ Flexible Box 或 flexbox），是一种当页面需要适应不同的屏幕大小以及设备类型时确保元素拥有恰当的行为的布局方式。

引入弹性盒布局模型的目的是提供一种更加有效的方式来对一个容器中的子元素进行排列、对齐和分配空白空间。

>#### 行内元素与块级元素互相转换

- display:inline; 转换为行内元素
- display:inline-block;转换为行内块元素
- display:block;转换为块元素

>#### link和@import区别

- link兼容性好
- 两者加载顺序不一样 先加载link

>#### css的盒子模型有哪些？
- **标准盒子模型**:margin、border、padding、content
- **IE盒子模型**:margin、content、(border + padding + content)

*通过css如何转换盒子模型*
- box-sizing:content-box;**标准盒子模型**
- box-sizing:border-box;**IE盒子模型**

>#### line-height和height区别

- line-height是每一行文字的高，换行后盒子高度会增大（行数*行高）；
- height是一个死值，就是这个盒子的高度；

>#### css的选择符有哪些？哪些属性可以继承？

- css选择符
  - 通配（*）
  - id选择器（#）
  - 类选择器（.）
  - 标签选择器（div、p、h1）
  - 相邻选择器（+）
  - 后代选择器（ul li）*ul li + li{} //排除第一个li*
  - 子元素选择器（>）
  - 属性选择器（a[href]）
- css属性那些可与继承:
  - **文字系列**：font-size、color、line-height、text-align...
  *不可继承属性：border、padding、margin...*

>#### css的优先级算法如何计算？

- **优先级比较：** !important > 内联样式 > id > class > 标签 > 通配
- **css权重计算**
    - 内联样式：1000
    - id选择器：100
    - 类选择器：10
    - 标签&伪元素选择器：1
    - 通配、>、+：0

>#### css画个三角形？

- **用边框画**  
`border-left:100px solid #ccc;`  
`border-top:100px solid transparent;`  
`border-right:100px solid transparent;`  
`border-bottom:100px solid transparent;`

>#### 一个盒子不给宽高怎么垂直居中

- 方式一：  
    `{`  
        `display:flex;  `    
	    `justify-content:center;  `    
	    `align-items:center;   `     
    `}`

- 方式二：  
    `{`  
       `position:absolute; `  
	   `top:50%; `  
	   `left:50;`  
	   `transform:translate(-50%,-50%);`     
    `}`
>#### display有哪些值

-  **none** 隐藏元素
-  **inline** 转换为内联元素
-  **block** 转换为块元素
-  **inline-block** 转换为行内块元素

>#### 对BFC规范（块级格式化上下文）的理解

- **BFC就是页面上一个隔离的独立容器，容器里面的子元素不会影响到外部的元素；**
    - **1.了解BFC** : 块级格式化上下文；
    - **2.BFC原则** : 如果一个元素具有BFC，那么内部元素怎么样都不会影响外面元素；
    - **3.触发BFC** :   
        float的值为none；
        overflow的值为非visible；  
        display的值为：inline-block、table-cell...  
        position的值为：absoute、fixed  