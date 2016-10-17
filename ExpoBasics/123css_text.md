##文本

####字体

font: [< font-style >||< font-variant >||< font-weight >]?< font-size >[/< line-height >]?[<'font-family'>]#

>font：【斜体+粗体(2选1)】 大小 【/行距】 字体(1~n个用，分隔)

** 改变字号 **

font-size: < absolute-size > | < relative-size > | < length > | < percentage > | inherit

* < absolute-size > 有 small large medium
* < relative-size > 有 smaller larger

    例：font-size 12px
    font-size 16px
    font-size 2em
    font-size 200%



NOTE：以上两值在开发中并不常用。2em 与 200% 都为父元素默认大小的两倍（参照物为父元素的字体大小 12px）。
