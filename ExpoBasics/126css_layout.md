#布局

学习布局前须知道 CSS 中的定位机制。

* 标准文档流（Normal Flow）
* 浮动（Float）
* 绝对定位（Absolute Positioning)
	
标准文档流，从上到下，从左到右的输出文档内容。它由块级（block）元素和行级元素组成，且它们都是盒子模型。

下面为 Firefox 布局可视化 Gecko Reflow Visualisation，布局是指浏览器将元素以正确的大小摆放在正确的位置上。

![](http://wiki.jikexueyuan.com/project/fend_note/images/G/gecko-reflow-visualisation.gif)

##display(元素显示类型)

设置元素的显示方式

| display | 默认宽度 | 可设置宽高 | 起始位置 |
| :-----: | :-----: | :-------: | :-----: |
| block   | 父元素宽度 | 是 | 换行 |
| inline  | 内容宽度 | 否 | 同行 |
| inline-block | 内容宽度 | 是 | 同行 |

** display:block **

块级元素

* 默认宽高为父元素宽高
* 可设置宽高
* 换行显示
* 默认为block的元素：div、p、h1~h6、ul、li、ol、form、···

** display:inline **

行级元素

* 默认宽度为内容宽度
* 不可设置宽高
* 同行显示（元素内部可换行）
* 默认为inline的元素：span、a、label、cite 、em、···

** display:inline-block **

行内块元素

* 默认宽度为内容宽度
* 可设置宽高
* 同行显示
* 整块换行
* 默认为inline-block的元素：input、textarea、select、button、img、···

** display:none **

* 设置元素不显示

display:none 与 visibility:hidden 的区别为 display:none 不显示且不占位，但 visibility:hidden不显示但占位。

##Position

position 用于设置定位的方式与top right bottom left z-index 则用于设置参照物位置（必须配合定位一同使用）。

四种定位形式

* 静态定位（static）
* 相对定位（relative）
* 绝对定位（absolute）
* 固定定位（fixed）

position: static | relative | absolute | fixed

>默认值为 static

** position:relative **

* 相对定位的元素仍在文档流之中，并按照文档流中的顺序进行排列。
* 参照物为元素本身的位置。
	
>NOTE：最常用的目的为改变元素层级和设置为绝对定位的参照物。

![](/image/position-relative.png)

** position:absolute **

建立以包含块为基准的定位，其随即拥有偏移属性和 z-index 属性。

* 默认宽度为内容宽度,转化为了行内块元素
* 脱离文档流
* 参照物为第一个定位祖先或根元素（< html > 元素）
    * 当给一个单独的元素设置绝对定位，以浏览器左上角（body）为基准设置定位的。
    * 当盒子发生嵌套关系的时候，如果父盒子没有设置定位，子盒子设置定位以浏览器左上角为基准设置定位。
    * 当盒子发生嵌套关系的时候，如果父盒子设置定位，子盒子设置定位父盒子左上角为基准设置定位。

![](/image/position-absolute.png)

** position:fixed(固定定位) **

* 默认宽度为内容宽度
* 脱离文档流
* 参照物为视窗
	
>NOTE：宽高的100%的参照依然为视窗（例：网页遮罩效果）；Fixed 定位在 IE7 和 IE8 下需要描述 !DOCTYPE 才能支持. 

** top/right/bottom/left **

![](/assets/layout-position.png)

其用于设置元素边缘与参照物边缘的距离，且设置的值可为负值。在同时设置相对方向时，元素将被拉伸。

** z-index **

其用于设置 Z 轴上得排序，默认值为 0 但可设置为负值。（如不做设置，则按照文档流的顺序排列。后面的元素将置于前面的元素之上）

![](/assets/layouy-position-zindex.png)

_z-index 栈_

父类容器的 z-index 优于子类 z-index 如图

![](/assets/layout-position-zindex-stack.jpg)

##float

CSS 中规定的定位机制，其可实现块级元素同行显示并存在于文档流之中。浮动仅仅影响文档流中下一个紧邻的元素。

float: left | right | none | inherit

* 默认宽度为内容宽度,浮动可以行内元素转化为行内块元素
* 脱离文档流（会被父元素边界阻挡与position脱离文档流的方式不同）
* 指的方向一直移动

作用：

* 浮动用来解决文字图片环绕问题
* 制作导航栏
* 网页布局

![](/assets/float-right.png)

* **float 元素在同一文档流中**，当同时进行 float 时它们会按照文档流中的顺序排列。(当所有父元素中的所有元素脱离文档流之后，父元素将失去原有默认的内容高度)



>注意：float 元素是半脱离文档流的，对元素是脱离文档流，但对于内容则是在文档流之中的（既元素重叠但内容不重叠）。