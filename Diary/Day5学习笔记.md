# Day5学习笔记

---

## Vue2基本语法

### 

---

## ES6+特性

### let 和 const

一般用于申明常量。

#### let

- 变量不能重复申明

- 只在当前块级作用域下声明才有效

- 命令声明的变量必须先声明后赋值，在let命令声明变量之前，该变量不可用。

经典用例：for 循环计数器

```JavaScript
// var 声明
var a = [];
for (var i = 0; i < 10; i++) {
    a[i] = function () {
        console.log(i);
    }
}
a[0]();  // 10

// let 声明
var a = [];
for (let i = 0; i < 10; i++) {
    a[i] = function () {
        console.log(i);
    }
}
a[0](); // 0
console.log(i);
// ReferenceError: i is not defined
```

#### const

- 一定要赋初始值
- 也具有块级作用域(与let一样)
- **常量的值不能修改**

```JavaScript
// const声明的基本数据类型不能改变
const a = 1;
a = 2; // error

// const声明的引用数据类型中的属性值可被重新赋值
const obj = {};
obj.attr = value;
obj.attr; // value;
```
> ES6声明变量的六种方法：
`var、function、let、const、import、class`
---

### 变量解构赋值

ES6 允许按照一定模式从数组和对象中提取值，对变量进行赋值，这被称为解构赋值。

#### 数组的解构赋值

```JavaScript
let [a, b, c] = [1, 2, 3]; // a = 1; b = 2; c = 3;
let [a, b, c = 3] = [1,2]; // a = 1; b = 2; c = 3;
let [a, [b, c], d] = [1, [2, 3], 4]; // a = 1; b = 2; c = 3; d = 4;

// 解构不成功为undefined
let [x, y, ...z] = ['a']; // x = 'a'; y = undefined; z = [];

// 可以设置默认值
let [x, y = 'b'] = ['a', undefined]; // x = 'a'; y = 'b';

// ES6通过严格运算符(===),判断一个位置是否有值,只有一个数组成员严格等于undefined,默认值才会生效
let [x = 1] = [undefined];  x // 1
let [x = 1] = [null]; x // null

```

#### 对象的解构赋值
```JavaScript
// 变量名和属性名一致
let { foo, bar } = { foo: "aaa", bar: "bbb" }; 
<===> 
let { foo: foo, bar: bar } = { foo: "aaa", bar: "bbb" };
foo // aaa
var // bbb
```

#### 字符串的解构赋值 

```JavaScript
const [a,b,c,d,e] = 'hello';
a // 'h'
b // 'e'
c // 'l'
d // 'l'
o // 'o'

let { length: len } = 'hello';
len // 5
```
#### 数值和布尔值的解构赋值
```JavaScript
// 解构赋值时，如果等号右边是数值和布尔值，则先转化为对象
let { toString: s } = 123;
s === Number.prototype.toString // true

let { toString: s } = true;
s === Boolean.prototype.toString // true
```
#### 函数的解构赋值
```JavaScript
// 解构赋值时，如果等号右边是数值和布尔值，则先转化为对象
let { toString: s } = 123;
s === Number.prototype.toString // true

let { toString: s } = true;
s === Boolean.prototype.toString // true

// 函数move的参数是一个对象，通过对这个对象解构，得到x和y；解构失败，x和y为默认值
function move({x = 0, y = 0} = {}) {
    return [x, y];
}
<===>
function move({x = 0, y = 0}) {
    return [x, y];
}
move({x: 3, y: 8}); // [3, 8]
move({x: 3}); // [3, 0]
move({});  // [0, 0]
move();  // [0, 0]

```
### 
---
**还未完成。。。**

