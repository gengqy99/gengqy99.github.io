---
title: JS：变量作用域
date: 2020-11-08 00:00:00 +0800
categories: [JS, Basic]
tags: [js]
---

## JS中作用域的分类

用不同方式声明的变量，起作用的范围是不同。变量起作用的范围被称为变量的作用域。JS变量的作用域有以下3种：

1. 全局作用域
2. 函数作用域
3. 块级作用域(es6)

用不同声明方式声明的变量的作用域如下：

### 无关键字直接赋值

不使用任何关键字声明，直接赋值的变量，具有全局作用域

```javascript
function f() {
    function f_inner() {
        variable = 10; // 第3行
    }
    f_inner();
}
f();
console.log(variable); // 10
```

### 使用var声明

使用var声明在非函数体内的变量，具有全局作用域

```javascript
if(true) {
    var variable = 10;
}
console.log(variable); // 10
```

```javascript
for(var i = 0; i < 2; i++){}
console.log(i); // 2
```

使用var声明在函数体内的变量，具有函数作用域

```javascript
function f() {
    var variable = 10;
    console.log(variable); // 10
}
f();
console.log(variable); // Uncaught ReferenceError: variable is not defined
```

### 位于函数形参列表的变量

### 使用let、const声明的变量
