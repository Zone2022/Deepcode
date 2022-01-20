# Day3&Day4学习笔记

---


## python基础语法

### 数据类型

#### 变量赋值

Python中的变量赋值不需要类型声明。
等号 = 用来给变量赋值。
等号 = 运算符左边是一个变量名，等号 = 运算符右边是存储在变量中的值。
例：
```Python
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
counter = 100 # 赋值整型变量
miles = 1000.0 # 浮点型
name = "John" # 字符串
```

#### 标准数据类型

Python有五个标准的数据类型：

- Numbers（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Dictionary（字典）

---

### 列表

序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。
常见的是**列表**和元组。

创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。
如下：
```Python
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5 ]
list3 = ["a", "b", "c", "d"]
```

#### 访问列表中的值

可使用下标索引来访问列表中的值，或使用方括号的形式截取字符
如下：
```Python
#!/usr/bin/python
 
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5, 6, 7 ]
 
print "list1[0]: ", list1[0]
print "list2[1:5]: ", list2[1:5]
```

输出：
```
list1[0]:  physics
list2[1:5]:  [2, 3, 4, 5]
```

#### 其他列表函数

- cmp(list1, list2)  比较两个列表的元素
- len(list) 列表元素个数
- max(list) 返回列表元素最大值 
- min(list) 返回列表元素最小值 
- list(seq) 将元组转换为列表 

#### 其他列表方法

- list.append(obj) 在列表末尾添加新的对象
- list.count(obj) 统计某个元素在列表中出现的次数
- list.extend(seq) 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）
- list.index(obj) 从列表中找出某个值第一个匹配项的索引位置
- list.insert(index, obj) 将对象插入列表
- list.pop([index=-1]) 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
- list.remove(obj) 移除列表中某个值的第一个匹配项
- list.reverse() 反向列表中元素
- list.sort(cmp=None, key=None, reverse=False) 对原列表进行排序

### 元组

元组与列表类似，不同之处在于**元组的元素不能修改**。
**元组使用小括号，列表使用方括号。**
元组创建需要在括号中添加元素，并使用逗号隔开。
```Python
tup1 = ('physics', 'chemistry', 1997, 2000)
tup2 = (1, 2, 3, 4, 5 )
tup3 = "a", "b", "c", "d"
```


注意：元组中只包含一个元素时，需要在元素后面添加逗号`tup1 = (50,)`
> 元组与字符串类似，下标索引从0开始，可以进行截取，组合等。
#### 访问元组

元组可以使用下标索引来访问元组中的值。
如下
```Python
#!/usr/bin/python
 
tup1 = ('physics', 'chemistry', 1997, 2000)
tup2 = (1, 2, 3, 4, 5, 6, 7 )
 
print "tup1[0]: ", tup1[0]
print "tup2[1:5]: ", tup2[1:5]
```
输出：
```
tup1[0]:  physics
tup2[1:5]:  (2, 3, 4, 5)
```
#### 元组运算符

|Python 表达式|	结果	|描述|
|-----------:|:-----:|:------|
|len((1, 2, 3))	|3	|计算元素个数|
|(1, 2, 3) + (4, 5, 6)	|(1, 2, 3, 4, 5, 6)	|连接|
|('Hi!',) * 4	|('Hi!', 'Hi!', 'Hi!', 'Hi!')	|复制|
|3 in (1, 2, 3)	|True	|元素是否存在|
|for x in (1, 2, 3): print x,|	1 2 3	|迭代|
---
### 字典

字典是另一种可变容器模型，且可存储任意类型对象。
字典的每个键值 key=>value 对用冒号 : 分割，每个键值对之间用逗号 , 分割，整个字典包括在花括号 {} 中 。
如下：
```Python
d = {key1 : value1, key2 : value2 }
```
---
### 函数
函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。

#### 定义函数

规则：

- 函数代码块以 def 关键词开头，后接函数标识符名称和圆括号()。
- 任何传入参数和自变量必须放在圆括号中间。圆括号之间可以用于定义参数。
- 函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
- 函数内容以冒号起始，并且缩进。
- return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。

#### 语法

```Python
def functionname( parameters ):
   "函数_文档字符串"
   function_suite
   return [expression]
   ```

#### 调用

例：调用printme（）函数：
 ```Python
 #!/usr/bin/python
# -*- coding: UTF-8 -*-
 
# 定义函数
def printme( str ):
   "打印任何传入的字符串"
   print str
   return
 
# 调用函数
printme("我要调用用户自定义函数!")
printme("再次调用同一函数")
```
输出：
```
我要调用用户自定义函数!
再次调用同一函数
```

### 循环语句

#### for循环

格式：
```
for iterating_var in sequence:
   statements(s)
   ```
   流程类似于Java中的for循环。
   例：
   ```Python
   #!/usr/bin/python
# -*- coding: UTF-8 -*-
 
for letter in 'Python':     # 第一个实例
   print("当前字母: %s" % letter)
 
fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # 第二个实例
   print ('当前水果: %s'% fruit)
 
print ("Good bye!")
```

输出：
```
当前字母: P
当前字母: y
当前字母: t
当前字母: h
当前字母: o
当前字母: n
当前水果: banana
当前水果: apple
当前水果: mango
Good bye!
```

#### while循环

格式：
```
while 判断条件(condition)：
    执行语句(statements）
```
    
流程类似于Java中while循环
例：
```Python
#!/usr/bin/python
 
count = 0
while (count < 9):
   print 'The count is:', count
   count = count + 1
 
print "Good bye!"
```

输出：
```
The count is: 0
The count is: 1
The count is: 2
The count is: 3
The count is: 4
The count is: 5
The count is: 6
The count is: 7
The count is: 8
Good bye!
```
