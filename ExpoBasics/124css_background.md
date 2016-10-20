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

>等同效果
>* background-position: 50% 50%; == center center; 
* background-position: 0 0; == left top;
* background-position: 100% 100%; == right bottom;

>四个值时方向只为参照物 
* background-position: right 10px top 20px;

![](/image/20161220bapo.png)

** Sprite(精灵图) 的使用 **

    background-image: url(sprite.png)
    background-repeat: no-repeat;
    background-positon: 0 -100px

或

    background: url(sprite.png) no-repeat 0 -100px;

使用位置为负值将图片偏移使需要的图片位置上移并显示正确的图案。

###不常用属性

** background-attachment **

background-attachment: < attachment >[, < attachment >]*;

< attachment > = scroll | fixed | local;

作用：设置背景图像是否固定或者随着页面的其余部分滚动 

* scroll：背景图片随页面的其余部分滚动。这是默认
* fixed：背景图像是固定的
* inherit：指定background-attachment的设置应该从父元素继承

>注意： Internet Explorer 8和更早版本的浏览器不支持多个背景图像在一个元素.

##CSS3背景属性

** linear-gradient（线性渐变） **

background: linear-gradient(); 

linear-gradient([ [< angle > | to < side-or-corner >],]? < color-step >[, < color-stop >]+ 

< side-or-corner > = [left | right] || [top | bottom]
< color-stop > = < color > [< percentage > | < length >]?)

![](/image/2016balg.png)

* 重复的线性渐变

repeating-linear-gradient() 函数用于重复线性渐变：

![](/image/2016barli.png)

** radial-gradient（径向渐变）**

![](/image/2016barg.jpg)

radial-gradient( [ circle || < length > ] [ at < position > ]? , | [ ellipse || [< length > | < percentage > ]{2}] [ at < position > ]? , | [ [ circle | ellipse ] || < extent-keyword > ] [ at < position > ]? , | at < position > , < color-stop > [ , < color-stop > ]+ )

< extent-keyword > = closest-corner | closest-side | farthest-corner | farthest-side

< color-stop > = < color > [ < percentage > | < length > ]?

![](/image/2016barg01.png)
![](/image/2016barg02.png)

* 重复的径向渐变

repeating-radial-gradient() 函数用于重复径向渐变：

![](/image/2016barre.png)

** background-Origin **

作用：属性指定background-position属性应该是相对位置。

>注意：如果背景图像background-attachment是"固定"，这个属性没有任何效果。

background-origin: padding-box|border-box|content-box; 

* padding-box：背景图像填充框的相对位置
* border-box：背景图像边界框的相对位置
* content-box：背景图像的相对位置的内容框

![](/image/2016orbox.png)

** background-clip **

作用：属性指定背景绘制区域

background-clip: border-box|padding-box|content-box; 

* border-box默认值。背景绘制在边框方框内（剪切成边框方框）。
* padding-box背景绘制在衬距方框内（剪切成衬距方框）。
* content-box背景绘制在内容方框内（剪切成内容方框）。

![](/image/2016baclip.png)

** background-size **
