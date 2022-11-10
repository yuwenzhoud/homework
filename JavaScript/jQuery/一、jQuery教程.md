# 一、jQuery教程

## 1、简介

### jQuery 库 - 特性

jQuery 是一个 JavaScript 函数库。

jQuery 库包含以下特性：

- HTML 元素选取
- HTML 元素操作
- CSS 操作
- HTML 事件函数
- JavaScript 特效和动画
- HTML DOM 遍历和修改
- AJAX
- Utilities

### 添加jQuery

jQuery 库位于一个 JavaScript 文件中，其中包含了所有的 jQuery 函数。

可以通过下面的标记把 jQuery 添加到网页中：

```
<head>
<script type="text/javascript" src="jquery.js"></script>
</head>
```

请注意，<script> 标签应该位于页面的 <head> 部分。

### 库的替代

Google 和 Microsoft 对 jQuery 的支持都很好。可以从 Google 或 Microsoft 加载 CDN jQuery 核心文件。

#### 1>使用 Google

```js
<head>
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs
/jquery/1.4.0/jquery.min.js"></script>
</head>
```

#### 2>使用 Microsoft

```js
<head>
<script type="text/javascript" src="http://ajax.microsoft.com/ajax/jquery
/jquery-1.4.min.js"></script>
</head>
```

## 2、语法

 **通过 jQuery，您可以选取（查询，query） HTML 元素，并对它们执行“操作”（actions）。** 

jQuery 语法是为 HTML 元素的选取编制的，可以对元素执行某些操作。

基础语法是：*$(selector).action()*

- 美元符号定义 jQuery
- 选择符（selector）“查询”和“查找” HTML 元素
- jQuery 的 action() 执行对元素的操作

#### (1)示例

```js
$(this).hide() - 隐藏当前元素

$("p").hide() - 隐藏所有段落

$(".test").hide() - 隐藏所有 class="test" 的所有元素

$("#test").hide() - 隐藏所有 id="test" 的元素
```

#### (2)文档就绪函数

您也许已经注意到在我们的实例中的所有 jQuery 函数位于一个 document ready 函数**里面**：

```
$(document).ready(function(){

--- jQuery functions go here ----

});
```

这是为了防止文档在完全加载（就绪）之前运行 jQuery 代码。

如果在文档没有完全加载之前就运行函数，操作可能失败。下面是两个具体的例子：

- 试图隐藏一个不存在的元素
- 获得未完全加载的图像的大小

## 3、选择器

 **选择器允许您对元素组或单个元素进行操作。** 

jQuery 元素选择器和属性选择器允许您通过标签名、属性名或内容对 HTML 元素进行选择。选择器允许您对 HTML 元素组或单个元素进行操作。

### (1)元素选择器

jQuery 使用 CSS 选择器来选取 HTML 元素。

```js
$("p") 选取 <p> 元素。

$("p.intro") 选取所有 class="intro" 的 <p> 元素。

$("p#demo") 选取所有 id="demo" 的 <p> 元素。
```



### (2)属性选择器

jQuery 使用 XPath 表达式来选择带有给定属性的元素。

```js
$("[href]") 选取所有带有 href 属性的元素。

$("[href='#']") 选取所有带有 href 值等于 "#" 的元素。

$("[href!='#']") 选取所有带有 href 值不等于 "#" 的元素。

$("[href$='.jpg']") 选取所有 href 值以 ".jpg" 结尾的元素。
```



### (3)CSS 选择器

jQuery CSS 选择器可用于改变 HTML 元素的 CSS 属性。

下面的例子把所有 p 元素的背景颜色更改为红色：

**实例**

```js
$("p").css("background-color","red");
```

 [jQuery 选择器参考手册](https://www.w3school.com.cn/jquery/jquery_ref_selectors.asp)。 

### (4)选择器实例

| 语法                | 描述                                              |
| ------------------- | ------------------------------------------------- |
| $(this)             | 当前HTML元素                                      |
| $("p")              | 所有<p>元素                                       |
| $("p.into")         | 所有class ="into"的<p>元素                        |
| $(".into")          | 所有class= "into"的元素                           |
| $("#into")          | id= "into"的元素                                  |
| $("ul li:first")    | 每一个<ul>l的第一个<li>元素                       |
| $("[herf$='.jpg']") | 所有带有以".jpg"结尾的属性值的herf属性            |
| $("div#into .head") | id = "into"的<div>元素中的所有class= "hand"的元素 |

## 4、事件

 **jQuery 是为事件处理特别设计的。** 

### (1)事件函数

jQuery 事件处理方法是 **jQuery 中的核心函数。**

事件处理程序指的是当 HTML 中发生某些事件时所调用的方法。术语由事件“触发”（或“激发”）经常会被使用。通常会把 jQuery 代码放到 <head>部分的事件处理方法中：

**实例**

```javascript
<html>
<head>
    //将jQuery代码放到head部分里面;
<script type="text/javascript" src="jquery.js"></script>
<script type="text/javascript">
$(document).ready(function(){
  $("button").click(function(){//按钮的点击事件，触发时调用一个函数;
    $("p").hide();//隐藏所有的<p>元素;
  });
});
</script>
</head>

<body>
<h2>This is a heading</h2>
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
<button>Click me</button>
</body>

</html>
```

### (2)单独文件中的函数

如果您的网站包含许多页面，并且您希望您的 jQuery 函数易于维护，那么请把您的 jQuery 函数放到独立的 .js 文件中。

**实例**

```js
<head>
    //添加jQuery
<script type="text/javascript" src="jquery.js"></script>  
//独立的js文件，存放自己的jQuery函数;
<script type="text/javascript" src="my_jquery_functions.js"></script>
</head>
```



### (3)jQuery 名称冲突

jQuery 使用 $ 符号作为 jQuery 的简介方式。

某些其他 JavaScript 库中的函数（比如 Prototype）同样使用 $ 符号。

jQuery 使用名为 noConflict() 的方法来解决该问题。

```js
var jq=jQuery.noConflict()，
```

帮助您使用自己的名称（比如 jq）来代替 $ 符号

**实例**

```js
<!DOCTYPE html>
<html>
<head>
<script src="/jquery/jquery-1.11.1.min.js"></script>
<script>
$.noConflict();
jQuery(document).ready(function(){
  jQuery("button").click(function(){
    jQuery("p").text("jQuery 仍在运行！");
  });
});
</script>
</head>

<body>
<p>这是一个段落。</p>
<button>测试 jQuery</button>
</body>
</html>
```



### (4)结论

由于 jQuery 是为处理 HTML 事件而特别设计的，那么当您遵循以下原则时，您的代码会更恰当且更易维护：

- 把所有 jQuery 代码置于事件处理函数中
- 把所有事件处理函数置于文档就绪事件处理器中
- 把 jQuery 代码置于单独的 .js 文件中
- 如果存在名称冲突，则重命名 jQuery 库

### (5)jQuery事件

**例子**

| Event函数                       | 绑定函数至                                     |
| ------------------------------- | ---------------------------------------------- |
| $(documet).ready(function)      | 将函数绑定到文档就绪事件（当文档完成加载时光） |
| $(selector).click(function)     | 触发或将函数绑定到被选元素的点击事件           |
| $(selector).dbclick(funcion)    | 触发或将函数绑定到被选元素的双击事件           |
| $(selector).focus(function)     | 触发或将函数绑定到被选元素的获取焦点事件       |
| $(selector).mouseover(function) | 触发或将函数绑定到被选元素的鼠标悬停事件       |

  [jQuery 事件参考手册](https://www.w3school.com.cn/jquery/jquery_ref_events.asp)。 

