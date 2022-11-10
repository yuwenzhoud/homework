# 三、jQuery HTML

## 1、获得内容和属性

### ~ 获得内容

 text()、html() 以及 val()

三个简单实用的用于 DOM 操作的 jQuery 方法：

- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值

通过 jQuery text() 和 html() 方法来**获得内容**：

**实例**

```js
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});
```

通过 jQuery val() 方法获得**输入字段的值**：

**实例**

```
$("#btn1").click(function(){
  alert("Value: " + $("#test").val());
});
```

### ~ 获取属性

 jQuery attr() 方法用于**获取属性值**。 

实例：如何获得链接中 href 属性的值：

```js
<script>
    $("button").click(function(){
  	alert($("#w3s").attr("href"));
	});
</script>

<p><a href="http://www.w3school.com.cn" id="w3s">W3School.com.cn</a></p>
    
    //弹窗：http://www.w3school.com.cn
```

##  2、设置内容和属性

### ~ 设置内容

设置内容 - text()、html() 以及 val()

- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值

下面的例子演示如何通过 text()、html() 以及 val() 方法来设置内容：

实例

```js
$("#btn1").click(function(){
  $("#test1").text("Hello world!");
});
$("#btn2").click(function(){
  $("#test2").html("<b>Hello world!</b>");
});
$("#btn3").click(function(){
  $("#test3").val("Dolly Duck");
});
```



text()、html() 以及 val() 的回调函数

上面的三个 jQuery 方法：text()、html() 以及 val()，同样拥有回调函数。回调函数由两个参数：**被选元素列表中当前元素的下标，以及原始（旧的）值。**

然后以函数新值返回您希望使用的字符串。

实例：带有回调函数的 text() 和 html()：

```js
$("#btn1").click(function(){
  $("#test1").text(function(i,origText){
    return "Old text: " + origText + " New text: Hello world!
    (index: " + i + ")";
  });
});

$("#btn2").click(function(){
  $("#test2").html(function(i,origText){
    return "Old html: " + origText + " New html: Hello <b>world!</b>
    (index: " + i + ")";
  });
});
```

### ~ 设置属性

 jQuery attr() 方法也用于设置/改变属性值。 

实例： 演示如何改变（设置）链接中 href 属性的值：

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#w3s").attr("href","http://www.w3school.com.cn/jquery");
  });
});
</script>
</head>

<body>
<p><a href="http://www.w3school.com.cn" id="w3s">W3School.com.cn</a></p>
<button>改变 href 值</button>
</body>
```



attr() 方法也允许**同时设置多个属性**。

实例：如何同时设置 href 和 title 属性：

```js
$("button").click(function(){
  $("#w3s").attr({
    "href" : "http://www.w3school.com.cn/jquery",
    "title" : "W3School jQuery Tutorial"
  });
});
```

attr() 的回调函数

jQuery 方法 attr()，也提供回调函数。回调函数由两个参数：**被选元素列表中当前元素的下标，以及原始（旧的）值**。然后以函数新值返回您希望使用的字符串。

实例：演示带有回调函数的 attr() 方法：

```js
$("button").click(function(){
  $("#w3s").attr("href", function(i,origValue){
    return origValue + "/jquery";
  });
});
```

## 3、添加元素

语法：

```js
$("p").append("需要插入的内容");

$("p").prepend("需要插入的内容");
```

### ~ append(结尾)

在被选元素的结尾插入内容

实例：

```js
<script src="/jquery/jquery-1.11.1.min.js">
</script>
<script>
$(document).ready(function(){
  $("#btn1").click(function(){
    $("p").append(" <b>Appended text</b>.");//p标签内容的结尾插入
  });

  $("#btn2").click(function(){
    $("ol").append("<li>Appended item</li>");//有序列表的结尾，即最后一个li
  });
});
</script>

<body>
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
<ol>
<li>List item 1</li>
<li>List item 2</li>
<li>List item 3</li>
</ol>
<button id="btn1">追加文本</button>
<button id="btn2">追加列表项</button>
</body>

