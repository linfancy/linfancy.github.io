---
layout: article
title: javascript中数组的引用调用问题
category: javascript
date: 20140902
---

在javascript中，数组是属于引用调用类型的，如下面例子

```javascript
a = [1,2,3];
b = a;
b[1] = 6;
console.log(a);//输出[1,6,3]
console.log(a === b);//输出true
```

但是请注意，js数组是引用类型,它只允许通过索引来获取或改变数组的值 引用类型的东西都是不能通过(它赋值过的外部变量)所改变的 也就是(它赋值过的外部变量)这个值改变了原数组不会有任何变化，请看下面例子：

```javascript
a = [1,2,3];
c = a[1];
c = 10;
console.log(a[1]);//输出2
console.log(c === a[1]);//输出true
```