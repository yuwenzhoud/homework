# 1.书写方法

1.写在HTML里面

JavaScript的语句，其中text表示文本类型为text，JavaScript是为了告诉浏览器里面的文本属于JavaScript语言。

```javascript
<script type="text/javascript">
        document.write("开启JS之旅!");
</script>
```

2.独立（引用JS外部文件 ）

在js文件中，不需要写script，直接写js代码就行。

js文件的引入：

```javascript
<script src="script.js"></script>
```

# 2.JS在页面中的位置

 我们可以将JavaScript代码放在html文件中**任何位置**，但是我们一般放在网页的head或者body部分。
**放在head部分**
最常用的方式是在页面中head部分放置<script>元素，浏览器解析head部分就会执行这个代码，然后才解析页面的其余部分。
**放在body部分**
JavaScript代码在网页读取到该语句的时候就会执行。 



 比如进行**页面显示初始化的js**必须**放在head里面**，因为初始化都要求提前进行（如给页面body设置css等）；而如果是通过事件调用执行的function那么对位置没什么要求的。 

# 3.认识语句和符号

每一句要被执行的语句后面都要写分号（；）；英文状态输入；

JS的符号和语句都要在英文状态下输入；

# 4.注释

**单行注释**：//；

**多行注释**：/*    */；

 此外，由于历史上 JavaScript 可以兼容 HTML 代码的注释，所以<!--和-->也被视为合法的**单行**注释。

 需要注意的是，`-->`只有**在行首**，才会被当成单行注释，否则会当作正常的运算。  

# 5.变量

变量的定义：关键字var；

 如果变量赋值的时候，忘了写`var`命令，这条语句也是有效的。 

```javascript
var a =1;
// 基本等同
a =1;
```

 可以在同一条`var`命令中声明多个变量。 

```javascript
var a, b;
```

 JavaScript 是一种动态类型语言，也就是说，变量的类型没有限制，变量可以随时更改类型 。即对a的赋值是可以无限次进行的；

```javascript
var x =1;
a = 'hello';
```

变量只能声明一次；第二次声明是无效的；如果第二次声明且赋值，则第二次会覆盖第一次的声明；

```javascript
var x =1;
var x;
x =2;
```

**变量名可以任意取名，但要遵循命名规则:**

  1.变量必须使用字母、下划线(_)或者美元符($**)开始**。

  2.然后可以使用任意多个英文字母、数字、下划线(_)或者美元符($)组成。

  3.不能使用JavaScript关键词与JavaScript保留字。

```
JavaScript 有一些保留字，不能用作标识符：arguments、break、case、catch、class、const、continue、debugger、default、delete、do、else、enum、eval、export、extends、false、finally、for、function、if、implements、import、in、instanceof、interface、let、new、null、package、private、protected、public、return、static、super、switch、this、throw、true、try、typeof、var、void、while、with、yield。
```

**变量要先声明再赋值：**

```javascript
var mychar;
mychar="javascript";
var mynum = 6;
```

变量可以重复赋值，后面的会覆盖掉前面的：

```javascript
var mychar;
mychar="javascript";
mychar="hello";
```

1. 在JS中**区分大小写**，如变量mychar与myChar是不一样的，表示是两个变量。

2. 变量需要**先声明，后使用。**

3. **变量提升**

   JavaScript 引擎的工作方式是，先解析代码，获取所有被声明的变量，然后再一行一行地运行。这造成的结果，就是所有的变量的声明语句，都会被提升到代码的头部，这就叫做变量提升（hoisting）。

   

# 6.标识符

 标识符（identifier）指的是用来识别各种值的合法名称。**最常见的标识符就是变量名**，以及后面要提到的函数名。JavaScript 语言的标识符对大小写敏感，所以`a`和`A`是两个不同的标识 。

 **中文是合法的标识符，可以用作变量名。**

```
JavaScript 有一些保留字，不能用作标识符：arguments、break、case、catch、class、const、continue、debugger、default、delete、do、else、enum、eval、export、extends、false、finally、for、function、if、implements、import、in、instanceof、interface、let、new、null、package、private、protected、public、return、static、super、switch、this、throw、true、try、typeof、var、void、while、with、yield。
```

