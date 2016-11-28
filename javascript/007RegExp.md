[TOC]

# 正则表达式

正则表达式是一个对象，这个对象描述一种字符模式。

JavaScript **RegExp** 类代表正则表达式，字符串和 **RegExp** 都定义了方法，在方法中使用正则表达式来执行文本中强大的模式匹配和搜索替换功能。

## 语法

正则表达式可以被 RegExp() 构造函数定义，如下所示：

```
var pattern = new RegExp(pattern, attributes);   
or simply   
var patter = /pattern/attributes;
```

参数描述：

- **pattern：**是一个字符串，指定了正则表达式的模式或其他正则表达式。
- **attributes：**是一个可选的字符串，包含属性 "g"、"i" 和 "m"，分别用于指定全局匹配、区分大小写的匹配和多行匹配。

## 方括号

方括号 ([]) 用于正则表达式的上下文中时有特殊意义，用来查找一系列字符。

| 表达     | 描述                 |
| ------ | ------------------ |
| [...]  | 查找方括号之间的任何字符       |
| [^...] | 查找任何不在方括号之间的字符     |
| [0-9]  | 查找任何从 0 至 9 的数字    |
| [a-z]  | 查找任何小写 a 到小写 z 的字符 |
| [A-Z]  | 查找任何大写 A 到大写 Z 的字符 |
| [a-Z]  | 查找任何小写 a 到大写 Z 的字符 |

上面所示的范围为一般情况；还可以使用范围 (0-3) 匹配任何从 0 到 3 的十进制数字，或范围 (b-v) 来匹配任何从小写 b 到小写 v 的字符。

## 量词

方括号括起来的字符序列或单个字符出现的频率或位置可以用一个特殊的符号来表示。每个特殊字符都有一个特定的含义。+、*、? 和 $ 符号都遵循一个字符序列模式。

| 表达     | 描述                     |
| ------ | ---------------------- |
| p+     | 匹配任何包含至少一个 p 的字符串      |
| p*     | 匹配任何包含零个或多个 p 的字符串     |
| p?     | 匹配任何包含零个或一个 p 的字符串     |
| p{N}   | 匹配包含 N 个 p 的序列字符串      |
| p{2,3} | 匹配包含 2 或 3 个 p 的序列的字符串 |
| p{2,}  | 匹配包含至少 2 个 p 的序列的字符串   |
| p$     | 匹配任何结尾为 p 的字符串         |
| ^p     | 匹配任何开头为 p 的字符串         |

## 例子

下面的例子会帮助理清字符匹配的概念。

| 表达          | 描述                                    |
| ----------- | ------------------------------------- |
| [^a-zA-Z]   | 匹配任何不包含从 a 到 z 和从 A 到 Z 中任何字符的字符串     |
| p.p         | 匹配任何以一个 p 开始、其次是任意字符、紧随其后的是另一个 p 的字符串 |
| ^.{2}$      | 匹配任何包含两个字符的字符串                        |
| <b>(.*)</b> | 匹配任何封闭在 <b> 和 </b> 内的字符串              |
| p(hp)*      | 匹配任何包含一个 p、紧随其后的零个或多个 hp 序列的字符串       |

## 原义字符

| 字符           | 描述                                       |
| ------------ | ---------------------------------------- |
| Alphanumeric | 它自己                                      |
| \0           | 查找 NUL 字符（\u0000）                        |
| \t           | 查找制表符（\u0009）                            |
| \n           | 查找换行符（\u000A）                            |
| \v           | 查找垂直制表符（\u000B）                          |
| \f           | 查找换页符（\u000C）                            |
| \r           | 查找回车符（\u000D）                            |
| \xnn         | 指定的以十六进制数 nn 表示的拉丁字符;例如 \x0A 和 \n 表示的一样  |
| \uxxxx       | 查找以十六进制数 xxxx 规定的 Unicode 字符，例如 \u0009 和 \t 表示的一样 |
| \cX          | 控制字符 ^X；例如 \cJ 相当于换行符 \n                 |

## 元字符

元字符：在一个字母字符之前加上一个反斜杠，使这个组合具有特殊的含义。

例如,您可以使用 '\d' 元字符搜索大量资金数额：**/([\d]+)000/**，这里 **\d** 将寻找任何数值字符的字符串。

下面是元字符的列表，使用 PERL 风格的正则表达式表达。

| 字符              | 描述                  |
| --------------- | ------------------- |
| .               | 单个字符                |
| \s              | 空白字符（空格、制表符、换行符）    |
| \S              | 非空白字符               |
| \d              | 数字字符（0-9）           |
| \D              | 非数字字符               |
| \w              | 单词字符（a-z,A-Z,0-9,_） |
| \W              | 非单词字符               |
| [\b]            | 一个文字退格(特殊情况)        |
| [aeiou]         | 匹配一个在给定集合内的字符       |
| [^aeiou]        | 匹配一个不在给定集合内的字符      |
| [foo\|bar\|baz] | 匹配任何指定的备选方案         |

## 修饰

几个可用的 regexp 修饰符，它能使你的工作更容易，比如大小写敏感、搜索多个行等。

| 字符   | 描述                          |
| ---- | --------------------------- |
| i    | 执行对大小写不敏感的匹配                |
| m    | 执行多行匹配                      |
| g    | 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止） |

## RegExp属性

这是 RegExp 的各个属性及对应的属性描述的列表。

| 属性          | 描述                  |
| ----------- | ------------------- |
| constructor | 指定创建一个对象原型的函数       |
| global      | RegExp 对象是否具有标志 g   |
| ignoreCase  | RegExp 对象是否具有标志 i   |
| lastIndex   | 一个整数，标示开始下一次匹配的字符位置 |
| multiline   | RegExp 对象是否具有标志 m   |
| source      | 正则表达式的源文本           |

## RegExp方法

这是 RegExp 的各个方法及对应的属性描述的列表。

| 方法         | 描述                                  |
| ---------- | ----------------------------------- |
| exec()     | 检索字符串中指定的值。返回找到的值，并确定其位置            |
| test()     | 检索字符串中指定的值。返回 ture 或 false          |
| toSource   | 返回一个对象字面值代表指定的对象;您可以使用这个值来创建一个新的对象。 |
| toString() | 返回一个代表指定对象的字符串。                     |


