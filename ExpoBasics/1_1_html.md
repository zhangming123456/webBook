## 学习HTML标签

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

** DOCTYPE（document type）:文档类型 **

声明位于文档中的最前面的位置，处于 <html> 标签之前。此标签可告知浏览器文档使用哪种 HTML 或 XHTML 规范.

* HTML与XHTML包括的文档类型

html：三种

xhtml: 三种(html升级版本)是一种相对html语法更加严谨的html;

| 文档类型 | 分类 | 备注 |
| :------ | :---------------------- | :--------------------|
| HTML | HTML Strict DTD | 请求比较严格的html类型 |
|  | HTML Transitional DTD | 相对而言比较规范不太严禁 |
|  | Frameset DTD | 框架级的类型 |
xHTML

HTML Strict DTD

请求比较严格的html类型

HTML Transitional DTD

相对而言比较规范不太严禁



注意事项：

- `<!DOCTYPE html>` 必须首行定格

- `<title>` 为文档标题

- `<meta charset="utf-8">` 文档解码格式

- `<meta name="keywords" content="...">` 和 `<meta name="description" content="...">` 提供给搜索引擎使用

- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` 移动端浏览器的宽高与缩放

- `<link>` 标签可以引入 favicon 和样式表 CSS 文件

***

#### HTML 语法


书写规范

- 小写标签和属性

- 属性值双引号

- 代码因嵌套缩进

***
#### 全局属性

- id, `<div id='unique-element'></div>`，页面中唯一

- class，`<button class='btn'>Click Me</button>`，页面中可重复出现

- style，尽量避免

- title，对于元素的描述类似于 Tooltip 的效果。

***
####