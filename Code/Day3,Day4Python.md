# Python
 输⼊变量n，输出形如{1:1, … ,n: n*n} 的字典。例如当n=8时，输出{1: 1，2: 4, 3: 9, 4: 16, 5:25, 6: 36, 7: 49, 8: 64} 


```Python
n = input('请输入n: ')
factorial = 1
while not n.isdigit():
    n = input('请重新输入n(数字): ')
n = int(n)
dic = {i: factorial*i for i in range(1, n + 1)}
print(dic)
```
