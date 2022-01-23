#Day1学习笔记
[TOC]
---
## HTML基础语法：
### 基本结构：
HTML文件是一种纯文本文件,以“.html”或“.htm”为后缀.
HTML的基本组成单位是**元素**,语法基本结构如下

```html
<label>_Content<\label>
```
#### 开头基本结构
```html
<!DOCTYPE html><!--文档类型声明-->
<html> <!--根标签-->
    <head> <!--首部标签-->
        <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
        <title>一个简单页面</title>
    </head>
    <body> <!--主体标签-->
        网页正文部分
        <table>
            <tr><td>Hello World!</td></tr>
        </table>
    </body>
</html>
```
#### 主体结构

HTML文档主体结构是由\<html\>根元素、\<head\>首部元素和\<body\>主体元素三大元素组成

- \<html\>: 文档以\<html\>标签开始,以\</html\>标签结束,所有内容都需要放在这两个标签之间.

- \<head\>元素: 页面头部信息,用于**向浏览器提供整个页面的基本信息**,但不包含页面的主体内容.
  - 头部信息中主要包括页面的标题、元信息、CSS样式、JavaScript脚本等元素.
  - 页面头部信息通常并不在浏览器中显示,标题元素（\<title\>\</title\>标签的内容）除外,会显示在浏览器窗口的左上角.
- \<body\>元素: **网页的正文,是用户在浏览器主窗口中看到的信息**,包括图片、表格、段落、图片、视频等内容,且需位于\<body\>标签之内;但并不是所有的\<body\>内部标签都是可见的.
### 标题
#### 定义：
HTML标题是通过`<h1>-<h6>`标签来定义的。`<h1>`定义最大的标题，`<h6>`定义最小的标题。
> 注释: 浏览器会自动地在标题的前后添加空行。
####使用：
搜索引擎使用标题为您的网页的结构和内容编制索引，
所以应该将 h1 用作主标题（最重要的），其后是 h2（次重要的），再其次是 h3，以此类推。
```HTML
<h1>这是一个标题。</h1>
<h2>这是一个标题。</h2>
<h3>这是一个标题。</h3>
```
#### 水平线
`<hr> `标签在 HTML 页面中创建水平线。
hr 元素用于分隔内容.
```HTML
<p>这是一个段落。</p>
<hr>
<p>这是一个段落。</p>
```
---
### 段落
段落是通过 `<p>`标签定义的。
```HTML
<p>这是一个段落 </p>
<p>这是另一个段落</p>
```
> 注释：不要忘记结束标签`</p>`
---
### HTML超链接
HTML使用标签 `<a>`来设置超文本链接。
#### 形式
当把鼠标指针移动到网页中的某个链接上时，箭头会变为一只小手；
在默认情况下，链接将以以下形式出现在浏览器中：
+ 一个未访问过的链接显示为蓝色字体并带有下划线。
+ 访问过的链接显示为紫色并带有下划线。
+ 点击链接时，链接显示为红色并带有下划线。
#### 语法
`<a href="url">链接文本</a>`
href 属性描述了链接的目标。
##### target 属性
使用 target 属性，可以定义被链接的文档在何处显示
`<a href="https://链接文本/" target="_blank">访问</a>`
如果你将 target 属性设置为 "_blank", 链接将在新窗口打开。