#  7.区块

 JavaScript 使用大括号，将多个相关的语句组合在一起，称为“区块”（block）。 

 对于`var`命令来说，JavaScript 的区块不构成单独的作用域（scope）。 

```
{
var a =1;
}
a // 1
```

区块内部定义变量a，区块外部变量a依然有效；



# 8.通过ID获取元素

语法： document.getElementById("id") 

```html
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>document.getElementById</title>
</head>
<body>
<p id="con">JavaScript</p>
<script type="text/javascript">
  var mychar=document.getElementById("con")
  document.write("结果:"+mychar); //输出获取的P标签。 
</script>
</body>
</html>
```

# 9.innerHTML 属性

innerHTML 属性用于**获取或替换 HTML 元素的内容**。

语法：Object.innerHTML

**注意**

1.Object是获取的**元素对象**，如通过document.getElementById("ID")获取的元素。

2.注意书写，innerHTML区分大小写。

例如：

<!DOCTYPE HTML>
    <html>
        <head>
            <title>innerHTML</title>
        </head>
        <body>
            <p id="con">
                hello world!
            </p>
            <script>
                var mycon=document.getElementById("con");
                document.write("p标签原来的内容："+mycon.innerHTML+"<br>");
                mycon.innerHTML="New text!";
                document.write("p标签修改后的内容："+mycon.innerHTML);
            </script>
        </body>
</html>
</!doctype>

# 10.改变HTML样式

语法：Object.style.property=new style;

object为获取的元素对象；

基本属性表：

| 属性            | 描述     |
| --------------- | -------- |
| backgroundColor | 背景颜色 |
| height          | 高度     |
| width           | 宽度     |
| color           | 字体颜色 |
| font            | 字体     |
| fontFamily      | 字体样式 |
| fontSize        | 字体大小 |

# 11.显示与隐藏（display）

语法：Object.style.display = value；

value的取值：none：该元素不会被显示；

​						block：此元素会被显示为块级元素；

```javascript
<!DOCTYPE html>
<html lang="zh-cn">
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>显示与隐藏</title>
	<script type="text/javascript">
		function hidetext()
		{
			var mychar=document.getElementById("con");
			mychar.style.display="none";
		}
		function showtext()
		{
			var mychar=document.getElementById("con");
			mychar.style.display="block";
		}
	</script>
</head>
<body>
	<h1>JavaScript</h1>
	<p id="con">
		作为一名Web工程师来说，如果你想提供漂亮的网页、令用户满意的上网体验，JavaScript将是必不可少的工具。
	</p>
	<form>
		<input type="button" onclick="hidetext()" value="不显示段落内容"/>
		<input type="button" onclick="showtext()" value="显示段落内容">
	</form>
</body>
</html>
```

# 12.控制类名

语法：object.className = classname；

```javascript
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb2312">
<title>className属性</title>
<style>
    body{ font-size:16px;}
    .one{
		border:1px solid #eee;
		width:230px;
		height:50px;
		background:#ccc;
		color:red;
    }
	.two{
		border:1px solid #ccc;
		width:230px;
		height:50px;
		background:#9CF;
		color:blue;
	}
	</style>
</head>
<body>
    <p id="p1" > JavaScript使网页显示动态效果并实现与用户交互功能。</p>
    <input type="button" value="添加样式" onclick="add()"/>
	<p id="p2" class="one">JavaScript使网页显示动态效果并实现与用户交互功能。</p>
    <input type="button" value="更改外观" onclick="modify()"/>

	<script type="text/javascript">
	   function add(){
	      var p1 = document.getElementById("p1");
	      p1.className="one";
	   }
	   function modify(){
	      var p2 = document.getElementById("p2");
	      p2.className="two";
	   }
	</script>
</body>
</html>
```

p1.className="one"；意思为给id名为p1的标签添加类标签one的CSS样式；