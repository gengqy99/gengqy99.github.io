---
title: JS：原型链
date: 2020-11-30 11:00:00 +0800
categories: [JS, Basic]
tags: [js]     # TAG names should always be lowercase
---

使用`对象名.属性名`调用对象的属性时，会先在当前对象内寻找是否有这个属性，如果没有就到对象的构造函数的原型对象中寻找，再没有再到原型对象的原型对象中找，直到找到null为止，这个链式的查找过程，就是原型链。

![ProtoChain](/assets/img/prototype/ProtoChain.png){: width="360" class="normal"}

![PrototypeChain](/assets/img/prototype/PrototypeChain.png){: width="360" class="normal"}

