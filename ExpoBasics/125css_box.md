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

** Padding **

padding: [< length > | < percentage >]{1,4} | inherit

** Margin **

margin: [< length > | < percentage > | auto]{1,4} | inherit

>NOTE：margin 默认值为 auto



Trick：

/* 可用于水平居中 */ margin: 0 auto;

margin 合并

毗邻元素外间距（margin）会合并，既取相对较大的值。父元素与第一个和最后一个子元素的外间距也可合并。

** Border **

border: [< br-width > || < br-style > || < color >] | inherit

border-width(宽度): [< length > | thin | medium | thick]{1,4} | inherit

border-style(样式): [solid | dashed | dotted | ...]{1,4} |inherit

border-colro(颜色): [< color > | transparent]{1,4} | inherit

>NOTE：border-color 默认为元素字体颜色。

** border-radius **
