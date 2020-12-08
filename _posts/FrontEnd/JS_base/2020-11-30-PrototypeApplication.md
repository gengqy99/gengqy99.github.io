---
title: JS：原型对象的应用
date: 2020-11-30 09:00:00 +0800
categories: [JS, Basic]
tags: [js]     # TAG names should always be lowercase
---

## 用于存放对象的方法

通过构造函数可以实例化任意个数的对象，但这些对象的`__proto__`指向的构造函数的原型对象却是唯一的。因此可以把对象的公共方法存放在原型对象中，而不是在构造函数的方法体中通过`this.`的方式来赋值，以达到节省内存空间的目的。

```javascript
function Person(name) {
    this.name = name;
}
Person.prototype.eat = function () {
    console.log(`${this.name} can eat`);
}
const per = new Person('xiaoming');
per.eat(); // xiaoming can eat
```

*ps：为什么`per`对象能成功调用到构造函数原型对象中的`eat`方法？*
