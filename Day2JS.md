# 计算66！
```JavaScript
<!DOCTYPE html>
<html lang='en'>

<head> 
<meta charset="utf-8"> 

<title>计算1*2*3*...*66 结果</title> 
</head>
<body>
<script>
function test(num){
var n=num;
var total = 0;
for(var i=1;i<=n;i++){
 var temp = 1;
for(var j=i;j>=1;j--){
 temp *=j;
}
total += temp;
}
return total;
}
console.log("66的阶乘总和为"，test(66))
</script>
</body>
</html>
```

# 输出由 $ 组成的倒等腰三角形
```JavaScript
<!DOCTYPE html>
<html lang='en'>
<head> 
<meta charset="UTF-8"> 

<title>倒等腰三角形</title> 
</head>
<body>
<script>
 for(var i =0;i <= 5;i++){
     for(var j =5;j >=i;j--){
         document.write('&nbsp')
     }
     for (var k = 5;k>=2*i - 1; k--){
         document.write('&')
     }
     document.write('<br>')
 }
  </script>
</body>
</html>
```