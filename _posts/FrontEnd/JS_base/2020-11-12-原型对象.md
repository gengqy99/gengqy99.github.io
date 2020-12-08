---
title: JS：原型对象
date: 2020-11-12 16:00:00 +0800
categories: [JS, Basic]
tags: [js]     # TAG names should always be lowercase
---

任何的`函数对象`在定义的时候都会伴随着一个原型对象`prototype`出现，原型对象 [**默认**](#特殊的) 是Object的实例对象，含有至少 `constructor` 和 `__proto__` 这两个属性。

```javascript
function Person(name, age){
    this.name = name;
    this.age = age;
}
console.dir(Person);
/* 打印结果如下：
ƒ Person(name, age)
    arguments: null
    caller: null
    length: 2
    name: "Person"
    prototype:
        constructor: ƒ Person(name, age)
        __proto__: Object
    __proto__: ƒ ()
    [[FunctionLocation]]: VM2872:1
    [[Scopes]]: Scopes[1]
*/
```

原型对象和定义的函数对象是互指的

#### 特殊的：

Object构造函数的原型对象的 `__proto__` 是 `null` 。

## prototype与__proto__

| 区别与联系            | `prototype`        | `__proto__`                                 |
|:---------------------|:-------------------|:--------------------------------------------|
| 叫法                 | 原型对象            | 隐式原型对象                                 |
| this指向             | 函数的原型对象       | 当前对象的构造函数的原型对象                  |
| 出现在哪些地方        | 只有函数对象才有     | 任何对象都有                                 |
| 联系                 | 当对象a是通过构造函数b `new` 出来时：<br/> `a.__proto__ === b.prototype` |

## 彩蛋

构造函数的 `__proto__` 是什么？

![Function构造函数](/assets/img/prototype/constructor-Function.png){: width="350" class="normal"}

在上图中可以看到，构造函数对象 `Person` 的构造函数是 `Function`。

不难想到，我们可以通过 `new Function()` 的方式定义一个函数，语法如下：

```javascript
var fun = new Function('arg1', 'arg2', `
  arg1 = "参数1";
  arg2 = "参数2";
  console.log("别的执行语句");
  return 0;
`);
```

> 尽管这样是可行的，但不建议这样定义函数。因为这会解析两次代码，第一次解析常规js代码，第二次解析传入构造函数的字符串，效率低
