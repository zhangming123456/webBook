#文本

##字体

font:[ [< font-style > || <'font-variant'> || < font-weight > || <'font-stretch'> ]? < font-size > [/< line-height >]? < font-family > ] | caption | icon | menu | message-box | small-caption | status-bar

>font：【斜体 粗体】 大小 【/行距】 字体

>NOTE：当其他值为空时，均被设置为默认值。


** 改变字号 **

font-size: < absolute-size > | < relative-size > | < length > | < percentage > | inherit

* absolute-size（决定大小）：small（大）large（中） medium（小）
* relative-size（相对大小）：smaller（更小） larger（更大）
* length:px em
* percentage（百分比）:%
* inherit:继承

NOTE：以上两值在开发中并不常用。2em 与 200% 都为父元素默认大小的两倍（参照物为父元素的字体大小 12px）。

** 改变字体**

font-family: [ < family-name > | < generic-family > ]#

< generic-family > 可选选项，但具体使用字体由浏览器决定

* serif 衬线体
* sans-serif 灯芯体(无衬线字体)
* cursive 草书
* fantasy 幻体
* Monospace 等宽字体

例：font-family: "宋体", arial, Verdana, sans-serif;

>NOTE：优先使用靠前的字体

** 加粗字体 **

font-weight: normal（正常） | bold（粗体） | bolder（更粗） | lighter | 100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900

例：font-weight: normal; font-weight: bold;

** 倾斜字体 **

font-style: normal | italic | oblique | inherit

italic 使用字体中的斜体，而 oblique 在没有斜体字体时强制倾斜字体。

** 更改行距（高） **

line-height: normal | < number > | < length > | < percentage >

normal 值为浏览器决定，在1.1至1.2之间（通常设置值为1.14左右）

* length 类型:line-height: 40px; line-height: 3em; 
* percentage 类型：line-height: 300%;
* number 类型：line-height: 3;

>NOTE：当line-height为 number 类型时，子类直接继承其数值（不计算直接继承）。 而当为percentage 类型时，子类则会先计算再显示（先计算后继承）。

** 字间距（字母间距）**

letter-spacing: normal | < length >

>用于设置字间距或者字母间距，此属性适用于中文或西文中的字母。 

word-spacing: normal | < length >

>用于设置西文中词与词的间距或标签直接的距离则需要使用 word-spacing。

** 改变文字颜色 **

color: < color > | inherit

| 值 | 描述 |
| :--- | :--- |
| color_name | 规定颜色值为颜色名称的颜色（比如 red）。 |
| hex_number | 规定颜色值为十六进制值的颜色（比如 #ff0000）。 |
| rgb_number | 规定颜色值为 rgb 代码的颜色（比如 rgb(255,0,0)）。|
| rgba_number | 与 rgb 相同，a 代表透明度（比如rgba(255,230,230,0.5)。 |
| inherit | 规定应该从父元素继承颜色。 |

##对齐方式

** 文字居中 **

text-align: start | end | left（左） | right（右） | center（居中） | justify（两端） | match-parent | start end | inherit

>NOTE：默认为文本左对齐。

** 文本垂直对齐 **

vertical-align: baseline | sub | super | text-top | text-bottom | middle | top | bottom | < percentage > | < length >

| 值 | 描述 
| :--- | :--- |
| baseline | 默认。元素放置在父元素的基线上。
| sub | 垂直对齐文本的下标。
| super |垂直对齐文本的上标
| top | 把元素的顶端与行中最高元素的顶端对齐
| text-top | 把元素的顶端与父元素字体的顶端对齐
| middle | 把此元素放置在父元素的中部。
| bottom | 把元素的顶端与行中最低的元素的顶端对齐。 
| text-bottom | 把元素的底端与父元素字体的底端对齐。|
| length | px em |
| parcentage | % 使用 "line-height" 属性的百分比值来排列此元素。允许使用负值。|
| inherit | 规定应该从父元素继承 vertical-align 属性的值。

>NOTE：< percentage >的参照物为line-height

** 文本缩进 **

text-indent: < length > | < percentage > && [ hanging || each-line ]

>NOTE：缩进两个字可使用 text-indent: 2em;


##格式处理

** 保留空格格式 **

white-space: normal | pre | nowrap | pre-wrap | pre-line

pre 行为同 < pre > 一致。

| 值 | 描述 | New lines | Spaces and tabs | Text wrapping| 
| :--- | :--- | :--- | :--- | :--- |
| normal | 默认。空白会被浏览器忽略。 |  Collapse | Collapse | Wrap |
| pre | 空白会被浏览器保留。其行为方式类似HTML 中的< pre > 标签。 | Preserve | Preserve | No Wrap |
| nowrap | 文本不会换行，文本会在在同一行上继续，直到遇到 <br> 标签为止。 | Collapse | Collapse | No Wrap |
| pre-wrap | 保留空白符序列，但是正常地进行换行。 | Preserve | Preserve | Wrap |
| pre-line | 合并空白符序列，但是保留换行符。 | Preserve | Collapse | Wrap |
| inherit | 规定应该从父元素继承 white-space 属性的值。 |  |  |  |

>NOTE: New lines：换行，Spaces and tabs：空格，Text wrapping：自动换行，Preseve：保留格式，Collapse：不保留，Wrap：换行。