/*
This is a paragraph. Appended text.

This is another paragraph. Appended text.

1.List item 1
2.List item 2
3.List item 3
4.Appended item
*/
```



### ~ prepend(开头)

在被选元素的开头插入内容

实例：

```js
<script>
$(document).ready(function(){
  $("#btn1").click(function(){
    $("p").prepend("<b>Prepended text</b>. ");//p标签内容的的开头;
  });
  $("#btn2").click(function(){
    $("ol").prepend("<li>Prepended item</li>");//有序列表的开头，即第一个li
  });
});
</script>

<body>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
<ol>
<li>List item 1</li>
<li>List item 2</li>
<li>List item 3</li>
</ol>

<button id="btn1">添加文本</button>
<button id="btn2">添加列表项</button>

</body>

/*
Prepended text. This is a paragraph.

Prepended text. This is another paragraph.

1.Prepended item
2.List item 1
3.List item 2
4.List item 3
*/
```

通过 append() 和 prepend() 方法添加若干新元素

实例：（ 对 prepend() 同样有效）

```js
<script>
    //创建新元素。这些元素可以通过 text/HTML、jQuery 或者 JavaScript/DOM 来创建
function appendText()
{
var txt1="<p>Text.</p>";              // 以 HTML 创建新元素
    
var txt2=$("<p></p>").text("Text.");  // 以 jQuery 创建新元素
    
var txt3=document.createElement("p");
txt3.innerHTML="Text.";               // 通过 DOM 来创建文本
    
$("body").append(txt1,txt2,txt3);        // 追加新元素
}
</script>

<p>This is a paragraph.</p>
<button onclick="appendText()">追加文本</button>
```



### ~ after(之后)

在被选元素之后插入内容

### ~ before(之前)

在被选元素之前插入内容

```js
<script>
$(document).ready(function(){
  $("#btn1").click(function(){
    $("img").before("<b>Before</b>");
  });

  $("#btn2").click(function(){
    $("img").after("<i>After</i>");
  });
});
</script>
<body>
<img src="/i/eg_w3school.gif" alt="W3School Logo" />
<br><br>
<button id="btn1">在图片前面添加文本</button>
<button id="btn2">在图片后面添加文本</button>
</body>
```

通过 after() 和 before() 方法添加若干新元素；创建若干新元素。这些元素可以通过 text/HTML、jQuery 或者 JavaScript/DOM 来创建。 

实例： （对 before() 同样有效） 

```js
<script>
function afterText()
{
var txt1="<b>I </b>";                    // 以 HTML 创建元素
var txt2=$("<i></i>").text("love ");     // 通过 jQuery 创建元素
var txt3=document.createElement("big");  // 通过 DOM 创建元素
txt3.innerHTML="jQuery!";
$("img").after(txt1,txt2,txt3);          // 在 img 之后插入新元素
}
</script>
</head>
<body>

<img src="/i/eg_w3school.gif" alt="W3School Logo" />
<br><br>
<button onclick="afterText()">在图片后面添加文本</button>

</body>
```

## 4、删除元素

### ~ remove

删除所选元素及其子元素

实例：

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#div1").remove();
  });
});
</script>

<body>

<div id="div1" style="height:100px;width:300px;border:1px solid black;background-color:yellow;">
This is some text in the div.
<p>This is a paragraph in the div.</p>
<p>This is another paragraph in the div.</p>
</div>
<br>
<button>删除 div 元素</button>
```



### ~ empty

删除被选元素的子元素

实例：

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#div1").empty();
  });
});
</script>

<body>

<div id="div1" style="height:100px;width:300px;border:1px solid black;background-color:yellow;">
This is some text in the div.
<p>This is a paragraph in the div.</p>
<p>This is another paragraph in the div.</p>
</div>

<br>
<button>清空 div 元素</button>
 //盒子依旧存在，内容被删除
```

### ~ 过滤被删除的元素

jQuery remove() 方法也可接受一个参数，允许您对被删元素进行过滤。该参数可以是**任何 jQuery 选择器**的语法。

实例： 删除 class="italic" 的所有 <p> 元素： 

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("p").remove(".italic");
  });
});
</script>
<body>

<p>This is a paragraph in the div.</p>
<p class="italic"><i>This is another paragraph in the div.</i></p>
<p class="italic"><i>This is another paragraph in the div.</i></p>
<button>删除 class="italic" 的所有 p 元素</button>

</body>
```

