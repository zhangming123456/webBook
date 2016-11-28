[TOC]

# 函数

## 函数定义

我们使用一个函数之前,我们需要定义该函数。在 *JavaScript* 中最常见的定义一个函数的方式是使用函数关键字，紧随其后的是一个独特的函数名，参数列表(也可能是空的)，和一个被花括号包围的语句块。这里显示的基本语法：

```
<script type="text/javascript">
<!--
function sayHell0(parameter-list){
    statements
}
//-->
</script>
```

### 调用函数

在脚本中调用某个函数之后,你会需要简单的编写的函数的名称如下：

```
<script type="text/javascript">
<!--
sayHello();
//-->
</script>
```

### 函数参数

到目前为止，我们已经看到了没有参数的函数，但这些函数里面都有一个功能就是去传递不同的参数。这些被传递的参数可以在函数内被捕获且可以在这些函数上进行任何操作。在一个函数内可以把多个参数用逗号隔开。

## reture 语句

一个 *JavaScript* 函数可以有一个可选的返回语句。这是必需的，如果你想从一个函数返回一个值。这个语句应该是函数里的最后一个语句。

例如你可以在一个函数内输入两个数字，然后你可以从函数返回调用他们相乘的结果。

## Function

**构造器说明**：定义函数或新增对象构造器

**实例化方法**

```
// 对象实例化
var f0 = new Function('i', 'j', 'return (i + j)');
// 函数关键字语句
function f1(i, j){return i + j;}
// 函数表达式
var f3 = function(i, j){return i + j;};
```

**属性及方法**

- prototype

**原型对象属性及其方法**

- constructor
- apply
- call
- bind

**实例对象属性和方法**

- length
- prototype
- arguments
- caller

### 自定义对象构造器

下面的代码声明一个 Point 增加了一个move方法，最后创建了一个 Point 的实例对象。

```
function Point(x, y) {
  this.x = x;
  this.y = y;
}

Point.prototype.move = function(x, y) {
  this.x += x;
  this.y += y;
}

var p = new Point(1, 2);
```

### Function.prototype.apply

功能：通过参数指定调用者和函数参数并执行该函数

```
// functionObj.apply(thisArg[, argsArray])
function Point(x, y) {
  this.x = x;
  this.y = y;
}

Point.prototype.move = function(x, y) {
  this.x += x;
  this.y += y;
}

var p = new Point(1, 1);
var circle = {x: 1, y: 1, r: 1};
p.move.apply(circle, [2, 1]); // {x: 3, y: 2, r: 1}
```

### Function.prototype.bind

功能：通过参数指定函数调用者和函数参数并返回该函数的引用

```
// functionObj.bind(thisArg[, arg1[, arg2[, ...]]])
function Point(x, y) {
  this.x = x;
  this.y = y;
}

Point.prototype.move = function(x, y) {
  this.x += x;
  this.y += y;
}

var p = new Point(1, 1);
var circle = {x: 1, y: 1, r: 1};
var circleMoveRef = p.move.bind(circle, 2, 1);
setTimeout(circleMoveRef, 1000); // {x: 3, y: 2, r: 1}

// 之间使用 circleMoveRef() 效果等同于 apply()
circleMoveRef();
```

### 子类构造器

```
function Circle(x, y, r) {
  Point.apply(this, [x, y]);
  this.radius = r;
}
Circle.prototype = Object.create(Point.prototype);
Circle.prototype.constructor = Circle;
Circle.prototype.area = function(){
  return Math.PI * this.radius * this.radius;
}

var c = new Circle(1, 2, 3);
c.move(2, 2);
c.area();
```

### 函数调用

- `()`
- `apply`
- `call`

### 函数参数

- 形参个数不一定等于实参个数
- 值专递
- 通过参数类型检查实现函数重载

#### arguments

arguments 的常用属性

- length 实参个数
- 0...arguments.length-1 实参属性名称（key）
- callee 函数本身

```
function max(a, b) {
  if (max.length === arguments.length) {
    return a>b?a:b;
  } else {
    var _max = arguments[0];
    for(var i = 0; i < arguments.length; i++) {
      if (_max < arguments[i]) {
        _max = arguments[i];
      }
    }
    return _max;
  }
}
```

#### 值专递

函数参数的值专递是参数复制都是栈内存中的复制。![Function](images/Function.jpg)

```
// 原始类型
function plusplus(num) {
  return num++;
}
var count = 0;
var result = plusplus(count); // result = 1; count = 0;

// 引用类型
function setName(obj) {
  obj.name = 'obama';
}
var president = {name: 'bush'};
setName(president); // {name: 'obama'};
```

#### 函数重载

以 `Require.JS` 中的 `define()` 为例：

```
define(function(){
  var add = function(x, y) {
    return x + y;
  };
  return {
    add: add
  };
})

define(['lib'], function(){
  var add = function(x, y) {
    return x + y;
  };
  return {
    add: add
  };
})

define('math', ['lib'], function(){
  var add = function(x, y) {
    return x + y;
  };
  return {
    add: add
  };
})

// define 的实现代码
/**
 * The function that handles definitions of modules. Differs from
 * require() in that a string for the module should be the first argument,
 * and the function to execute after dependencies are loaded should
 * return a value to define the module corresponding to the first argument's
 * name.
 */
define = function (name, deps, callback) {
    var node, context;

    //Allow for anonymous modules
    if (typeof name !== 'string') {
        //Adjust args appropriately
        callback = deps;
        deps = name;
        name = null;
    }

    //This module may not have dependencies
    if (!isArray(deps)) {
        callback = deps;
        deps = null;
    }

    // 省略以下代码
    // ...
};
```