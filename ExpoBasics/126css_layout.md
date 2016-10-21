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
* 默认为block的元素：< div >, < p >, < h1 > ~ < h6 >, < ul >, < form >

** display:inline **

行级元素

* 默认宽度为内容宽度
* 不可设置宽高
* 同行显示（元素内部可换行）
* 默认为inline的元素：< span >, < a >, < label >, < cite >, < em >

** display:inline-block **

行内块元素

* 默认宽度为内容宽度
* 可设置宽高
* 同行显示
* 整块换行
* 默认为inline-block的元素：input、textarea、select、button、img ···
