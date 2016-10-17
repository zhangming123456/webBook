##文本

####字体

font: [< font-style >||< font-variant >||< font-weight >]?< font-size >[/< line-height >]?< font-family >

>font：【斜体+粗体（2选1）】 大小 【/行距】 字体

》NOTE：当其他值为空时，均被设置为默认值。


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

