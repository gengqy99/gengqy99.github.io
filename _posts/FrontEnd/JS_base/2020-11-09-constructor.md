---
title: JS：构造函数
date: 2020-11-09 20:00:00 +0800
categories: [JS, Basic]
tags: [js]     # TAG names should always be lowercase
---

## 构造函数的定义

构造函数也是函数，使用大驼峰命名（不规范的命名并不会引发错误，但不建议）。来看一个简单的构造函数的例子：

```javascript
function Person(name, age) {
    console.log(this);
    this.eat = function () {
        console.log('人会吃饭');
    }
    console.log(this);
    this.name = name;
    this.age = age;
    console.log(this);
}
```

通过上述构造函数`new`出来的对象，具有一个eat()方法和name、age这两个属性。同时可以看到在构造函数中出现了[`this`关键字](/posts/this)，this默认指向的是调用这个函数的对象。

## 构造函数的使用

构造函数是用来实例化一个对象的，现在我们用之前定义的`Person`来实例化一个对象。

```javascript
var per1 = new Person('xiaoming', 20);
/*
console（控制台输出）:
Person {}
Person {eat: f}
Person {name: "xiaoming", age: 20, eat: ƒ}
*/
console.log(per1); // Person {name: "xiaoming", age: 20, eat: f}
```

以上打印结果可以得出一些信息：

1. 通过`new`使用构造函数时，函数方法体内的语句会执行。
2. this指向的对象在最开始是一个“内容为空的对象”，最后成为了一个和`per1`变量拥有同样内容的对象

## new做了什么

我认为js是这样做的：

1. 在堆结构中开辟一块内存空间，并在这块内存中存上其构造函数的原型对象的地址（引用）。

    ```console
   > var newObj = {};
   < undefined
   > newObj.__proto__ = Person.prototype; // 将构造函数Person的原型对象存到该对象的隐式原型对象__proto__上
   < { constructor: f }
    ```

2. 在这个内存（对象）中直接调用constructor()，会寻着原型链找到原型对象中的constructor()，并执行。

    ```console
   > newObj.constructor('xiaoming', 20);
   < undefined
    ```

3. constructor实际上指向的是Person函数对象，执行constructor()就是执行构造函数Person()。
4. 此时this指向这片新开辟的内存（对象），其中`this.属性名 = xxx;`自然就给该内存空间添加上了属性。
5. 返回这个内存空间的地址，最后被我们定义的per1变量接收。

    ```console
   > var per1 = newObj;
   < undefined
   > console.log(per1); // Person {name: "xiaoming", age: 20, eat: f}
   < undefined
    ```

> PS：
>   * 以上代码是在chrome中解释执行的，大家可以自行尝试，看看能否得到与new出来的per1相同的结果。
>   * 在该内存中直接调用的constructor()，所以this指向该内存（this指向最终调用函数的对象）。
>   * 原型对象是伴随着构造函数的定义而产生的。

事实上js是这样做的（网上大多数的说法）：

1. 为即将实例化的对象在堆结构中开辟一块内存空间。
2. 将构造函数内的this指向该内存空间。
3. 执行构造函数。
4. 生成实例对象，返回上述内存空间的地址值


