**CSS高级技巧**

# 1.元素的显示与隐藏

## 1>display显示

display：none；隐藏且**不保留位置**；

display：block；不仅表示转换为块级元素，还表示显示；

## 2>visibility可见性

visibility：visible；对象可见；

visibility：hidden；对象不可见；**位置保留**；

visibility：inherit；继承上一个父对象的可见性；

visibility：collapse；隐藏表格的行或者列；

## 3>overflow溢出

| 属性值  | 描述                                       |
| ------- | ------------------------------------------ |
| visible | 不剪切内容也不添加滚动条                   |
| hidden  | 不显示超出对象尺寸的内容，超出的部分隐藏掉 |
| scroll  | 不管超出的内容，总显示滚动条               |
| auto    | 超出的自动显示滚动条，不超出不显示         |

# 2.用户界面样式

## 1>鼠标样式cursor

设置或检索对象上移动的鼠标指针采取何种系统预定义的光标形状

| 属性值      | 描述 |
| ----------- | ---- |
| default     | 默认 |
| pointer     | 小手 |
| move        | 移动 |
| text        | 文本 |
| not-allowed | 禁止 |

## 2>outline

绘制在元素周围的一条线，位于边框的外围，起到突出元素的作用；

## 3>防止拖拽文本域

文本域专用：reize：none；

# 3.垂直对齐

vertical-align只针对**行内元素和行内块元素**，实现**图片表单文字**的对齐关系；

vertical-align：baseline；基线；

vertical-align：top；顶线；

vertical-align：middle；中线；

vertical-align：bottom；底线；

# 4.去除图片的底侧空白

1.vertical-align改为top；

2.因为块级元素vertical-align无效，所以将**图片转化为块级元素**；

# 5.溢出文字省略号显示

三部曲：

1. 强制一行显示文本；**先**
2. 超出部分隐藏；   **后**
3. 文字用省略号代替超出部分；

## 1.white-space

white-space：文本显示方式：一般强制一行显示；

white-space：normal；默认处理方式；

white-space：nowrap；强制一行显示所有文本，直到文本结束或者遇到br标签换行；

## 2.text-overflow

处理文本溢出

text-overflow：clip；不显示省略标记，简单裁切；

text-overflow：ellipsis；文本溢出时显示省略标记；

# 6.CSS精灵技术

1>为什么需要精灵技术：为了有效减少服务器接受和发送请求的次数，提高页面加载速度；css精灵技术**针对于背景图片**，不是插入的img；

2>使用背景位置background-position，准确定位大图片中小图片的大小和位置；背景定位基本为负值；

# 7.滑动门

制作网页美观，需要为网页元素设置特殊形状的背景；为了使各种特殊形状的背景能够自然适应文本的多少，出现了CSS滑动门技术，从新的角度构建页面，**使各种形状的背景能够自由拉伸滑动**，以适应元素内部的文本内容，可用性强。常见于导航栏。

**核心技术**

布局：将a转化为行内块，实现文字撑开盒子

```html
<li>
    <a herf="#">
    	<span>导航栏内容</span>//a左侧，span右侧
    </a>
</li>
```

CSS样式：

```css
a{
			display: inline-block;
			height: 33px;
			background: url(image/to.png) no-repeat ;
			margin: 100px;
			padding-left: 15px;
			color: #000;
		}
		a span{
			display: inline-block;
			height: 33px;
			background: url(image/to.png) no-repeat  right top;
			padding-right: 15px;
			
		}
```

a设置背景左侧，padding撑开合适宽度

span设置背景右侧（右对齐），padding撑开合适宽度；剩下由文字撑开；

