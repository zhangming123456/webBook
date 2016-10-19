#背景

##背景CSS2相关的属性 

background: [< background-color > || < background-image > || < background-repeat > || < background-position >]{1,4};

** 背景颜色 **

background-color: < color >;

** 背景图片 **

background-image: < bg-image >[, < bg-image >]*;

>NOTE：当background-color 与 background-image 共存时，背景颜色永远在最底层（于背景图片之下）。

** 背景是否平铺 **

background-repeat: < repeat-style >[, < repeat-style ]*;

< repeat-style > = repeat-x | repeat-y | [repeat | space | round | no-repeat]{1,2};

* no-repeat:不平铺

* repeat-x：在水平方向上平铺

* repeat-y:在垂直方向上平铺

* repeat:平铺

** 背景图片的位置 **