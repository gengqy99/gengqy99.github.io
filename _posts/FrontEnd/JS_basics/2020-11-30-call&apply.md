---
title: JS：call和apply的用法
date: 2020-11-30 14:00:00 +0800
categories: [JS, Basic]
tags: [js]     # TAG names should always be lowercase
---

`apply`和`call`方法可以改变一个函数的执行对象

```javascript
var result_apply = window.add.apply(per, [10, 20]);
var result_call = window.add.call(per, 10, 20);

function add(num1, num2) {
    return num1 + num2;
}
```

`apply`和`call`仅仅只是传参方式不同
