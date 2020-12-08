---
title: JS：数据类型
date: 2020-11-07 00:00:00 +0800
categories: [JS, Basic]
tags: [js]     # TAG names should always be lowercase
---

## JS数据类型分类

1. 基本数据类型
    * number
    * string
    * boolean
    * undefined
    * null
2. 引用数据类型
    * 数组
    * 函数
    * 对象
    * 内置工具对象

> undefined类型只有一个值==>undefined。涵义为定义了但是未赋值（未定义就使用会报错）
> boolean类型只有两个值==>true|false
> null类型只有一个值==>null。通常用于对`对象`进行初始化或删除

## typeof

使用typeof返回一个 `字符串`，该字符串即为被判断变量的数据类型名称。

### typeof判断基本数据类型

typeof对null类型进行判断时，得到的是object；

对其余4种基本数据类型进行判断时，得到对应的类型名。

```javascript
const num = 0;
console.log(typeof num); // number
const str = 'a string';
console.log(typeof str); // string
const bl = true;
console.log(typeof bl); // boolean
const undef = undefined;
console.log(typeof undef); // undefined
const nullObj = null;
console.log(typeof nullObj); // object
```

注意：typeof返回一个 `字符串`

```javascript
console.log(typeof typeof {}); // string
```

### typeof判断引用数据类型

```javascript
console.log(typeof [1,2]); // object
console.log(typeof function(){}); // function
console.log(typeof {}); // object
console.log(typeof new Person('xiaoming')); // object
```

## instanceof

`instanceof`用于判断是不是某构造函数的实例对象，返回一个布尔值

用法： `变量名 instanceof 构造函数名`

```javascript
var arr = [];
console.log(arr instanceof Array); // true
console.log(arr instanceof Object); // true
```

注意： null不是Object的实例，null是基本数据类型（即使 `typeof null` 返回 `object` ）

```javascript
console.log(null instanceof Object); // false
```

## 小结：怎么判断数据类型

### null和undefined用 `===`

null和undefined都是只含有一个值的基本数据类型，因此用 `===` 进行判断

### 函数和除null以外的基本数据类型用 `typeof`

### 数组和其他自定义构造函数的对象用 `instanceof`