### 图像
在 HTML 中，图像由`<img>` 标签定义。
> 但要注意，`<img>` 是空标签.要在页面上显示图像，你需要使用源属性（src）
#### 语法
`<img src="url" alt="some_text">`
URL 指存储图像的位置。如果名为 "pulpit.jpg" 的图像位于 www.runoob.com 的 images 目录中，那么其 URL 为 http://www.runoob.com/images/pulpit.jpg。
#### Alt属性
alt 属性用来为图像定义一串预备的可替换的文本。
`<img src="boat.gif" alt="Big Boat">`
在浏览器无法载入图像时，替换文本属性会告诉读者失去的信息。
#### 设置图像的高度与宽度
height（高度） 与 width（宽度）属性用于设置图像的高度与宽度。
`<img src="pulpit.jpg" alt="Pulpit rock" width="304" height="228">`
### 列表
#### HTML无序列表
无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈）进行标记。
无序列表使用` <ul> `标签
```
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
```
显示为
+ Coffee
+ Milk
#### HTML 有序列表
有序列表项目使用数字进行标记。 有序列表始于 `<ol>` 标签。每个列表项始于 `<li> `标签。
列表项使用数字来标记。
```
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```
显示为
1. Coffee
2. Milk
### HTML表单
HTML 表单用于收集不同类型的用户输入，使用表单标签 `<form>` 来设置
#### 输入元素
多数情况下被用到的表单标签是输入标签`<input>`。
输入类型是由类型属性（type）定义的。主要输入类型如下：
##### 文本域
文本域通过`<input type="text"> `标签来设定
```
<form>
First name: <input type="text" name="firstname"><br>
Last name: <input type="text" name="lastname">
</form>
```
显示
First name: 
Last name: 
##### 密码字段
密码字段通过标签`<input type="password">` 来定义:
```
<form>
Password: <input type="password" name="pwd">
</form>
```
显示
Password: 
##### 复选框
```
<form>
<input type="checkbox" name="vehicle" value="Bike">I have a bike<br>
<input type="checkbox" name="vehicle" value="Car">I have a car
</form>
```
显示
o Male
o Female
##### 提交按钮
```
<form name="input" action="html_form_action.php" method="get">
Username: <input type="text" name="user">
<input type="submit" value="Submit">
</form>
```
<form name="input" action="html_form_action.php" method="get">
Username: <input type="text" name="user">
<input type="submit" value="Submit">
</form>
在上面的文本框内键入几个字母，然后点击确认按钮，那么输入数据会传送到 "html_form_action.php" 的页面。该页面将显示出输入的结果。

### 表格
由 `<table>` 标签来定义。每个表格均有若干行（由 `<tr>`标签定义），每行被分割为若干单元格（由 `<td> `标签定义）。字母 td 指表格数据（table data），即数据单元格的内容。
例：
```
<table border="1">
    <tr>
        <td>row 1, cell 1</td>
        <td>row 1, cell 2</td>
    </tr>
    <tr>
        <td>row 2, cell 1</td>
        <td>row 2, cell 2</td>
    </tr>
</table>
```
显示
| row1,cell1 | row1,cell2 |
|------------|------------|
| row2,cell1 | row2,cell2 |
###HTML 框架
使用框架可以在同一个浏览器窗口中显示不止一个页面。
#### 框架属性
\<frame\>标签用于指示框架集中每个框架的内容.该标签可以使用单标签形式,也可以使用双标签形式.
```html
<frame src="url" name=" " ...> </frame>
```
- | 属性         | 取值            | 描述                                                         |
  | ------------ | --------------- | ------------------------------------------------------------ |
  | src          |                 | 用于指向一个页面资源的URL路径，可以是绝对路径，也可以是相对路径 |
  | name         |                 | 为框架指定一个名称                                           |
  | frameborder  | 0 / 1           | 设置框架的边框是否显示                                       |
  | marginheight | 整数(**1**)     | 定义内容与框架的上下边缘高度                                 |
  | marginwidth  | 整数(**1**)     | 定义内容与框架的左右边缘宽度                                 |
  | scrolling    | yes / no / auto | 设置框架中是否显示滚动条(通常在右侧)                         |
  | noresize     |                 | 设置框架不能调整大小                                         |
  
## CSS基本语法



###引入方式


- 内联样式

  ```html
  <element style="attr1:val1; attr2:val2; ...">
  ```

- 内部样式

  ```html
  <head>
      <style type="text/css">
          <!--选择器-->
      </style>
  </head>
  ```

- 外部样式

  - ```html
    <link htrf="style.css" rel="stylesheet" type="text/css">
    ```


### 选择器

```css
*{attr1:val1; attr2:val2; ...} /*通用选择器*/
p{attr1:val1; attr2:val2; ...} /*元素选择器*/
#id名称{attr1:val1; attr2:val2; ...} /*ID选择器*/
.class名称{attr1:val1; attr2:val2; ...} /*类选择器*/
元素名称[元素属性]{attr1:val1; attr2:val2; ...} /*属性选择器*/
	例: a[href="https://www.baidu.com"]{color:red;}
/*组合选择器*/
p.class{attr1:val1; attr2:val2; ...}
p#ID{attr1:val1; attr2:val2; ...}
p,.class{attr1:val1; attr2:val2; ...} /*用逗号分隔的选择器列表*/

/*子代选择器, '>' 分隔*/
div > span{attr1:val1; attr2:val2; ...} /*<div>的直接子元素<span>*/

/*后代选择器, 空格分隔*/
div span{attr1:val1; attr2:val2; ...} /*<div>的间接子元素<span>*/

/*伪类选择器*/
/*链接伪类*/
:link{} /*未访问过的链接*/
:visited{} /*已访问过的链接*/
/*动态伪类*/
:hover{} /*鼠标悬停*/
:active{} /*点击链接*/
:focuse{} /*表单项获取焦点*/
```

