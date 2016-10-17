##文本

####字体

font: [< font-style >||< font-variant >||< font-weight >]?< font-size >[/< line-height >]?< font-family >

>font：【斜体+粗体（2选1）】 大小 【/行距】 字体

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
* cursive
* fantasy
* Monospace

font-family: arial, Verdana, sans-serif;

>NOTE：优先使用靠前的字体



加粗字体



font-weight: normal | bold | bolder | lighter | 100 | 200 | 300 | 400 | 500 | 600 | 700 | 800 | 900



font-weight: normal; font-weight: bold;



倾斜字体



font-style: normal | italic | oblique | inherit



italic 使用字体中的斜体，而 oblique 在没有斜体字体时强制倾斜字体。

 �
