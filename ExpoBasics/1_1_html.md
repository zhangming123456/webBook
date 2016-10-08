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