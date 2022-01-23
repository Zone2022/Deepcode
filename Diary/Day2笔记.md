# Day2学习笔记

---

## JavaScript基础

### 基本语法

- 脚本语言、简单性、弱类型、跨平台、大小写敏感.

严格区分大小写,建议每句代码结尾加分号.

JavaScript中单引号和双引号没有区别.

注释有单行注释和多行注释,与C/C++相同.

#### 变量

JavaScript是弱类型检查语言,只需要用var关键字声明变量,而不用区分类型.使用等号来为变量赋值：

```JavaScript
var x, length
x = 5
length = 6
```

#### 注释

双斜杠 // 后的内容将会被浏览器忽略

#### 保留关键字

JavaScript 关键字用于标识要执行的操作。
如下：

- boolean、byte、char、double、enum、float、int、long、short
- const、static
- class、private、protected、public、super、extends、implements、interface、abstract
- throws、final
- import、export、package
- goto
- native、translent、debugger、synchronized、valatile

---
### 数据类型

原始类型: Number(数字)、Boolean(布尔值)、String(字符串)、Null(空值)、Undefined(未定义).

- JavaScript 只有一种数字类型Number。数字可以带小数点，也可以不带

- typeof方法用于检测变量数据类型.

#### 声明变量类型
 
 当声明新变量时，可以使用关键词 "new" 来声明其类型：
```JavaScript
var carname=new String;
var x=      new Number;
var y=      new Boolean;
var cars=   new Array;
var person= new Object;
```



#### typeof 操作符

- typeof方法用于检测变量数据类型
实例
```JavaScript
typeof "John"                 // 返回 string
typeof 3.14                   // 返回 number
typeof NaN                    // 返回 number
typeof false                  // 返回 boolean
typeof [1,2,3,4]              // 返回 object
typeof {name:'John', age:34}  // 返回 object
typeof new Date()             // 返回 object
typeof function () {}         // 返回 function
typeof myCar                  // 返回 undefined (如果 myCar 没有声明)
typeof null                   // 返回 object
```
**注意：**

- NaN 的数据类型是 number
- 数组(Array)的数据类型是 object
- 日期(Date)的数据类型为 object
- null 的数据类型是 object
- 未定义变量的数据类型为 undefined

---

### 数据类型转换

#### 将数字转换为字符串

全局方法 String() 可以将数字转换为字符串。

该方法可用于任何类型的数字，字母，变量，表达式：

```JavaScript
String(x)         // 将变量 x 转换为字符串并返回
String(123)       // 将数字 123 转换为字符串并返回
String(100 + 23)  // 将数字表达式转换为字符串并返回
```

#### 将布尔值转换为字符串

全局方法 String() 可以将布尔值转换为字符串。
```JavaScript
String(false)        // 返回 "false"
String(true)         // 返回 "true"
```
#### 将日期转换为字符串

全局方法 String() 可以将日期对象转换为字符串。
```JavaScript
String(new Date())      // 返回 Thu Jul 17 2014 15:38:19 GMT+0200 (W. Europe Daylight Time)
```

#### 将字符串转换为数字

全局方法 Number() 可以将字符串转换为数字。

字符串包含数字(如 "3.14") 转换为数字 (如 3.14).

空字符串转换为 0。

其他的字符串会转换为 NaN (不是个数字)。
```JavaScript
Number("3.14")    // 返回 3.14
Number(" ")       // 返回 0
Number("")        // 返回 0
Number("99 88")   // 返回 NaN
```
#### 其他方法
- 转字符串: toString();
- 转数字: parseInt(); parseFloat();
- 强制类型转换: Boolean(value); Number(value); String(value);

---

### 对象

#### 对象类型

本地对象: 是ECMAScript定义的引用类型.

内置对象: 无需实例化可以直接使用的对象,是特殊的本地对象.

宿主对象: 用户的机器环境,包括DOM和BOM

#### 本地对象

##### 数组

```JavaScript
// 变长数组
var d_arr = new Array();
var d_arr[0] = "1";
var d_arr[1] = "2";
var d_arr[2] = "3";

// 定长数组
var s_arr = new Array("1","2","3");
var s_arr2 = ["1","2","3"];
```

| 方法名                      | 描述                                                      |
| --------------------------- | --------------------------------------------------------- |
| concat(arr1, arr2, ...)     | 在数组的结尾处连接多个新数组                              |
| join(sep)                   | 把数组元素按照分隔符sep合并成一个字符串                   |
| shift()                     | 删除第一个元素并返回该元素                                |
| pop()                       | 删除最后一个元素并返回该元素                              |
| push(el1, el2, ... ,elN)    | 数组结尾插入元素,并返回新数组的长度                       |
| unshift(el1, el2, ... ,elN) | 数组开头插入元素,并返回新数组的长度                       |
| reverse()                   | 数组元素倒序重组                                          |
| slice(start, end)           | 返回数组中开始与结束范围的一系列元素,若为负数则从后向前数 |
| toString()                  | 相当于join(",")                                           |

##### 日期

```javascript
new Date(); // 获取当前日期与时间
new Date(dateString); // 用日期时间字符串定义时间,如Jun 2,2000 08:00:00
new Date(milliseconds); // 使用1970.1.1到指定日期的毫秒数定义时间,如1232345
new Date(YY,MM,DD,HH,mm,ss,ms);
```

##### 正则表达式RegExp

- 用于检索文本中是否包含指定字符串

- ```javascript
  new RegExp(pattern [,attributes]);
  
  var pattern = new RegExp([0-9], g);
  ```

  - pattern: 字符串,用于规定正则表达式的匹配规则或其他正则表达式
  - attributes: 可选参数,包含属性值g(全局匹配)、i(区分大小写匹配)、m(多行匹配).

##### object

```javascript
// 所有类型都是对象
var student = new Object();
student.name = "xx";
student.id = "21191413";
student.major = "计算机科学与技术";
student.study = function(){
	alert("学习中");
}
```

- 内置对象
  - global全局对象
    - 其属性和函数可以用于所有的本地对象
    - 常用于编码、解码、数据类型的转换等.
  - math对象
    - 用于数学计算,包括绝对值函数、三角函数、最大最小值函数、乘方、四舍五入、随机数等函数.


---


### 函数

#### 语法

函数就是包裹在花括号中的代码块，前面使用了关键词 function：
```JavaScript
function functionname()
{
    // 执行代码
}
```
当调用该函数时，会执行函数内的代码。

#### 调用带参数的函数
`myFunction(argument1,argument2)`
声明函数时，请把参数作为变量来声明
```JavaScript
function myFunction(var1,var2)
{
代码
}
```

#### 带有返回值的函数
```JAvaScript
function myFunction()
{
    var x=5;
    return x;
}
```
上面的函数会返回值 5。
