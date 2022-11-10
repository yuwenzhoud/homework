# flex布局

块元素：display：flex；

行内元素：display：inline-flex；

# flex-diraction

主轴排列方式

| 属性值         | 描述           |
| -------------- | -------------- |
| row            | 水平，从左到右 |
| row-reverse    | 水平，从右向左 |
| column         | 竖直，从上到下 |
| column-reverse | 竖直，从下到上 |

# flex-wrap

决定容器内项目是否换行

| 属性值       | 描述                                                         |
| ------------ | ------------------------------------------------------------ |
| nowrap       | 不换行，主轴空间固定，空间不足时，项目尺寸随之调整并不会挤到下一行。 |
| wrap         | 项目尺寸超出自动换行，第一行在上。                           |
| wrap-reverse | 换行，第一行在下。                                           |

#  flex-flow

flex-direction属性和flex-wrap属性的简写形式，默认值为row（横向） nowrap（不换行）。 

# justify-content

定义了项目在主轴上的对齐方式

| 属性值        | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| flex-start    | 左对齐。                                                     |
| flex-end      | 右对齐。                                                     |
| center        | 居中。                                                       |
| space-between | 两端对齐，**项目之间的间隔相等，剩余空间等分**               |
| space-around  | **每个项目两侧间隔相等**，所以项目之间间隔比边缘的间隔**大一倍**。 |

# align-items

定义了项目在交叉轴上的对齐方式

| 属性值     | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| flex-start | 交叉轴起点对齐                                               |
| flex-end   | 交叉轴终点对齐                                               |
| center     | 交叉轴中点对齐                                               |
| baseline   | 第一行文字的基线对齐                                         |
| stretch    | 默认值。项目未设置高度或设置为auto，将占满整个容器。容器高为100px，未设定高度时，项目高度也为100px |

# align-content

**定义了多根轴线的对齐方式**，项目只有一根轴线，将不起作用。

当flex-wrap设置为nowrap时，容器仅有一根轴线，项目不会换行，不会产生多条轴线

当你 flex-wrap 设置为 wrap 的时候，容器可能会出现多条轴线，这时候你就需要去设置多条轴线之间的对齐方式了。

| 属性值        | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| flex-start    | 交叉轴起点对齐                                               |
| flex-end      | 交叉轴终点对齐                                               |
| center        | 交叉轴中间对齐                                               |
| space-between | 轴线两端对齐，之间的间隔相等，即剩余空间等分成间隙。         |
| space-around  | 每个轴线两侧的间隔相等，所以轴线之间的间隔比轴线与边缘的间隔大一倍 |
| stretch       | 等分间距分布，不设置盒子大小将等分布满。                     |

# 项目属性

**有六种属性可运用在项目上**

| 属性值      | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| order       | 定义项目在容器中的排列顺序，数值越小，排列越靠前，默认值为0。 |
| flex-basis  | 定义了在分配多余空间之前，项目占据的主轴空间，浏览器根据这个属性，计算主轴是否有多余空间。**默认值：auto，即项目本来的大小, 这时候 item 的宽高取决于 width 或 height 的值** |
| flex-grow   | 定义项目的**放大**比例，默认为0，即如果存在剩余空间，也不放大 |
| flex-shrink | 定义了项目的**缩小**比例，默认值: 1，即如果空间不足，该项目将缩小，负值对该属性无效 |
| flex        | **flex-grow, flex-shrink 和 flex-basis的简写**               |
| align-self  | **允许单个项目有与其他项目不一样的对齐方式**                 |

## 1.order

```css
.item-1 {
			width: 20px;
			height: 20px;
			background-color: skyblue;
			order: 2;
		}
.item-2 {
			width: 20px;
			height: 20px;
			background-color: skyblue;
			order: 1;
		}

<div class="item-2">-2</div>
		<div class="item-1">-1</div>
```

order在越小的，排序越靠前；

## 2.flex-basis

**当主轴为水平方向的时候，当设置了 flex-basis，项目的宽度设置值会失效，flex-basis 需要跟 flex-grow 和 flex-shrink 配合使用才能发挥效果。**

- 当 flex-basis 值为 0 % 时，是把该项目视为零尺寸的，故即使声明该尺寸为 140px，也并没有什么用。
- 当 flex-basis 值为 auto 时，则根据尺寸的设定值(假如为 100px)，则这 100px 不会纳入剩余空间。



## 3.flex-grow

 **定义项目的放大比例** ； 默认值为 0，即如果存在剩余空间，也不放大 

当所有的项目都以 flex-basis 的值进行排列后，**仍有剩余空间**，那么这时候 flex-grow 就会发挥作用了。

如果所有项目的 flex-grow 属性都为 1，则它们将等分剩余空间。(如果有的话)

如果一个项目的 flex-grow 属性为 2，其他项目都为 1，则前者占据的剩余空间将比其他项多一倍。

 当然如果当所有项目**以 flex-basis 的值排列完后发现空间不够了**，且 flex-wrap：nowrap 时，此时 **flex-grow 则不起作用了**，这时候就需要接下来的这个属性。 