## 5、获取并设置CSS类

  [jQuery CSS 操作参考手册](https://www.w3school.com.cn/jquery/jquery_ref_css.asp) 

### ~ addClass

向被选元素添加一个或多个类；

**实例1： 向不同的元素添加 class 属性；添加类时可以选取多个元素：** 

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("h1,h2,p").addClass("blue");//向h1,h2,p添加blue样式
    $("div").addClass("important");//向div添加important样式
  });
});
</script>
<style type="text/css">
.important
{
font-weight:bold;
font-size:xx-large;
}
.blue
{
color:blue;
}
</style>
```

**实例2：也可以在addClass中规定多个类**

```js
$("button").click(function(){
  $("#div1").addClass("important blue");
});
```



### ~ removeClass

从被选元素删除一个或多个类

实例1： 不同的元素中删除指定的 class 属性： 

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("h1,h2,p").removeClass("blue");//去除blue的class属性
  });
});
</script>
<style type="text/css">
.blue
{
color:blue;
}
```



### ~ toggleClass(切换)

对被选元素进行**添加/删除类的切换操作**

实例：

```js
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("h1,h2,p").toggleClass("blue");
  });
});
</script>

<style type="text/css">
.blue
{
color:blue;
}
</style>
```



### ~ CSS

 设置或返回被选元素的一个或多个样式属性。

#### (1)返回CSS属性 

语法：

```js
css("propertyname");
```

实例： 返回**首个匹配**元素的 background-color 值： 

```js
$("p").css("background-color");
```

#### (2)设置CSS属性

语法：

```js
css("propertyname","value");
```

实例： 为**所有匹配元素**设置 background-color 值： 

```js
$("p").css("background-color","yellow");
```

#### (3)设置多个 CSS 属性

语法：

```js
css({"propertyname":"value","propertyname":"value",...});
```

实例： 为所有匹配元素设置 background-color 和 font-size： 

```js
$("p").css({"background-color":"yellow","font-size":"200%"});
```

## 7、尺寸

### ~ width ~ height

- width() 方法设置或返回元素的宽度（不包括内边距、边框或外边距）。
- height() 方法设置或返回元素的高度（不包括内边距、边框或外边距）。

实例1： 返回指定的 <div> 元素的宽度和高度： 

```js
$("button").click(function(){
  var txt="";
  txt+="Width: " + $("#div1").width() + "</br>";
  txt+="Height: " + $("#div1").height();
  $("#div1").html(txt);
});
```

实例2： 设置指定的 <div> 元素的宽度和高度： 

```js
$("button").click(function(){
  $("#div1").width(500).height(500);
});
```

实例3： 返回文档（HTML 文档）和窗口（浏览器视口）的宽度和高度： 

```js
$("button").click(function(){
  var txt="";
    //方法一:
  txt+="Document width/height: " + $(document).width();
  txt+="x" + $(document).height() + "\n";
    //方法二:
  txt+="Window width/height: " + $(window).width();
  txt+="x" + $(window).height();
  alert(txt);
});
```



### ~ innerWidth

### ~ innerHeight

- innerWidth() 方法返回元素的宽度（包括内边距）。
- innerHeight() 方法返回元素的高度（包括内边距）。

实例： 返回指定的 <div> 元素的 inner-width/height 

```js
$("button").click(function(){
  var txt="";
  txt+="Inner width: " + $("#div1").innerWidth() + "</br>";
  txt+="Inner height: " + $("#div1").innerHeight();
  $("#div1").html(txt);
});
```



### ~ outerWidth

### ~ outerHeight

- outerWidth() 方法返回元素的宽度（**包括内边距和边框**）。
- outerHeight() 方法返回元素的高度（**包括内边距和边框**）。

实例： 返回指定的 <div> 元素的 outer-width/height 

```js
$("button").click(function(){
  var txt="";
  txt+="Outer width: " + $("#div1").outerWidth() + "</br>";
  txt+="Outer height: " + $("#div1").outerHeight();
  $("#div1").html(txt);
});
```

- outerWidth(true) 方法返回元素的宽度（**包括内边距、边框和外边距**）。
- outerHeight(true) 方法返回元素的高度（**包括内边距、边框和外边距**）。

实例：

```js
$("button").click(function(){
  var txt="";
  txt+="Outer width (+margin): " + $("#div1").outerWidth(true) + "</br>";
  txt+="Outer height (+margin): " + $("#div1").outerHeight(true);
  $("#div1").html(txt);
});
```