- 元素选择器: 对当前页面所有对应同名的元素生效

- 类选择器: 根据元素中的类名对元素进行筛选

  ```html
  <p class="class1 class2">p1</p> <!--可以定义多个类名-->
  <p class="class2 class3">p2</p>
  <p class="class3">p3</p>
  ```

  ```css
  .class2{} /*作用于p1和p2*/ 
  ```

- id选择器: 根据元素中的id对标签进行筛选

- 属性选择器: 作用于特定的属性

- 伪类选择器: 对于超链接等元素附加动态效果如鼠标悬停变色等.

- 后代选择器: 选择某一类元素下的特定的某类元素进行筛选
#### 选择器的优先级

| 选择器类型            | 优先级权值 |
| ---------------------| ---------- |
| 元素选择器            | 0, 0, 0, 1 |
| 类选择器 & 伪类选择器 | 0, 0, 1, 0 |
| id选择器              | 0, 1, 0, 0 |
| 内联样式              | 1, 0, 0, 0 |

- 权值相加,较大者优先,如果权值相同,后定义的优先.
- 权值会根据选择器的特殊性逐渐增大,在html的编写中,元素最普遍,其次是类(隶属于统一类的标签可以有多个),最特殊的是id(通常具有唯一性),越特殊的选择器具有越大的权值,便于作者控制.

### 框模型(盒子模型)



- padding 内边距 | margin 外边距
  - 参数
    - 1个参数: 4边统一参数
      - padding/margin-left/right/top/bottom: 指定某一间距
    - 2个参数: 1对应上下,2对应左右
    - 4个参数: 分别对应 **上 右 下 左**.

### CSS flex布局

flex全称flexbox, 即弹性布局,是横向或纵向的一维的布局模型,任何容器都可以指定位flex布局.

![image-20220108231507277](res/image-20220108231507277.png)

<center>
    Flex容器
</center>

- 注意这里由于元素是横向排列,故主轴为x轴,交叉轴为y轴,如果元素纵向排列,则主轴为y轴,交叉轴为x轴.

### 浮动

把一个元素浮动起来,会改变该元素本身和在正常布局流中跟随它的其他元素的行为.

这一元素会浮动到左侧或右侧,并从正常布局流中移除,这时候其他的周围内容就会在这个浮动元素的周围环绕.

### 定位

能够把一个元素从它原本在正常布局流中应该在的位置移动到另一个位置.

- position
  - val= **static**(静态,默认位置) | relative(相对) | absolute(绝对) | fixed(固定) | sticky(粘性)
    - relative: 根据原有位置进行top和left的相对偏移
    - absolute: 根据祖先容器中最接近的祖先采用非静态布局的位置进行top和left的相对偏移.
    - fixed: 根据浏览器窗口进行相对偏移.
    - sticky: 用于实现页面滚动需要的偏移.

### flex容器属性

- flex-direction: 控制容器中在主轴上的方向,即元素的排列方向.
  - val=row | row-reverse | column | column-reverse
- flex-wrap: 控制容器的换行与否.
- flex-flow: 上述两种属性的合称.

flex元素属性

- flex-basis: 控制元素在main axis上的大小.

- flex-grow: 控制剩余空间

  - ![image-20220108231951350](res/image-20220108231951350.png)

  - ```css
    .container{
        display: flex;
    }
    .item{
        flex-grow: 1; /*将剩余空间全部分配给item,其余元素的比例默认为0*/
    }
    ```

- flex-shrink: 控制溢出空间

  - ![image-20220108232157017](res/image-20220108232157017.png)

  - 如果发生溢出,flex默认会将所有的元素按同比例进行挤压

  - ```css
    .container{
        display: flex;
        flex-shrink: 0; /*先将默认的分配比例清零*/
    }
    .item{
        flex-grow: 1; /*将溢出空间全部分配给item,使item受到最大的挤压*/
    }
    ```

- flex: 上述三种属性的合称.
