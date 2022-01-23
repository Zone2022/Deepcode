# 自定义页面
```HTMl
<html>
    <head>
        <meta charset="utf-8">
        <title>自定义复原页面</title>
    </head>
    <body>
      <h1 id="words">Hello World！</h1> 
      <form action="">
        <input type="button" value="变为红色" id="turn_red">
        <input type="button" value="复原" id="resume">
    </form>
    <script type="text/javascript">
        document.getElementById("turn_red").addEventListener("click",function(){
            document.getElementById("words").style.color="red";
        });
        document.getElementById("resume").addEventListener("click",function(){
            document.getElementById("words").style.color="black";
        });
    </script>
    </body>
</html>
```
