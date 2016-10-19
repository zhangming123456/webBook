## HTML结构

HTML:(HyperText Markup Language)超文本标记语言。

#### 固定结构
     <html> 
        <head>
            <title></title>
        </head>
        <body>
        </body>
    </html>

>注意：现在这个阶段所有的内容都写在body标签之内。

![](/image/html-overview.png)

HTML与XHTML包括的文档类型

>html：三种

>xhtml: 三种(html升级版本)是一种相对html语法更加严谨的html;

>| 文档类型 | 分类 | 备注 |
| :------ | :---------------------- | :--------------------|
| HTML | HTML Strict DTD | 请求比较严格的html类型 |
|  | HTML Transitional DTD | 相对而言比较规范不太严禁 |
|  | Frameset DTD | 框架级的类型 |
| XHTML | HTML Strict DTD | 请求比较严格的html类型 |
|  | HTML Transitional DTD | 相对而言比较规范不太严禁 |
|  | Frameset DTD | 框架级的类型 |
| HTML5 |  | 无 |

| 元素 | 说明 | 备注 |
| :---- | :----- |
| DOCTYPE(document type):文档类型 | 告知浏览器文档使用哪种 HTML 或 XHTML 规范 |注意：每个页面都必须设置一个doctype，如果不设置，浏览器会默认开启quirks mode（怪异模式）解析（quirks mode是浏览器为了兼容很早之前针对旧版本浏览器设计、并未严格遵循 W3C 标准的网页而产生的一种页面渲染模式）|
| html | 表示文档中HTML部分的开始 |  属性：lang（用来设置页面的语言）|
| | |a.搜索引擎利用它能够告诉用户采用哪一种语言编写文档。|
| | |b.用于特殊设备上的设置（屏幕阅读器利用它能够以不同的语言进行阅读）。|
| head | 用于定义文档的头部，它是所以头部元素的容器 | 可以存放：`<base>, <link>, <meta>, <script>, <style>, 以及 <title>`
| | | 注意： `<title>` 定义文档的标题，它是 head 部分中唯一必需具备的元素 |
| body | 定义文档的主体| 包含文档的所有内容（比如文本、超链接、图像、表格和列表等等。） |
| title | 定义文档的标题。| 注意:title中的文本在SEO中占有很大的权重。 |
| meta标签（元信息）| 提供关于文档的信息 | 注意：meta中设置的所有的内容在页面都不会显示，一个页面上的meta标签可以有多个，但是最好不要超过10个。|
| link | 定义与外部资源（通常是样式表或网站图标）的关系 | |
| script | 定义脚本程序，可以是文档内嵌的也可以是外部文件中的 | |
| noscript | 禁止脚本或不支持脚本显示的内容 | |
| style | 定义css样式 | 无 |

meta的用法：
>1. Description：可以描述页面，可以用来使用百度程序（网络爬虫）来收录关键信息，以此提高页面的排名。

>2. Keywords：关键词，可以用来提高页。面的关健词的比重（前升排名的一种方式。）

>3. 字符集（编码格式）：`<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">`

>>Charset（字符集的格式）：

>>>UTF-8:国际通用字符集

>>>gb2312:亚洲国家使用字符集

** gb2312,utf-8之间的区别：**

相同点：都是字符的编码格式(字库)。

区别：

    Utf-8:收录是全世界所有的语言中的文字。

    Gb2312:收录了汉字，片假名。

大小：

    Utf-8>gb2312

性能：

    Uft-8<gb2312

>约定：将来我们在整个学习过程中都用utf-8;

>Utf-8存储一个汉字占3个字节，

>Gbk存储一个汉字点占2个字节

>Gb2312-->国标（国际标准）2312

>GBK-->国标扩（国际标准的扩展）


** 注意事项：**

- `<!DOCTYPE html>` 必须首行定格

- `<title>` 为文档标题

- `<meta charset="utf-8">` 文档解码格式

- `<meta name="keywords" content="...">` 和 `<meta name="description" content="...">` 提供给搜索引擎使用

- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` 移动端浏览器的宽高与缩放

- `<link>` 标签可以引入 favicon 和样式表 CSS 文件

***
## HTML 语法
![](/image/html-syntax.png)

** 书写规范 **

- 小写标签和属性

- 属性值双引号

- 代码因嵌套缩进


** 全局属性 **

- id, `<div id='unique-element'></div>`，页面中唯一

- class，`<button class='btn'>Click Me</button>`，页面中可重复出现

- style，尽量避免

- title，对于元素的描述类似于 Tooltip 的效果。

***
## HTML标签

#### 文档章节

`<body>` 页面内容

`<header>` 文档头部

`<nav>` 导航

`<aside>` 侧边栏

`<article>` 定义外部内容（如外部引用的文章）

`<section>` 一个独立的块

`<footer>` 尾部

**页面通常结构**

![](/image/structure.gif)

#### 常见标签

- `<div>` 块标签

- `<p>` 段落标签（Paeagraph)

- `<ol>` 有序列表

- `<ul>` 无序列表

- `<dl>` 自定义列表

- `<li>` 配合ol、ul、dl使用

- `<h1>~<h6>` 标题(一个页面只有一个h1标签，其他没限制）

** 自闭合标签 **

- `<hr />` 横线标签(Horizontal Rule)(自闭合标签，严格模式要加/）

- `<br />` 换行（break）(自闭合标签，严格模式要加/）

** 引用 **

- `<cite>` 引用作品的名字、作者的名字等

- `<q>` 引用一小段文字（大段文字引用用`<blockquote>`）

- `<blockquote>` 引用大块文字

- `<pre>` 保存格式化的内容（其空格、换行等格式不会丢失）

** 格式化 **（没有语义，建议少用）

- `<b>` 加粗（Bold)

- `<u>` 下划线 (Underlined)

- `<i>` 倾斜 (Italic)

- `<s>` 删除线 (Strikethrough)

** 强调 **（有语义）

- `<ins>` 下划线

- `<em>` 斜体。着重于强调内容，会改变语义的强调

- `<del>` 删除线

- `<strong>` 粗体。着重于强调内容的重要性

** img标签(image)：**

| 属性 | 说明 |
| :---- | :------------------------ |
| src | 图片显示路径 |
| alt | 如果图片加载不出来会显示这个属性中的文字 |
| title | 介绍这张图片 |

** a标签（超链接） **

| 属性 | 属性值 | 说明 |
| :---- | :-----: | :--------------------- |
| href |  | 标签跳转的目标地址 |
|  | "#" | 不跳转 |
|  | #id名 | 锚链接 |
| target | | 设置连接的跳转方式，默认"_self" |
|  | _blank | 保留原始页面，再跳转 |
|  | _self | 默认属性值，当前页面跳转 |
| base | | 为页面上所有的a标签设置跳转的方式（base标签一般放在titile标签下面） |

| 其他用法 |
| :---- |
| `<!-- iframe中打开 -->` |
| `<a href="http://sample-link.com" title="Sample Link" target="iframe-name">Sample</a>`     `<iframe name="iframe-name" frameborder="0"></iframe>` |
| `<!-- 页面中的锚点 -->` |
| `<a href="#achor">Achor Point</a>`      `<section id="achor">Achor Content</section>` |
| `<!-- 邮箱及电话需系统支持 -->` |
| `<a href="mailto:sample-address@me.com" title="Email">Contact Us</a>` |
| `<!-- 多个邮箱地址 -->` |
| `<a href="mailto:sample-address@me.com, sample-address0@me.com" title="Email">Contact Us</a>` |
| `<!-- 添加抄送，主题和内容 -->` |
| `<a href="mailto:sample-address@me.com?cc=admin@me.com&subject=Help&body=sample-body-text" title="Email">Contact Us</a>` |
| `<!-- 电话示例 -->` |
| `<a href="tel:99999999" title="Phone">Ring Us</a>` |

#### 表格

     <table border="1">
        <caption></caption>
        <thead>
            <tr><th></th><th></th></tr>
        </thead>
        <tbody>
            <tr><th></th><th></th></tr>
        </tbody>
        <tfoot>
            <tr><th></th><th></th></tr>
        </tfoot>
     </table>


| 属性 | 作用 |
| :---- | :-------------- |
| border | 给表格加上边框 |
| width | 设置宽度 |
| height | 设置高度 |
| cellspacing | 规定单元格之间的空白 |
| cellpadding | 规定单元格边沿与其内容之间的空白 |
| align(center/left/right) | 设置再table上，决定表格显示位置；设置在单元格上，决定单元格中文本的位置 |
| colspan | 一个单元格横跨多列 |
| rowspan | 一个单元格纵跨多行 |
| headers | 设置为一个或多个th单元格的id属性值 |

>虽然我们可以使用table中的标签来设置标签的一些样式，但是最好不要用，因为将来凡是与样式相关内容都是由css来设置的。

| 标签 | 作用 | 特点 |
| :---- | :-------------- | :--------------- |
| th | 表示标题行单元格 | 其中的文字加粗，居中 |
| tr | 表示一行单元格 | |
| td | 表示单元格 | |
| caption | 表格标题 | 在表格的最上面显示标题 |
| col | 表示一列 |   |
| colgroup | 表示一组列 |  |
| table | 表示表格 | 表格元素都写在此标签中 |
| thead | 用来存放当前列的表头 | 如果没有加css页面默认将表头中的高度设置变小 |
| tbody | 一般用来存放页面中的主体数据 | 如果不写会自动加上 |
| tfoot | 表格表尾 | 无 |


#### 表单

作用：用来收集用户的信息，将来提交到服务器

| 标签 | 作用 |
| :---- | :-------------- |
| input | 表示用于收集用户的建议值 |
| form | |
| select | 下拉框 | 
| textarea | 文本域 | 

| 属性 | 属性值 | 作用 | html? |
| :---- | :-------------- | :-----| :-----|
| type | text | 文本框 |  |
|  | password | 密码框 |  |
|  | hidden | 隐藏域 |  |
|  | radio | 单选框 |  | 
|  | checkbox | 多选框 |  |
|  | button | 按钮 |  |
|  | reset | 重置 |  |
|  | image | 图片按钮 |  |
|  | submit | 提交 |  |
|  | number | 生成输入框只获取数据 | ![](/image/html5_badge20.png) |



| 属性 | 属性值 | 作用 | HTML5? | 作用域 |
| :---- | :--- | :----: | :---- |
| dirname | | 指定元素内容文字方向的名称 | ![](/image/html5_badge20.png) | input>text |
| list | | 指定为文本框提供建议值的datalist元素， 其值为datalist元素的id值 | ![](/image/html5_badge20.png) | input>text |
| value | | 用于设置默认值(text,password,button) |  |  |
| maxlength | | 输入字符最大数目 | | |
| readonly | | 不影响其外观，用来将文本框设为只读以阻止用户编辑其内容 | | |
| disabled | | 文本框显示灰色，并且禁止编辑其中的文字 | | |
| required | | 表示用户必须输入一个值，否则无法通过输入验证 | ![](/image/html5_badge20.png) | |
| pattern | | 输入验证的正则表达式 | ![](/image/html5_badge20.png) | |
| placeholder | | 指定关于所需数据类型的提示 | ![](/image/html5_badge20.png) | |
| size | | 通过指定文本框中可见的字符数目设定其宽度 |  | 无 |

















