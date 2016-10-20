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

* space 平铺并在水平和垂直留有空隙，空隙的大小为图片均匀分布后完整覆盖显示区域的宽高

* round 不留空隙平铺且覆盖显示区域，图标会被缩放以达到覆盖效果（缩放不一定等比）

** 背景图片的位置 **

background-position: < position >[, < position >]*;

< position > = [left | center | right | top | bottom |< percentage > | < length > ] | 【left | center | right | top | bottom | < percentage > | < length >】 【left | center | right | top | bottom | < percentage > | < length >] | [center | [left | right] [< percentage > | < length >】? ] && [center | [left | right][< percentage > | < length >]? ]

###不常用属性

** background-attachment **

background-attachment: < attachment >[, < attachment >]*;

< attachment > = scroll | fixed | local;

作用：设置背景图像是否固定或者随着页面的其余部分滚动 

* scroll背景图片随页面的其余部分滚动。这是默认
* fixed背景图像是固定的
* inherit指定background-attachment的设置应该从父元素继承