## 4.flex-shrink

 **定义了项目的缩小比例** ； 默认值: 1，即如果空间不足，该项目将缩小，负值对该属性无效。 

如果所有项目的 flex-shrink 属性都为 1，当空间不足时，都将等比例缩小。

如果一个项目的 flex-shrink 属性为 0，其他项目都为 1，则空间不足时，前者不缩小。

## 5.flex

flex：flex-grow    flex-shrink   flex-basis；

flex 的默认值是以上三个属性值的组合。假设以上三个属性同样取默认值，则 flex 的默认值是 0 1 auto。

有关快捷值：auto (1 1 auto) 和 none (0 0 auto)

**情况一**

- **当 flex 取值为一个非负数字，则该数字为 flex-grow 值**，flex-shrink 取 1，flex-basis 取 0%，如下是等同的：

```css
.item {flex: 1;}
.item {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 0%;
}
```

- 

```css
.item {flex: 0;}
.item {
    flex-grow: 0;
    flex-shrink: 1;
    flex-basis: 0%;
}
```



**情况二**

**当 flex 取值为一个长度或百分比，则视为 flex-basis 值**，flex-grow 取 1，flex-shrink 取 1，有如下等同情况（注意 0% 是一个百分比而不是一个非负数字）

```css
.item-1 {flex: 0%;}
.item-1 {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 0%;
}

.item-2 {flex: 24px;}
.item-2 {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 24px;
}
```



**情况三**

**当 flex 取值为两个非负数字，则分别视为 flex-grow 和 flex-shrink 的值，**flex-basis 取 0%，如下是等同的：



```css
.item {flex: 2 3;}
.item {
    flex-grow: 2;
    flex-shrink: 3;
    flex-basis: 0%;
}
```





**情况四**

**当 flex 取值为一个非负数字和一个长度或百分比，则分别视为 flex-grow 和 flex-basis 的值**，flex-shrink 取 1，如下是等同的：

```css
.item {flex: 11 32px;}
.item {
    flex-grow: 11;
    flex-shrink: 1;
    flex-basis: 32px;
}
```



## 注意

1. 当 flex-wrap 为 wrap | wrap-reverse，且[子项宽度](https://www.zhihu.com/search?q=子项宽度&search_source=Entity&hybrid_search_source=Entity&hybrid_search_extra={"sourceType"%3A"article"%2C"sourceId"%3A25303493})和不及父容器宽度时，flex-grow 会起作用，子项会根据 flex-grow 设定的值放大（为0的项不放大）
2. 当 flex-wrap 为 wrap | wrap-reverse，且子项宽度和超过父容器宽度时，首先一定会换行，换行后，每一行的右端都可能会有剩余空间（最后一行包含的子项可能比前几行少，所以剩余空间可能会更大），这时 flex-grow 会起作用，若当前行所有子项的 flex-grow 都为0，则剩余空间保留，若当前行存在一个子项的 flex-grow 不为0，则剩余空间会被 flex-grow 不为0的子项占据
3. 当 flex-wrap 为 nowrap，且子项宽度和不及父容器宽度时，flex-grow 会起作用，子项会根据 flex-grow 设定的值放大（为0的项不放大）
4. 当 flex-wrap 为 nowrap，且子项宽度和超过父容器宽度时，flex-shrink 会起作用，子项会根据 flex-shrink 设定的值进行缩小（为0的项不缩小）。但这里有一个较为特殊情况，就是当这一行所有子项 flex-shrink 都为0时，也就是说所有的子项都不能缩小，就会出现讨厌的横向滚动条
5. 总结上面四点，可以看出不管在什么情况下，在同一时间，flex-shrink 和 flex-grow 只有一个能起作用，这其中的道理细想起来也很浅显：空间足够时，flex-grow 就有发挥的余地，而空间不足时，flex-shrink 就能起作用。当然，flex-wrap 的值为 wrap | wrap-reverse 时，表明可以换行，既然可以换行，一般情况下空间就总是足够的，flex-shrink 当然就不会起作用。



## 6.align-self

 **允许单个项目有与其他项目不一样的对齐方式** ；

单个项目覆盖 align-items 定义的属性

默认值为 auto，表示继承父元素的 align-items 属性，如果没有父元素，则等同于 stretch。

| 属性值     | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| auto       | 表示继承父元素的 align-items 属性，如果没有父元素，则等同于 stretch。 |
| flex-start | 交叉轴起点对齐                                               |
| flex-end   | 交叉轴终点对齐                                               |
| center     | 交叉轴中点对齐                                               |
| baseline   | 第一行文字的基线对齐                                         |
| strech     | 默认值。项目未设置高度或设置为auto，将占满整个容器。容器高为100px，未设定高度时，项目高度也为100px |

这个跟 align-items 属性时一样的，只不过 align-self 是对单个项目生效的，而 align-items 则是对容器下的所有项目生效的。