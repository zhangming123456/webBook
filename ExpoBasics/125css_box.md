#盒模型

盒子模型是网页布局的基石。它有边框、外边距、内边距、内容组成。

![](/image/2016box01.png)

** 盒子 3D 模型 **

盒子由上到下依次分为五层，它们自上而下的顺序是。

* border 边框

* content + padding 内容与内边距

* background-image 背景图片

* background-color 背景颜色

* margin 外边距

###属性

** 内容盒子宽 **

width：< length > | < percentage > | auto | inherit

>NOTE：通常情况下百分比得参照物为元素的父元素。max-width 与 min-width 可以设置最大与最小宽度。

** 内容盒子高 **

height：< length > | < percentage > | auto | inherit

>NOTE：默认情况元素的高度为内容高度。max-height 与 min-height 可以设置最大与最小高度。

** Padding(内边距/填充) **

padding: [< length > | < percentage >]{1,4} | inherit

** Margin **

margin(外边距): [< length > | < percentage > | auto]{1,4} | inherit

>NOTE：margin 默认值为 auto



Trick：

/* 可用于水平居中 */ margin: 0 auto;

margin 合并

毗邻元素外间距（margin）会合并，既取相对较大的值。父元素与第一个和最后一个子元素的外间距也可合并。

** Border(边框) **

border: [< br-width > || < br-style > || < color >] | inherit

border-width(宽度): [< length > | thin | medium | thick]{1,4} | inherit

border-style(样式): [solid | dashed | dotted | ...]{1,4} |inherit

border-colro(颜色): [< color > | transparent]{1,4} | inherit

>NOTE：border-color 默认为元素字体颜色。

** Overflow **

作用：属性指定如果内容溢出一个元素的框，会发生什么。

overflow: visible | hidden | scroll | auto

* visible默认值。内容不会被修剪，会呈现在元素框之外。
* hidden内容会被修剪，并且其余内容是不可见的。
* scroll内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。
* auto如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。
* inherit规定应该从父元素继承 overflow 属性的值。

>NOTE：默认属性为 visible。使用 overflow-x 与 overflow-y 单独的设置水平和垂直方向的滚动条。

##css3相关属性

** border-radius(边框圆角) **

border-radius: [ < length > | < percentage > ]{1,4} [ / [ < length > | < percentage > ]{1,4} ]?/\* 水平半径/垂直半径 \*/

>NOTE：四个角的分解属性由左上角顺时针附值。

** box-sizing **

![](/image/2016box02.png)

作用：允许你以某种方式定义某些元素，以适应指定区域。

box-sizing: content-box | border-box | inherit

* content-box = 内容盒子宽高 + 填充（Padding）+ 边框宽（border-width）
* border-box = 内容盒子宽高

** box-shadow **

作用：向框添加一个或多个阴影

box-shadown: none | [inset? && [ < offset-x > < offset-y > < blur-radius >? < spread-radius >? < color >? ] ]#

![](/image/2016box03.png)

![](/image/2016box04.png)

>NOTE：水平与垂直偏移可以为负值即相反方向偏移。颜色默认为文字颜色。阴影不占据空间，仅为修饰效果。

** Outline **

作用：outline（轮廓）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。

>outline简写属性在一个声明中设置所有的轮廓属性。
可以设置的属性分别是（按顺序）：outline-color, outline-style, outline-width

outline: [ <'outline-color'> || <'outline-style'> || <'outline-width'> ]

outline-width: < length > | thin | medium | thick | inherit

* thin规定细轮廓。
* medium默认。规定中等的轮廓。
* thick规定粗的轮廓。
* length允许您规定轮廓粗细的值。

outline-style: solid | dashed | dotted | ... | inherit

* none默认。定义无轮廓。
* dotted定义点状的轮廓。
* dashed定义虚线轮廓。
* solid定义实线轮廓。
* double定义双线轮廓。双线的宽度等同于 outline-width 的值。
* groove定义 3D 凹槽轮廓。此效果取决于 outline-color 值。
* ridge定义 3D 凸槽轮廓。此效果取决于 outline-color 值。
* inset定义 3D 凹边轮廓。此效果取决于 outline-color 值。
* outset定义 3D 凸边轮廓。此效果取决于 outline-color 值。


outline-color: < color > | invert | inherit

* invert:默认。执行颜色反转（逆向的颜色）。可使轮廓在不同的背景颜色中都是可见。

>NOTE：outline 与 border 相似但无法分别设置四个方向的属性。outline 并不占据空间，而 border占据空间，且显示位于 border 以外。

###TRBL

![](/image/2016box05.png)

TRBL (Top, Right, Bottom, Left) 即为顺时针从顶部开始。具有四个方向的属性都可以通过 \*-top \*-right \*-bottom 与 \*-left 单独对其进行设置。

