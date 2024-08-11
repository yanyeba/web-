# 为什么学习 JavaScript?

JavaScript 是 web 开发人员必须学习的 3 门语言中的一门：

1. **HTML** 定义了网页的内容
2. **CSS** 描述了网页的布局
3. **JavaScript** 控制了网页的行为

本教程是关于 JavaScript 及介绍 JavaScript 如何与 HTML 和 CSS 一起工作。



# 1 JavaScript 简介

------

JavaScript 是互联网上最流行的脚本语言，这门语言可用于 HTML 和 web，更可广泛用于服务器、PC、笔记本电脑、平板电脑和智能手机等设备。

------

## 1.1 JavaScript 是脚本语言

JavaScript 是一种轻量级的编程语言。

JavaScript 是可插入 HTML 页面的编程代码。

JavaScript 插入 HTML 页面后，可由所有的现代浏览器执行。

JavaScript 很容易学习。

------

## 1.2 您将学到什么

下面是您将在本教程中学到的主要内容。

### 1.2.1 JavaScript：直接写入 HTML 输出流

```javascript
<body>
<p> JavaScript：直接写入 HTML 输出流</p>
<script>
document.write("<h1>这是个标题</h1>")
document.write("<p>这是个段落</p>")
</script>

</body>
```

**您只能在 HTML 输出中使用 document.write。如果您在文档加载后使用该方法，会覆盖整个文档。**



### 1.2.2 JavaScript：对事件的反应


```javascript
<body>
<p>
JavaScript 能够对事件作出反应。比如对按钮的点击：
</p>
<script>
    <button type="button"  onclick="alert('欢迎')">点击</button>
</script>
</body>
```

alert() 函数在 JavaScript 中并不常用，但它对于代码测试非常方便。

onclick 事件只是您即将在本教程中学到的众多事件之一。



### 1.2.3 JavaScript：改变 HTML 内容

使用 JavaScript 来处理 HTML 内容是非常强大的功能。<br>

```javascript
<h1>一段Javascript</h1>
<p id="demo">
    Javascript能修改HTML元素的内容
</p>
<script>
    function myFunction()
    {
        x=document.getElementById("demo"); //查找元素
        x.innerHTML="Hello Javascript";     //修改元素
    }
</script>
<script>
    <button type="button" onClick="myFunction()">点击</button>
</script>
```

您会经常看到 **document.getElementById("*****some id*****")**。这个方法是 HTML DOM 中定义的。

DOM (**D**ocument **O**bject **M**odel)（文档对象模型）是用于访问 HTML 元素的正式 W3C 标准。

您将在本教程的多个章节中学到有关 HTML DOM 的知识。



### 1.2.4 JavaScript：改变 HTML 图像

本例会动态地改变 HTML image 的来源（src）：

```javascript
<script>
function changeImage()
{
    element=document.getElementById('myimage')
    if (element.src.match("bulbon"))
    {
        element.src="/images/pic_bulboff.gif";
    }
    else
    {
        element.src="/images/pic_bulbon.gif";
    }
}
</script>
<img id="myimage" onclick="changeImage()" src="/images/pic_bulboff.gif" width="100" height="180">
```

```
*以上实例中代码* **element.src.match("bulbon")** *的作用意思是：检索* **<img id="myimage" onclick="changeImage()" src="/images/pic_bulboff.gif" width="100" height="180">** *里面 src 属性的值有没有包含* **bulbon** *这个字符串，如果存在字符串* **bulbon***，图片* **src** *更新为* **bulboff.gif***，若匹配不到* **bulbon** *字符串，***src** *则更新为* **bulbon.gif**
```





### 1.2.5 JavaScript：改变 HTML 样式<br>

改变 HTML 元素的样式，属于改变 HTML 属性的变种。

x=document.getElementById("demo")  //找到元素 

x.style.color="#ff0000";           //改变样式



### 1.2.6 JavaScript：验证输入

JavaScript 常用于验证用户的输入。<br>

```javascript
if isNaN(x) {       
    alert("不是数字");  
}                       
```



以上实例只是普通的验证，如果要在生产环境中使用，需要严格判断，**如果输入的空格，或者连续空格 isNaN 是判别不出来的**。可以添加正则来判断（后续章节会说明）：

```javascript
<body>  
<input type="text" id="demo">请输入数字：

<script>

    function yanzheng(){

        var x = document.getElementById("demo").value;
        if(isNaN(x)||x.replace((/(^\s*)|(\s*$)/g,"")=="")){ //replace取代的意思。把空格取代为空
        alert("不是数字");
        }

    }
</script>
<button type="button" onclick="yanzheng()">点击~</button>

</body>    
```



​                 

# 2 JavaScript 用法

HTML 中的 Javascript 脚本代码必须位于 <script> 与 </script> 标签之间。
Javascript 脚本代码可被放置在 HTML 页面的 <body> 和 <head> 部分中。

## 2.1 <script> 标签

如需在 HTML 页面中插入 JavaScript，请使用 <script> 标签。
<script> 和 </script> 会告诉 JavaScript 在何处开始和结束。
<script> 和 </script> 之间的代码行包含了 JavaScript-->

```javascript
<script>
alert("我的第一个 JavaScript");
</script>
```
您无需理解上面的代码。只需明白，浏览器会解释并执行位于 <script> 和 </script>之间的 JavaScript 代码 

## 2.2 body 中的 JavaScript

在本例中，JavaScript 会在页面加载时向 HTML 的 body 写文本：
```javascript
<!DOCTYPE html>
        <html>
        <body>
        .
        .
        <script>
        document.write("<h1>这是一个标题</h1>");
        document.write("<p>这是一个段落</p>");
        </script>
        .
        .
        </body>
        </html>
```

## 2.3 JavaScript 函数和事件

上面例子中的 JavaScript 语句，会在页面加载时执行。
**通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。**
**如果我们把 JavaScript 代码放入函数中，就可以在事件发生时调用该函数。**

## 2.4 在 head 或者 body 的JavaScript

您可以在 HTML 文档中放入不限数量的脚本。
脚本可位于 HTML 的 body 或 head 部分中，或者同时存在于两个部分中。
**通常的做法是把函数放入 head 部分中，或者放在页面底部。这样就可以把它们安置到同一处位置，不会干扰页面的内容。**

### \<head> 中的 JavaScript 函数

```javascript
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</head>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">尝试一下</button>
</body>
</html>
```



### \<body> 中的 JavaScript 函数

```javascript
<!DOCTYPE html>
<html>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">尝试一下</button>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</body>
</html>
```



## 2.5 外部的 JavaScript

也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。
外部 JavaScript 文件的文件扩展名是 .js。
**如需使用外部文件，请在 script 标签的 "src" 属性中设置该 .js 文件：**

```javascript
<!DOCTYPE html>
<html>
<body>

<script src="myScript.js"></script>

</body>
</html>
```


你可以将脚本放置于 head 或者 body中，放在 script 标签中的脚本与外部引用的脚本运行效果完全一致。



# 3 Chrome 浏览器中执行 JavaScript

本章节为大家介绍如何在 Chrome 浏览器上进行 JavaScript 代码的运行与调试。

Chrome 是由 Google 开发的免费网页浏览器，对于前端开发来说（尤其是调试代码）非常方便。

Chrome 官网地址：https://www.google.com/intl/zh-CN/chrome/。

我们在 Chrome 浏览器中可以通过按下 <kbd>F12</kbd> 按钮或者右击页面，选择"**检查**"来开启开发者工具。

![img](https://www.runoob.com/wp-content/uploads/2020/11/2FC7724A-4281-41C0-94F5-0DAE2D9D7C14.jpg)

也可以在右上角菜单栏选择 "更多工具"=》"开发者工具" 来开启：

![img](https://www.runoob.com/wp-content/uploads/2020/11/62B70027-DD24-4F04-8040-2DB58D1EDCFC.jpg)

## 3.1 Console 窗口调试 JavaScript 代码

打开开发者工具后，我们可以在 Console 窗口调试 JavaScript代码，如下图：

![img](https://www.runoob.com/wp-content/uploads/2020/11/93B1E50A-D2D9-4FB4-B458-D50045FDE599.jpg)

上图中我们在<kbd> ></kbd> 符号后输入我们要执行的代码 <kbd>console.log("runoob")</kbd>，按回车后执行。

我们也可以在其他地方复制一段代码过来执行，比如复制以下代码到 Console 窗口，按回车执行：

```
console.log("runoob-1")
console.log("runoob-2")
```

![img](https://www.runoob.com/wp-content/uploads/2020/11/3F6D97EB-2E51-47AA-919D-79EE62DC14DA.jpg)

清空 Console 窗口到内容可以按以下按钮：

![img](https://www.runoob.com/wp-content/uploads/2020/11/C1A3FF50-1C1C-463E-B12C-D7D8735F6844.jpg)

## 3.2、Chrome snippets 小脚本

我们也可以在 Chrome 浏览器中创建一个脚本来执行，在开发者工具中点击 Sources 面板，选择 Snippets 选项卡，在导航器中右击鼠标，然后选择 Create new snippet 来新建一个脚本文件：

![img](https://www.runoob.com/wp-content/uploads/2020/11/8C18C75F-6C15-4B7F-8C66-122D1D23C14E.jpg)



如果你没看到 Snippets ，可以点下面板上到<kbd> **>>**</kbd> 就能看到了。

![img](https://www.runoob.com/wp-content/uploads/2020/11/9F5F8D84-9C0D-4F6B-98AF-8B9349118297.jpg)



点击 Create new snippet 后，会自动创建一个文件，你只需在右侧窗口输入以下代码，然后按 Command+S（Mac）或 Ctrl+S（Windows 和 Linux）保存更改即可。

```
console.log("runoob-1")
console.log("runoob-2")

```

保存后，右击文件名，选择 "Run" 执行代码：

![img](https://www.runoob.com/wp-content/uploads/2020/11/0DBBF606-1F97-4861-B690-1DBED83A0E5E.jpg)

# 4 JavaScript 输出

**JavaScript 没有任何打印或者输出的函数。**

## 4.1 JavaScript 显示数据

JavaScript 可以通过不同的方式来输出数据：

- 使用<kbd> window.alert() </kbd>弹出**警告框**。
- 使用 <kbd>document.write() </kbd>方法**将内容写到 HTML 文档中。**
-  使用<kbd> innerHTML</kbd> **写入到 HTML 元素**。
- 使用 <kbd>console.log() </kbd>**写入到浏览器的控制台**。

## 4.2.使用 window.alert() 

你可以弹出警告框来显示数据：

```javascript
<!DOCTYPE html>
<html>
<body>

<h1>我的第一个页面</h1>
<p>我的第一个段落。</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```



## 4.3 操作 HTML 元素

如需从 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。

请使用 "id" 属性来标识 HTML 元素，并 innerHTML 来获取或插入元素内容：

```javascript
<!DOCTYPE html><html>
<body>

<h1>我的第一个 Web 页面</h1>

	<p id="demo">我的第一个段落</p>

<script>
	document.getElementById("demo").innerHTML = "段落已修改。";
</script>

</body>
</html>
```

以上 JavaScript 语句（在 <script> 标签中）可以在 web 浏览器中执行：
**document.getElementById("demo") **是使用 id 属性来查找 HTML 元素的 JavaScript 代码 。
**innerHTML = "段落已修改。**" 是用于修改元素的 HTML 内容(innerHTML)的 JavaScript 代码。

## 4.4 在本教程中, 我们将使用上面描述的方法来输出：

在大多数情况下，在本教程中，我们将使用上面描述的方法来输出：

上面的例子直接把 id="demo" 的 p 元素写到 HTML 文档输出中：



## 4.5 写到 HTML 文档

出于测试目的，您可以将JavaScript直接写在HTML 文档中：

使用 document.write() 方法将内容写到 HTML 文档中。

```javascript
<!DOCTYPE html><html>
<body><h1>我的第一个 Web 页面</h1>
	<p>我的第一个段落。</p>
	<script>document.write(Date());
</script>

</body>
</html>
```

使用 document.write() 可以向文档写入内容。

**如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖。**



## 4.6 写到控制台

如果您的浏览器支持调试，你可以使用 **console.log() **方法在浏览器中显示 JavaScript 值。

浏览器中使用 F12 来启用调试模式， 在调试窗口中点击 "Console" 菜单。

```javascript
<!DOCTYPE html>
<html>
<body>
<h1>我的第一个 Web 页面</h1>
<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>

</body>
</html>
```

实例 console 截图：

![img](https://www.runoob.com/wp-content/uploads/2013/08/console-log.jpg)

# 5 JavaScript 语法

JavaScript 是一个程序语言。语法规则定义了语言结构。



## 5.1 JavaScript 语法

JavaScript 是一个脚本语言。

它是一个轻量级，但功能强大的编程语言。



### 5.2 JavaScript 字面量

在编程语言中，一般固定值称为字面量，如 3.14。

### 5.2.1 数字（Number）字面量 

可以是整数或者是小数，或者是科学计数(e)。

```
3.14
1001
123e5
```

```javascript
<p id="demo"></p>
<script>
    document.getElementById("demo").innerHTML = 12e5;
</script>
```



### 5.2.2字符串（String）

字面量 可以使用单引号或双引号:

```
"John Doe"
'John Doe'
```

```javascript
<p id="dem"></p>
<script>
    document.getElementById("dem").innerHTML = "john"
</script>
```



### 5.2.3表达式字面量 用于计算：

```javascript
<p id="de"></p>
<script>
    document.getElementById("de").innerHTML = 5 * 6;
</script>
```



### 5.2.4 数组（Array）字面量 

定义一个数组：

```
[40, 100, 1, 5, 25, 10]
```

### 5.2.5 对象（Object）字面量 

定义一个对象：

```javascript
{firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}
```

### 5.2.6 函数（Function）字面量 

定义一个函数：

```javascript
function myFunction(a, b) { return a * b;}
```



## 5.3 JavaScript 变量

在编程语言中，变量用于存储数据值。

JavaScript 使用关键字<kbd> var</kbd> 来定义变量， 使用等号来为变量赋值：

```javascript
<p id="d"></p>
<script>
    var  length;
    length = 6
    document.getElementById("d").innerHTML = length
</script>
```

变量可以通过变量名访问。在指令式语言中，变量通常是可变的。字面量是一个恒定的值。

**提示：变量是一个名称。字面量是一个值。**



## 5.4.JavaScript 操作符

JavaScript使用 算术运算符 来计算值:

```javascript
<p id="z"></p>
<script>
    document.getElementById("z").innerHTML = (5 + 6) * 10;
</script>
```



### 5.4.1 JavaScript使用赋值运算符给变量赋值：

```javascript
<p id="zi"></p>
<script>
    var x, y, z;
    x = 5;
    y = 6;
    z = (x + y) * 10;
    document.getElementById("zi").innerHTML = z;
</script>
```



JavaScript语言有多种类型的运算符：

  类型	      |       实例    |          	描述
-|-|-
赋值，算术和位运算符|	=  +  -  *  /	|在 JS 运算符中描述
条件，比较及逻辑运算符	|==  != <  > 	|在 JS 比较运算符中描述

## 5.5 JavaScript 语句

在 HTML 中，JavaScript 语句用于向浏览器发出命令。
语句是用分号分隔：

```
x = 5 + 6;
y = x * 10;
```



## 5.6.JavaScript 关键字

JavaScript 关键字用于标识要执行的操作。

和其他任何编程语言一样，JavaScript 保留了一些关键字为自己所用。

**var 关键字**告诉浏览器**创建一个新的变量：**

JavaScript 同样保留了一些关键字，这些关键字在当前的语言版本中并没有使用，但在以后 JavaScript 扩展中会用到。
以下是 JavaScript 中最重要的保留关键字（按字母顺序）：

abstract	|else	|instanceof	|super
-|-|-|-
boolean	|enum|	int|	switch
break|	export	|interface	|synchronized
byte	|extends|	let	|this
case|	false|	long|	throw
catch	|final	|native|	throws
char	|finally	|new|	transient
class|	float	|null	|true
const|	for|	package|	try
continue|	function	|private|	typeof
debugger	|goto	|protected|	var
default	|if	|public	|void
delete	|implements|	return	|volatile
do	|import	|short|	while
double|	in|	static	|with



## 5.7 JavaScript 注释

不是所有的 JavaScript 语句都是"命令"。双斜杠 // 后的内容将会被浏览器忽略：
// 我不会执行

JavaScript 数据类型

JavaScript 有多种数据类型：数字，字符串，数组，对象等等：

```javascript
var length = 16;                                  // Number 通过数字字面量赋值<br>
var points = x * 10;                              // Number 通过表达式字面量赋值<br>
var lastName = "Johnson";                         // String 通过字符串字面量赋值<br>
var cars = ["Saab", "Volvo", "BMW"];              // Array  通过数组字面量赋值<br>
var person = {firstName:"John", lastName:"Doe"};  // Object 通过对象字面量赋值<br>
```



## 5.8 数据类型的概念

编程语言中，数据类型是一个非常重要的内容。

为了可以操作变量，了解数据类型的概念非常重要。

如果没有使用数据类型，以下实例将无法执行：

```
16 + "Volvo"
```

16 加上 "Volvo" 是如何计算呢? 以上会产生一个错误还是输出以下结果呢？

```
"16Volvo"
```

你可以在浏览器尝试执行以上代码查看效果。



## 5.9.JavaScript 函数

JavaScript 语句可以写在函数内，函数可以重复引用：
**引用一个函数 = 调用函数(执行函数内的语句)。**

```
function myFunction(a, b) {      
    return a * b// 返回 a 乘以 b 的结果
}   
```



## 5.10.JavaScript 字母大小写

JavaScript 对大小写是敏感的。

当编写 JavaScript 语句时，请留意是否关闭大小写切换键。

函数 getElementById 与 getElementbyID 是不同的。

同样，变量 myVariable 与 MyVariable 也是不同的。



## 5.11.JavaScript 字符集

JavaScript 使用 **Unicode 字符集。**

Unicode 覆盖了所有的字符，包含标点等字符。

# 6 JavaScript 语句

JavaScript 语句向浏览器发出的命令。语句的作用是告诉浏览器该做什么。



## 6.1.JavaScript 语句

JavaScript 语句是发给浏览器的命令。

这些命令的作用是告诉浏览器要做的事情。

下面的 JavaScript 语句向 id="demo" 的 HTML 元素输出文本 "你好 Dolly" ：

```javascript
<p id="demo"></p>
<script>
    document.getElementById("demo").innerHTML = "你好 Dolly";
</script>
```

## 6.2 分号 ;

分号用于**分隔 JavaScript 语句**。

通常我们在每条可执行的**语句结尾添加分号。**

使用分号的另一用处是**在一行中编写多条语句。**
```
a = 5;
b = 6;
c = a + b;
或者写成：
a = 5; b = 6; c = a + b;
```



## 6.3 JavaScript 代码

JavaScript 代码是 JavaScript 语句的序列。
浏览器按照编写顺序依次执行每条语句。
本例向网页输出一个标题和两个段落：

```javascript
<p id="dem"></p>
<p id="de"></p>
<script>
    document.getElementById("dem").innerHTML = "hello"
    document.getElementById("de").innerHTML = "世界"
</script>
```



## 6.4 JavaScript 代码块

JavaScript 可以分批地组合起来。
代码块以**左花括号开始，以右花括号结束**。
**代码块的作用是一并地执行语句序列**。
本例向网页输出一个标题和两个段落：

```javascript
<p id="z"></p>
<p id="zi"></p>
<script>
    function myFuntion()
    {
        document.getElementById("z").innerHTML ="HELLO";
        document.getElementById("zi").innerHTML ="世界";
    }
</script>
```



## 6.5 JavaScript 语句标识符

JavaScript 语句通常以一个 **语句标识符 **为开始，并执行该语句。

语句标识符是保留关键字不能作为变量名使用。

下表列出了 JavaScript 语句标识符 (关键字) ：

语句	|描述
-|-
break	|用于跳出循环。
catch	|语句块，在 try 语句块执行出错时执行 catch 语句块。
continue	|跳过循环中的一个迭代。
do ... while	|执行一个语句块，在条件语句为 true 时继续执行该语句块。
for	|在条件语句为 true 时，可以将代码块执行指定的次数。
for ... in	|用于遍历数组或者对象的属性（对数组或者对象的属性进行循环操作）。
function	|定义一个函数
if ... else	|用于基于不同的条件来执行不同的动作。
return	|退出函数
switch	|用于基于不同的条件来执行不同的动作。
throw	|抛出（生成）错误 。
try	|实现错误处理，与 catch 一同使用。
var	|声明一个变量。
while	|当条件语句为 true 时，执行语句块。



## 6.6.空格

JavaScript 会忽略多余的空格。您可以向脚本添加空格，来提高其可读性。下面的两行代码是等效的：
```
var person="runoob";
var person = "runoob";
```



## 6.7.对代码行进行折行(换行)

您可以在文本字符串中**使用反斜杠对代码行进行换行**。下面的例子会正确地显示：

实例
```javascript
document.write("你好 \
世界!");
```



# 7 JavaScript 变量

变量是用于存储信息的"容器"。变量是个名词
```
var x=5;
var y=6;
var z=x+y;
```

就像代数那样

x=5
y=6
z=x+y

在代数中，我们使用字母（比如 x）来保存值（比如 5）。

通过上面的表达式 z=x+y，我们能够计算出 z 的值为 11。

**在 JavaScript 中，这些字母被称为变量。**

**可以把变量看做存储数据的容器。**



## 7.1 JavaScript 变量

与代数一样，JavaScript 变量可用于存放值（比如 x=5）和表达式（比如 z=x+y）。

变量可以使用短名称（比如 x 和 y），也可以使用描述性更好的名称（比如 age, sum, totalvolume）。

- 变量**必须以字母开头**

- 变量**也能以 $ 和 _ 符号开头**（不过我们不推荐这么做）

- 变量名称对**大小写敏感**（y 和 Y 是不同的变量）

  

**JavaScript 语句和 JavaScript 变量都对大小写敏感。**



## 7.2 javaScript 数据类型

JavaScript 变量还能保存其他数据类型，比如文本值 (name="Bill Gates")。

在 JavaScript 中，类似 "Bill Gates" 这样一条文本被称为字符串。

JavaScript 变量有很多种类型，但是现在，我们只关注数字和字符串。

**当您向变量分配文本值时，应该用双引号或单引号包围这个值。**

**当您向变量赋的值是数值时，不要使用引号**。如果您用引号包围数值，该值会被作为文本来处理。

```javascript
var pi=3.14;
// 如果你熟悉 ES6，pi 可以使用 const 关键字，表示一个常量
// const pi = 3.14;
var person="John Doe";
var answer='Yes I am!';
```



## 7.3 声明（创建） JavaScript 变量

在 JavaScript 中**创建变量通常称为"声明"变量**。
我们使用 var 关键词来声明变量：

```
var carname;
```

变量声明之后，该变量是空的（它没有值）。



如需向变量赋值，请使用等号：

```
carname="Volvo";
```



不过，您也可以在声明变量时对其赋值：
```
var carname="Volvo";
```



我们创建了名为 carname 的变量，并向其赋值 "Volvo"，然后把它放入 id="demo" 的 HTML 段落中：
实例

```javascript
var carname="Volvo";
document.getElementById("demo").innerHTML=carname;
```



## 7.4.一条语句，多个变量

您可以在一条语句中声明很多变量。该语句以 var 开头，并使用逗号分隔变量即可：

```javascript
var lastname="Doe", age=30, job="carpenter";
```

声明也可横跨多行：

```javascript
var lastname="Doe",
age=30,
job="carpenter";
```

一条语句中声明的多个变量不可以同时赋同一个值:

```javascript
var x,y,z=1;
x,y 为 undefined， z 为 1。
```



## 7.5.Value = undefined

在计算机程序中，经常会声明无值的变量。**未使用值来声明的变量，其值实际上是 undefined**。
在执行过以下语句后，变量 carname 的值将是 undefined：



## 7.6 重新声明 JavaScript 变量

如果重新声明 JavaScript 变量，该变量的值不会丢失：
在以下两条语句执行后，变量 carname 的值依然是 "Volvo"：
var carname="Volvo";
var carname;

## 7.7 JavaScript 算数

您可以通过 JavaScript 变量来做算数，使用的是 = 和 + 这类运算符：

```javascript
<p id="pa"></p>
<script>
    var y = 5;
    x = y + 2;
    document.getElementById("pa").innerHTML = x;
</script>
```



# 8.JavaScript 数据类型

**值类型(基本类型**)：字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）、Symbol。
**引用数据类型（对象类型）**：对象(Object)、数组(Array)、函数(Function)，还有两个特殊的对象：正则（RegExp）和日期（Date）

![img](https://www.runoob.com/wp-content/uploads/2013/08/Javascript-DataType.png)**Symbol 是 ES6 引入了一种新的原始数据类型，表示独一无二的值。**



## 8.1.JavaScript 拥有动态类型

JavaScript 拥有动态类型。这意味着相同的变量可用作不同的类型：

```javascript
var x;               // x 为 undefined
var x = 5;           // 现在 x 为数字
var x = "John";      // 现在 x 为字符串
```



变量的数据类型可以使用 typeof 操作符来查看：
```java
typeof "John"                // 返回 string
typeof 3.14                  // 返回 number
typeof false                 // 返回 boolean
typeof [1,2,3,4]             // 返回 object
typeof {name:'John', age:34} // 返回 object
```



## 8.2.JavaScript 字符串

字符串是存储字符（比如 "Bill Gates"）的变量。
字符串可以是引号中的任意文本。您可以使用单引号或双引号：

```javascript
var carname="Volvo XC60";
var carname='Volvo XC60';
```

您可以在字符串中使用引号，只要不匹配包围字符串的引号即可：

```javascript
var answer="It's alright";
var answer="He is called 'Johnny'";
var answer='He is called "Johnny"';
```



## 8.3. JavaScript 数字

JavaScript 只有一种数字类型。数字可以带小数点，也可以不带：

```javascript
var x1=34.00;      //使用小数点来写
var x2=34;         //不使用小数点来写
```



极大或极小的数字可以通过科学（指数）计数法来书写：
```javascript
var y=123e5;      // 12300000
var z=123e-5;     // 0.00123
```



## 8.4 JavaScript 布尔

布尔（逻辑）只能有两个值：true 或 false。

```java
var x=true;
var y=false;
```



## 8.5 JavaScript 数组

下面的代码创建名为 cars 的数组：

```javascript
var cars=new Array();
cars[0]="Saab";
cars[1]="Volvo";
cars[2]="BMW";
```

或者 (condensed array):

```javascript
var cars=new Array("Saab","Volvo","BMW");
```


或者 (literal array):

```javascript
<p id="mode"></p>
<script>
    var cars=["san", "vo", "Bm"];
    document.getElementById("mode").innerHTML = cars;
</script>
```



**数组下标是基于零的，所以第一个项目是 [0]，第二个是 [1]，以此类推**。

## 8.6 JavaScript 对象

**对象由花括号分隔**。在括号内部，**对象的属性以名称和值对的形式 (name : value) 来定义。属性由逗号分隔：**

```javascript
var person={firstname:"John", lastname:"Doe", id:5566};
```

上面例子中的对象 (person) 有三个属性：firstname、lastname 以及 id。
空格和折行无关紧要。声明可横跨多行：

```javascript
var person={
firstname : "John",
lastname  : "Doe",
id        :  5566
};
```

对象属性有两种寻址方式：

```javascript
name=person.lastname;
name=person["lastname"];
```



## 8.7 Undefined 和 Null

Undefined 这个值表示变量不含有值。
**可以通过将变量的值设置为 null 来清空变量。**



## 8.8 声明变量类型

当您声明新变量时，可以使用关键词 "new" 来声明其类型：
  ```java
    var carname=new String;
      var x=      new Number;
      var y=      new Boolean;
      var cars=   new Array;
      var person= new Object;
  ```

JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。



# 9.JavaScript 对象

**在 JavaScript中，几乎所有的事物都是对象。**

**在 JavaScript 中，对象是非常重要的，当你理解了对象，就可以了解 JavaScript 。**

你已经学习了 JavaScript 变量的赋值。

以下代码为变量 car 设置值为 "Fiat" :

```javascript
var car = "Fiat";
```



对象也是一个变量，但对象可以包含多个值（多个变量），每个值以 name:value 对呈现。

```javascript
var car = {name:"Fiat", model:500, color:"white"};
```

在以上实例中，3 个值 ("Fiat", 500, "white") 赋予变量 car。
	***JavaScript 对象是变量的容器。***



## 9.1.对象定义

你可以使用字符来定义和创建 JavaScript 对象:

```javascript
<p id="mode">创建Javascript对象例子</p>
<script>
    var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
    document.getElementById("mode").innerHTML = person.firstName + "现在" + person.age + "岁";
</script>
```

定义 JavaScript 对象可以跨越多行，空格跟换行不是必须的：

```javascript
var person = {
    firstName:"John",
    lastName:"Doe",
    age:50,
    eyeColor:"blue"
};
```



## 9.2 对象属性

可以说 "**JavaScript 对象是变量的容器**"。

但是，我们通常认为 "JavaScript 对象是键值对的容器"。

键值对通常写法为 **name : value** (键与值以冒号分割)。

**键值对**在 JavaScript 对象通常称为 **对象属性**。

​    	JavaScript 对象是属性变量的容器。



对象键值对的写法类似于：

- PHP 中的关联数组
- Python 中的字典
- C 语言中的哈希表
- Java 中的哈希映射
- Ruby 和 Perl 中的哈希表



## 9.3 访问对象属性

你可以通过两种方式访问对象属性:**person.lastName; 或者 person["lastName"]**

```javascript
<p>;</p>
<p id="demo"></p>
<script>
var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue",
    }
    document.getElementById("demo").innerHTML = person.firstName + "比" + person.lastName
    + "大" + person.age + "岁"
</script>
```



## 9.4 对象方法

**对象的方法定义了一个函数，并作为对象的属性存储**。

对象方法通过添加 () 调用 (作为一个函数)。

该实例**访问了 person 对象的 fullName() 方法:**
name = person.fullName();

```javascript
var person = {
        firstName:"jphe",
        lastName:"Dove",
        age:50,
        eyeColor:"red",
        fullName:function (){
            return this.firstName + "   " + this.lastName
    }
    }
    document.getElementById("demo").innerHTML = person.fullName() //调用属性方法（函数）
	document.getElementById("demo").innerHTML = person.fullNane//访问（查看）属性
```

```javascript
<p>创建和使用对象方法。</p>
<p>对象方法是一个函数定义,并作为一个属性值存储。</p>
<p>如果你要访问 person 对象的 fullName 属性，它将作为一个定义函数的字符串返回：</p>
<p id="demo1"></p>
<p id="demo2"></p>
<script>
    var person={
        firstName: "John",
        lastName : "Doe",
        id : 5566,
        fullName : function ()
        {
            return this.firstName + "" + this.lastName;
        }
    }
    document.getElementById("demo1").innerHTML = "不加括号输出函数表达式" + person.fullName;
    document.getElementById("demo2").innerHTML = "加括号输出函数执行结果" + person.fullName();
</script>
```



## 9.5 访问对象方法

你可以使用以下语法创建对象方法：
```javascript
methodName : function() {
    // 代码
}
```

你可以使用以下语法访问对象方法：
```javascript
objectName.methodName()

document.getElementById("demo").innerHTML = person.fullName() //调用属性方法（函数）
```



通常 fullName() 是作为 person 对象的一个方法， fullName 是作为一个属性。
**如果使用 fullName 属性，不添加 (), 它会返回函数的定义：**

```javascript
objectName.methodName

ocument.getElementById("demo").innerHTML = person.fullNane//访问（查看）属性
```



# 10.JavaScript 函数

函数是由**事件驱动的**或者当它**被调用**时执行的可重复使用的代码块。

```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>测试实例</title>
<script>
function myFunction()
{
    alert("Hello World!");
}
</script>
</head>
 
<body>
<button onclick="myFunction()">点我</button>
</body>
</html>
```





## 10.1.JavaScript 函数语法

函数就是包裹在花括号中的代码块，前面使用了关键词 function：

```javascript
function functionname()
{
    // 执行代码
}
```

**当调用该函数时，会执行函数内的代码。**

可以在某事件发生时直接调用函数（比如当用户点击按钮时），并且可由 JavaScript 在任何位置进行调用。

**JavaScript 对大小写敏感。关键词 function 必须是小写的，并且必须以与函数名称相同的大小写来调用函数**



## 10.2.调用带参数的函数

**在调用函数时，您可以向其传递值，这些值被称为参数。**

这些参数可以在函数中使用。

**您可以发送任意多的参数，由逗号 (,) 分隔：**

```javascript
myFunction(argument1,argument2)
```



**当您声明函数时，请把参数作为变量来声明：**

```javascript
function myFunction(var1,var2)
{
代码
}
```

**变量和参数必须以一致的顺序出现。第一个变量就是第一个被传递的参数的给定的值，以此类推。**


```javascript
<p>点击这个按钮，来调用带参数的函数。</p>
<button onclick="myFunction('Herry potter', 'Wizard')">点击这里</button>

<script>
    function myFunction(name,job){
        alert("welcome" + name + ",the" + job)
    }
</script>
上面的函数在按钮被点击时会提示 "Welcome Harry Potter, the Wizard"。
```


函数很灵活，您可以使用不同的参数来调用该函数，这样就会给出不同的消息：
```javascript
<button onclick="myFunction('Harry Potter','Wizard')">点击这里</button>
<button onclick="myFunction('Bob','Builder')">点击这里</button>
根据您点击的不同的按钮，上面的例子会提示 "Welcome Harry Potter, the Wizard" 或 "Welcome Bob, the Builder"。
```


## 10.3 带有返回值的函数
有时，我们会希望函数将值返回调用它的地方。

通过使用 <kbd>return </kbd>语句就可以实现。

**在使用 return 语句时，函数会停止执行，并返回指定的值。**

语法
```javascript
function myFunction()
{
    var x=5;
    return x;
}
```
上面的函数会返回值 5。

**注意： 整个 JavaScript 并不会停止执行，仅仅是函数。JavaScript 将继续执行代码，从调用函数的地方。**

函数调用将被返回值取代：
```javascript
    var myVar=myFunction();
```
myVar 变量的值是 5，也就是函数 "myFunction()" 所返回的值。

**即使不把它保存为变量，您也可以使用返回值：**
```javascript
    document.getElementById("demo").innerHTML=myFunction();
```
"demo" 元素的 innerHTML 将成为 5，也就是函数 "myFunction()" 所返回的值。


您可以使返回值基于传递到函数中的参数：

计算两个数字的乘积，并返回结果：
```javascript
<p id="demo3"></p>
<script>
    function myFunction(a,b){
        return a * b;
    }
    document.getElementById("demo3").innerHTML = myFunction(4 , 3)
</script>
```

在您仅仅希望退出函数时 ，也可使用 return 语句。返回值是可选的：
```javascript
function myFunction(a,b)
{
    if (a>b)
    {
        return;
    }
    x=a+b
}
```
如果 a 大于 b，则上面的代码将退出函数，并不会计算 a 和 b 的总和。



## 10.4 局部 JavaScript 变量

在 JavaScript 函数内部声明的变量（使用 var）是局部变量，所以只能在函数内部访问它。（该变量的作用域是局部的）。
您可以在不同的函数中使用名称相同的局部变量，因为只有声明过该变量的函数才能识别出该变量。
只要函数运行完毕，本地变量就会被删除。



## 10.5 全局 JavaScript 变量

**在函数外声明的变量是全局变量，网页上的所有脚本和函数都能访问它。**



### 10.6 JavaScript 变量的生存期

JavaScript 变量的生命期从它们被声明的时间开始。
**局部变量会在函数运行以后被删除。**
**全局变量会在页面关闭后被删除。**



## 10.7 向未声明的 JavaScript 变量分配值

如果您把值赋给尚未声明的变量，该变量将被自动作为 window 的一个属性。
这条语句：
carname="Volvo";
将声明 window 的一个属性 carname。
非严格模式下给未声明变量赋值创建的全局变量，是全局对象的可配置属性，可以删除。



# 11 JavaScript 作用域

作用域是可访问变量的集合。



## 11.1 JavaScript 作用域

在 JavaScript 中, ** 对象和函数同样也是变量。**
**在 JavaScript 中, 作用域为可访问变量，对象，函数的集合。**
**JavaScript 函数作用域: 作用域在函数内修改。**

## 11.2 JavaScript 局部作用域
**变量在函数内声明，变量为局部变量，具有局部作用域。**
**局部变量：只能在函数内部访问。**

**因为局部变量只作用于函数内，所以不同的函数可以使用相同名称的变量。**
**局部变量在函数开始执行时创建，函数执行完后局部变量会自动销毁。**

## 11.3 JavaScript 全局变量
**变量在函数外定义，即为全局变量。**
**全局变量有 全局作用域: 网页中所有脚本和函数均可使用。**
```javascript
var carName = " Volvo";
// 此处可调用 carName 变量
function myFunction() {
    // 函数内可调用 carName 变量
}
```

**如果变量在函数内没有声明（没有使用 var 关键字），该变量为全局变量。**

以下实例中 carName 在函数内，但是为全局变量。

实例
```javascript
// 此处可调用 carName 变量

function myFunction() {
    carName = "Volvo";
    // 此处可调用 carName 变量
}
```

## 11.4 JavaScript 变量生命周期
JavaScript 变量生命周期在它声明时初始化。
局部变量在函数执行完毕后销毁。
全局变量在页面关闭后销毁。

## 11.5 函数参数
**函数参数只在函数内起作用，是局部变量**

## 11.6 HTML 中的全局变量
在 HTML 中, **全局变量是 window 对象**，*所以 window 对象可以调用函数内的未声明（未加 var)的局部变量。*

注意：所有数据变量都属于 window 对象。
```javascript
//此处可使用 window.carName

function myFunction() {
    carName = "Volvo";
}
```

## 11.7将函数内的变量暴露给外部作用域
在 JavaScript 中，函数内部的局部变量通常不可以直接被外部作用域访问，但有几种方式可以将函数内的局部变量暴露给外部作用域，具体如下：

    通过全局对象：在函数内部，可以通过将局部变量赋值给 window 对象的属性来使其成为全局可访问的。例如，使用 window.a = a; 语句，可以在函数外部通过 window.a 访问到这个局部变量的值。
    
    定义全局变量：在函数内部不使用 var、let 或 const 等关键字声明变量时，该变量会被视为全局变量，从而可以在函数外部访问。但这种做法通常不推荐，因为它可能导致意外的副作用和代码难以维护。
    
    返回值：可以通过在函数内部使用 return 语句返回局部变量的值，然后在函数外部接收这个返回值。这样，虽然局部变量本身不会被暴露，但其值可以通过函数调用传递到外部。
    
    闭包：JavaScript 中的闭包特性允许内部函数访问外部函数的局部变量。即使外部函数执行完毕后，其局部变量仍然可以被内部函数引用。
    
    属性和方法：定义在全局作用域中的变量和函数都会变成 window 对象的属性和方法，因此可以在调用时省略 window，直接使用变量名或函数名。



# 12.JavaScript事件

HTML 事件是发生在 HTML 元素上的事情。

当在 HTML 页面中使用 JavaScript 时， JavaScript 可以触发这些事件。



## 12.1 HTML 事件

HTML 事件可以是浏览器行为，也可以是用户行为。

以下是 HTML 事件的实例：

- HTML 页面完成加载

- HTML input 字段改变时

- HTML 按钮被点击

  

通常，当事件发生时，你可以做些事情。
**在事件触发时 JavaScript 可以执行一些代码。**
HTML 元素中可以添加事件属性，使用 JavaScript 代码来添加 HTML 元素。

单引号:
```javascript
<some-HTML-element some-event='JavaScript 代码'>
```
双引号:
```javascript
<some-HTML-element some-event="JavaScript 代码">
```

在以下实例中，按钮元素中添加了 onclick 属性 (并加上代码):
```javascript
<button onclick="getElementById('demo').innerHTML = Date()">现在时间</button>
<p id="demo"></p>
```
以上实例中，JavaScript 代码将修改 id="demo" 元素的内容。


在下一个实例中，代码将修改自身元素的内容 (使用 this.innerHTML):
```javascript
<button onclick="this.innerHTML= Date()">现在时间是</button>
	JavaScript代码通常是几行代码。比较常见的是通过事件属性来调用：


<button onclick="displayDate()">现在时间是多少</button>
<script>
    function displayDate(){
        document.getElementById("dem").innerHTML = Date();
    }
</script>
<p id="dem"></p>
```



## 12.2 常见的HTML事件

下面是一些常见的HTML事件的列表:



事件	|描述
-|-
onchange|	HTML 元素改变
onclick	|用户点击 HTML 元素
onmouseover|	鼠标指针移动到指定的元素上时发生
onmouseout|	用户从一个 HTML 元素上移开鼠标时发生
onkeydown|	用户按下键盘按键
onload|	浏览器已完成页面的加载



## 12.3 JavaScript 可以做什么?

事件可以用于处理**表单验证，用户输入，用户行为及浏览器动作:**

- 页面加载时触发事件

- 页面关闭时触发事件

- 用户点击按钮执行动作

- 验证用户输入内容的合法性
  等等 ...

  

可以使用多种方法来执行 JavaScript 事件代码：

- HTML 事件属性可以直接执行 JavaScript 代码
- HTML 事件属性可以调用 JavaScript 函数
- 你可以为 HTML 元素指定自己的事件处理程序
- 你可以阻止事件的发生。



# 13 JavaScript 字符串

JavaScript 字符串用于存储和处理文本。



## 13.1.JavaScript 字符串

字符串可以存储一系列字符，如 "John Doe"。
字符串可以是插入到引号中的任何字符。你可以使用单引号或双引号：
你可以使用索引位置来访问字符串中的每个字符：

```javascript
<p id="demo"></p>
<p id="demo1"></p>
<p id="demo2"></p>
<script>
    var carname= "Volvo XC60";
    var x = 'It\'s alright';    //可以在字符串添加转义字符来使用引号：
    var tex = "ahjcsba"
    var character = carname[2];
    document.getElementById("demo").innerHTML = character;
    document.getElementById("demo1").innerHTML = x;
    document.getElementById("demo2").innerHTML = tex.length; //字符串长度
</script>
```

你可以在字符串中使用引号，字符串中的引号不要与字符串的引号相同:
```javascript
var answer = "It's alright";
var answer = "He is called 'Johnny'";
var answer = 'He is called "Johnny"';
```

你也可以在字符串**添加转义字符来使用引号**：
```javascript
var x = 'It\'s alright';
var y = "He is called \"Johnny\"";
```



## 13.2 字符串长度

可以使用内置属性 **length 来计算字符串的长度**：

```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```



## 13.3 特殊字符

在 JavaScript 中，字符串写在单引号或双引号中。
因为这样，以下实例 JavaScript 无法解析：

```
 "We are the so-called "Vikings" from the north."
```


字符串 "We are the so-called " 被截断。

如何解决以上的问题呢？可以使用反斜杠 (\) 来转义 "Vikings" 字符串中的双引号，如下:
 ```
 "We are the so-called \"Vikings\" from the north."
 ```



 反斜杠是一个**转义字符**。 转义字符将特殊字符转换为字符串字符：
转义字符 (\) 可以用于转义撇号，换行，引号，等其他特殊字符。
下表中列举了在字符串中可以使用转义字符转义的特殊字符：
代码 |输出
-|-
\'	|单引号
\"	|双引号
\\	|反斜杠
\n	|换行
\r	|回车
\t	|tab(制表符)
\b	|退格符
\f	|换页符



## 13.4 字符串可以是对象

通常， JavaScript 字符串是原始值，可以使用字符创建： **var firstName = "John"**
但我们也可以使用 new 关键字将字符串定义为一个对象： **var firstName = new String("John")**

```javascript
var x = "John";
var y = new String("John");
typeof x // 返回 String
typeof y // 返回 Object
```



**不要创建 String 对象。它会拖慢执行速度，并可能产生其他副作用：**

```js
var x = "John";
var y = new String("John");
(x === y) // 结果为 false，因为 x 是字符串，y 是对象
```

=== 为绝对相等，即数据类型与值都必须相等。



## 13.5 字符串属性和方法

原始值字符串，如 "John", 没有属性和方法(因为他们不是对象)。
原始值可以使用 JavaScript 的属性和方法，因为 JavaScript 在执行方法和属性时可以把原始值当作对象。

字符串属性

属性|	描述
-|-
constructor|	返回创建字符串属性的函数
length|	返回字符串的长度
prototype	|允许您向对象添加属性和方法

## 13.6 字符串方法
方法	|描述
-|-
charAt()	|返回指定索引位置的字符
charCodeAt()	|返回指定索引位置字符的 Unicode 值
concat()	|连接两个或多个字符串，返回连接后的字符串
fromCharCode()|	将 Unicode 转换为字符串
indexOf()	|返回字符串中检索指定字符第一次出现的位置
lastIndexOf()|	返回字符串中检索指定字符最后一次出现的位置
localeCompare()	|用本地特定的顺序来比较两个字符串
match()	|找到一个或多个正则表达式的匹配
replace()	|替换与正则表达式匹配的子串
search()	|检索与正则表达式相匹配的值
slice()|	提取字符串的片断，并在新的字符串中返回被提取的部分
split()	|把字符串分割为子字符串数组
substr()|	从起始索引号提取字符串中指定数目的字符
substring()|	提取字符串中两个指定的索引号之间的字符
toLocaleLowerCase()|	根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射
toLocaleUpperCase()|	根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射
toLowerCase()	|把字符串转换为小写
toString()	|返回字符串对象值
toUpperCase()	|把字符串转换为大写
trim()	|移除字符串首尾空白
valueOf()|	返回某个字符串对象的原始值JavaScript 模板字符串
JavaScript |中的模板字符串是一种方便的字符串语法，允许你在字符串中嵌入表达式和变量。



# 14 JavaScript 模板字符串

JavaScript 中的模板字符串是一种方便的字符串语法，允许你在字符串中嵌入表达式和变量。

模板字符串使用反引号 <kbd>**``** </kbd>作为字符串的**定界符分隔的字面量**。

模板字面量是用反引号（<kbd>**`**</kbd>）**分隔的字面量**，允许多行字符串、带嵌入表达式的字符串插值和一种叫带标签的模板的特殊结构。

### 语法

```
`string text`

`string text line 1
 string text line 2`

`string text ${expression} string text`

tagFunction`string text ${expression} string text`
```

参数

- **string text**：将成为模板字面量的一部分的字符串文本。几乎允许所有字符，包括换行符和其他空白字符。但是，**除非使用了标签函数，否则无效的转义序列将导致语法错误。**
- **expression**：要**插入当前位置**的表达式，**其值被转换为字符串**或传递给 tagFunction。
- **tagFunction**：如果指定，将使用模板字符串数组和替换表达式调用它，返回值将成为模板字面量的值。

```js
<p>模板字面量使用反引号 (``) 来定义一个字符串:</p>

<p id="demo"></p>
<script>
let text = `Hello RUNOOB!`;
document.getElementById("demo").innerHTML = text;
</script>
```



模板字符串中可以同时使用单引号和双引号：

```js
let text = `He's often called "Runoob"`;
```



模板字符串还支持多行文本，而无需使用特殊的转义字符：
```js
const multiLineText = `
  This is
  a multi-line
  text.
`;
```
若要转义模板字面量中的反引号（<kbd>`</kbd>），需在反引号之前加一个反斜杠（<kbd> \  </kbd>）。
```js
`\`` === "`"; // true
```

**模板字面量用反引号（`）括起来，而不是双引号（"）或单引号（'）**。

除了普通字符串外，模板字面量还可以包含占位符——一种由美元符号和大括号分隔的嵌入式表达式：${expression}。

字符串和占位符被传递给一个函数（要么是默认函数，要么是自定义函数）。默认函数（当未提供自定义函数时）只执行字符串插值来替换占位符，然后将这些部分拼接到一个字符串中。

模板字符串中允许我们使用变量：

实例
const name = 'Runoob';
const age = 30;
const message = `My name is ${name} and I'm ${age} years old.`;

以上实例中，${name} 和 ${age} 是模板字符串的表达式部分，它们被包含在 ${} 内部，并在运行时求值。

模板字符串允许你在字符串中引用变量、执行函数调用和进行任意的JavaScript表达式。

模板字符串中允许我们使用表达式：

实例
let price = 10;
let VAT = 0.25;

let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;

模板字符串当作 HTML 模板使用：

实例
let header = "";
let tags = ["RUNOOB", "GOOGLE", "TAOBAO"];

let html = `<h2>${header}</h2><ul>`;
for (const x of tags) {
  html += `<li>${x}</li>`;
}

html += `</ul>`;



## 15.JavaScript 运算符

运算符 = 用于赋值。
运算符 + 用于加值。
运算符 = 用于给 JavaScript 变量赋值。
算术运算符 + 用于把值加起来。
```js
<p id="mode"></p>
<p id="mode1"></p>
<p id="mode2"></p>
<p id="mode3"></p>
<p id="mode4"></p>
<p id="mode5"></p>
<p id="mode6"></p>
<script>
    y = 5;
    x = 2;
    z = y + x; //加法
    x1 = y - x; //减法
    x2 = y * x; //乘法
    x3 = y / x; //除法
    x4 = y % x; //取模（余数）
    x5 = ++ y;  //自增(y++)
    x6 = --y;//自减
    document.getElementById("mode").innerHTML = x;
    document.getElementById("mode1").innerHTML = x1;
    document.getElementById("mode2").innerHTML = x2;
    document.getElementById("mode3").innerHTML = x3;
    document.getElementById("mode4").innerHTML = x4;
    document.getElementById("mode5").innerHTML = x5;
    document.getElementById("mode6").innerHTML = x6;
</script>
```

15.1.JavaScript 算术运算符
与/或值之间的算术运算。
y=5，下面的表格解释了这些算术运算符：

运算符	|描述| 	例子	   |     x 运算结果|	y 运算结果|	在线实例
-|-|-|-|-|-
\+	|    加法 |	x=y+2	|    7	 |       5	|实例 »
\-	 |   减法	 |   x=y-2	 |   3	 |       5	|实例 »
\*	 |   乘法	|    x=y*2	|    10	    |    5	|实例 »
/	  |  除法	 |   x=y/2	 |   2.5	|        5|	实例 »
%	|    取模（余数）|	x=y%2|	1	 |       5	|实例 »
++	    |自增	   | x=++y	 |   6	      |  6	|实例 »
|||x=y++|	                 5	|        6	|实例 »
--	   | 自减	    |    x=--y|	4	   |     4	|实例 »
|||x=y--|	                 5	|        4|

## 15.2 JavaScript 赋值运算符

赋值运算符用于给 JavaScript 变量赋值。

给定 x=10 和 y=5，下面的表格解释了赋值运算符：

运算符	|例子 |	等同于|	运算结果|	在线实例
-|-|-|-|-
=	|    x=y	| 	   |    x=5	  |  实例 »
+=	 |   x+=y|	x=x+y	|x=15|	实例 »
-=	  |  x-=y	|x=x-y	|x=5	|    实例 »
*=	 |   x*=y	|x=x*y	|x=50	|实例 »
/=	  |  x/=y	|x=x/y|	x=2	   | 实例 »
%=	  |  x%=y|	x=x%y	|x=0

<p id="coco"></p>
<p id="coco1"></p>
<p id="coco2"></p>
<script>
    x = 10;
    y = 5;
    x1 = y;
    x2 += y;
    x3 -= y;
    document.getElementById("coco").innerHTML = x1;
    document.getElementById("coco1").innerHTML = x2;
    document.getElementById("coco2").innerHTML = x3;
</script>
## 15.3 用于字符串的 + 运算符

+ 运算符用于把文本值或字符串变量加起来（连接起来）。
如需把两个或多个字符串变量连接起来，请使用 + 运算符。

```js
txt1="What a very";
txt2="nice day";
txt3=txt1+txt2;
```



+ 要想在两个字符串之间增加空格，需要把空格插入一个字符串之中：

```js
txt1="What a very ";
txt2="nice day";
txt3=txt1+txt2;
```



## 15.4 对字符串和数字进行加法运算

两个数字相加，返回数字相加的和，如果数字与字符串相加，返回字符串，如下实例：

```js
x=5+5;
y="5"+5;
z="Hello"+5;
```

规则:**如果把数字与字符串相加，结果将成为字符串！**



# 16 JavaScript 比较 和 逻辑运算符

比较和逻辑运算符用于测试 **true 或者 false**。

## 16.1 比较运算符

**比较运算符在逻辑语句中使用，以测定变量或值是否相等。**
x=5，下面的表格解释了比较运算符：

运算符	|  描述	|比较	   |     返回值|	 实例
-|-|-|-|-
==	  |    等于|	x==8	|    false|	实例 »
|||   x==5	   | true	|实例 »
===	|绝对等于（值和类型均相等）|	x==="5"	|false	|实例 »
|||     x===5	|    true|	实例 »
!=	 |   不等于|	x!=8	|    true|	实例 »
!==	 |不绝对等于（值和类型有一个不相等，或两个都不相等）	|x!=="5"|true	|实例 »
|||   x!==5	  |  false	|实例 »
\>	|      大于|	x>8	  |      false	|实例 »
<	|        小于|	x<8	 |       true	|实例 »
\>=	  |  大于或等于	|x>=8|	false|	实例 »
<=	  |  小于或等于	|x<=8|	true|	实例 »
```js
<p id="mode"></p>
<p id="mode1"></p>
<p id="mode2"></p>
<p id="mode3"></p>
<p id="mode4"></p>
<p id="mode5"></p>
<p id="mode6"></p>
<p id="mode7"></p>
<p id="mode8"></p>
<p id="mode9"></p>
<p id="mode10"></p>
<script>
  var x = 5;
  document.getElementById("mode").innerHTML = x==8;     //比较等于返回false
  document.getElementById("mode1").innerHTML = x==5;    //比较等于返回true
  document.getElementById("mode2").innerHTML = x==="5";    //比较绝对等于返回false
  document.getElementById("mode3").innerHTML = x===5;    //比较绝对等于返回true
  document.getElementById("mode4").innerHTML = x!=8;    //比较绝对等于返回true
  document.getElementById("mode5").innerHTML = x !=="5";    //不绝对等于（值和类型有一个不相等，或两个都不相等）true
  document.getElementById("mode6").innerHTML = x !==5;    //不绝对等于（值和类型有一个不相等，或两个都不相等）false
  document.getElementById("mode7").innerHTML = x > 8;    //大于 false
  document.getElementById("mode8").innerHTML = x < 8;    //大于 true
  document.getElementById("mode9").innerHTML = x >= 8;    //大于或者等于 false
  document.getElementById("mode10").innerHTML = x <= 8;    //大于或者等于 false
</script>
```



## 16.2 如何使用

可以在条件语句中使用比较运算符对值进行比较，然后根据结果来采取行动：

```js
if (age<18) x="Too young";
```



## 16.3 逻辑运算符
**逻辑运算符用于测定变量或值之间的逻辑**。
给定 x=6 以及 y=3，下表解释了逻辑运算符：

运算符	|描述	    |例子
-|-|-
&&	   | and	    |(x < 10 && y > 1) 为 true
\|\|	    |or	    |(x==5 \|\| y==5) 为 false
!	    |not	   | !(x==y) 为 true
```js
<p id="coco"></p>
<p id="coco1"></p>
<p id="coco2"></p>
<script>
    var x=6; y=3;
    document.getElementById("coco").innerHTML =(x < 10 && y > 1); //&&表示并且
    document.getElementById("coco1").innerHTML =(x == 5 || y == 5); // ||表示或者
    document.getElementById("coco2").innerHTML =!(x==y); // !表示不是
</script>
```



## 16.4.条件运算符

JavaScript 还包含了基于某些条件对变量进行赋值的条件运算符。
语法

```js
variablename=(condition)?value1:value2
根据条件condition判断。不符合（false）条件执行value2。符合(true)条件执行value1
```

例子：
如果变量 age 中的值小于 18，则向变量 voteable 赋值 "年龄太小"，否则赋值 "年龄已达到"。

```js
voteable=(age<18)?"年龄太小":"年龄已达到";
```



# 17.JavaScript if...Else 语句

条件语句用于**基于不同的条件来执行不同的动作。**

## 17.1 条件语句

通常在写代码时，您总是需要为不同的决定来执行不同的动作。您可以在代码中使用条件语句来完成该任务。
在 JavaScript 中，我们可使用以下条件语句：

-  <kbd>if </kbd>语句 - 只有**当指定条件为 <kbd>true</kbd> 时，使用该语句来执行代码**

-  <kbd>if...else </kbd> 语句 - 当条件为 <kbd> true </kbd> 时执行代码，当条件为  <kbd>false  </kbd>时执行其他代码

-  <kbd>if...else if....else </kbd> 语句- 使用该语句来**选择多个代码块之一**来执行

-  <kbd>switch  </kbd>语句 -  使用该语句来**选择多个代码块之一**来执行

  

## 17.2  if 语句

只有当指定条件为 true 时，该语句才会执行代码。
语法

```js
if (condition)
{
    当条件为 true 时执行的代码
}
```

请使用小写的 if。使用大写字母（IF）会生成 JavaScript 错误！
例子：
```js
if(time<20){
    x = "Good day";
}
```
17.2.if...else 语句
请使用 if....else 语句在条件为 true 时执行代码，在条件为 false 时执行其他代码。
语法

```js
if (condition)
{
    当条件为 true 时执行的代码
}
else
{
    当条件不为 true 时执行的代码
}
```

```js
<script>    
function myFunctio(){
        var x = "";
        var time= new Date().getHours();
        if(time<20){
            x = "Good day";
        }
        else{
            x = "Good evening"
        }
        document.getElementById("demo").innerHTML = x;
    }

</script>
<button type="button" onclick="myFunctio()">点击</button>
```



## 17.3 if...else  if...else 语句

使用 if....else if...else 语句来选择多个代码块之一来执行。
```js
语法
if (condition1)
{
    当条件 1 为 true 时执行的代码
}
else if (condition2)
{
    当条件 2 为 true 时执行的代码
}
else
{
  当条件 1 和 条件 2 都不为 true 时执行的代码
}
```



如果时间小于 10:00，则生成问候 "Good morning"，如果时间大于 10:00 小于 20:00，则生成问候 "Good day"，否则生成问候 "Good evening"：

```js
<script> 
function myFunction(){
        var x = "";
        var time = new Date().getHours();
        if(time<10){
            x = "Good morning";
        }
        else if(10<time<20){
            x = "Gooy day";
        }
        else{
            x = "Good evening";
        }

        document.getElementById("demo").innerHTML = x;
    }
</script>
<button type="button"  onclick="myFunction()">点击提示</button>
```



## 18.JavaScript switch 语句

switch 语句用于基于**不同的条件来执行不同的动作**。

## 18.1.JavaScript switch 语句
请使用 switch 语句来选择要执行的多个代码块之一
语法

```js
switch(n)
{
    case 1:
        执行代码块 1
        break;
    case 2:
        执行代码块 2
        break;
    default:
        与 case 1 和 case 2 不同时执行的代码
}
```

**工作原理**：首先设置表达式 n（**通常是一个变量**）。随后**表达式的值会与结构中的每个 case 的值做比较**。如果存在匹配，则与该 case 关联的代码块会被执行。请使用 break 来阻止代码自动地向下一个 case 运行。

例子：
显示今天的星期名称。请注意 Sunday=0, Monday=1, Tuesday=2, 等等：
```js
<p id="moode"></p>
<script>
    var d=new Date().getDay();
    switch(d)
    {
    case 0:x="今天是星期日";
    break
    case 1:x="今天是星期一";
    break
    case 2:x="今天是星期二";
    break
    case 3:x="今天是星期三";
    break
    case 4:x="今天是星期四";
    break
    case 5:x="今天是星期五";
    break
    case 6:x="今天是星期六";
    break
    }
    document.getElementById("moode").innerHTML = x;
</script>
```


## 18.2 default 关键词
请使用 default 关键词来**规定匹配不存在时做的事情**：
<p id="dome"></p>
如果今天不是星期六或星期日，则会输出默认的消息：
<script>
    var d=new Date().getDay();
    switch (d){
        case 6:x="今天是周六";
        break
        case 0:x="今天是周日"
        break
        default:
            x="又是期待周末的一天"
    }
    document.getElementById("dome").innerHTML = x;


# 19 JavaScript for 循环
**循环可以将代码块执行指定的次数。**

## 19.1 JavaScript 循环
**如果您希望一遍又一遍地运行相同的代码，并且每次的值都不同，那么使用循环是很方便的**。
我们可以这样输出数组的值：
```js
document.write(cars[0] + "<br>");
document.write(cars[1] + "<br>");
document.write(cars[2] + "<br>");
document.write(cars[3] + "<br>");
document.write(cars[4] + "<br>");
document.write(cars[5] + "<br>");
```
使用for循环
```js
<script>
    cars=["python", "java", "c", "c++"]
    for (var i=0;i<cars.length;i++)
    {
        document.write(cars[i] + "<br>");
    }
</script>
```

## 19.2 不同类型的循环
JavaScript 支持不同类型的循环：
- for - 循环代码块一定的次数
- for/in - 循环遍历对象的属性
- while - 当指定的条件为 true 时循环指定的代码块
- do/while - 同样当指定的条件为 true 时循环指定的代码块

## 19.3 For 循环
for 循环是您在希望创建循环时常会用到的工具。
下面是 for 循环的语法：
```js
for (语句 1; 语句 2; 语句 3)
{
    被执行的代码块
}
```
语句 1 （代码块）开始前执行
语句 2 定义运行循环（代码块）的条件
语句 3 在循环（代码块）已被执行之后执行

例子：
```js
<button onclick="myFunction()">按钮</button>
<p id="m" ></p>
<script>
    function myFunction()
    {
        var x=""; 
        for(var i=0; i<5; i++)
        {
        x=x +"该数字为" + i + "<br>";
        }
        document.getElementById("m").innerHTML =x;
    }
</script>
```

从上面的例子中，您可以看到：
Statement 1 在**循环开始之前设置变量 (var i=0)。**
Statement 2 **定义循环运行的条件（i 必须小于 5）。**
Statement 3 在**每次代码块已被执行后增加一个值 (i++)。**

### 19.3.1 语句 1
通常我们会使用语句 1 初始化循环中所用的变量 (var i=0)。
语句 1 是可选的，也就是说不使用语句 1 也可以。
**您可以在语句 1 中初始化任意（或者多个）值**：

```js
for (var i=0,len=cars.length; i<len; i++)
{
    document.write(cars[i] + "<br>");
}
```



**同时您还可以省略语句 1**（比如在循环开始前已经设置了值时）：

```js
var i=2,len=cars.length;
for (; i<len; i++)
{
    document.write(cars[i] + "<br>");
}
```



### 19.3.2 语句 2

**通常语句 2 用于评估初始变量的条件。**
语句 2 同样是可选的。
**如果语句 2 返回 true，则循环再次开始，如果返回 false，则循环将结束**。

**如果您省略了语句 2，那么必须在循环内提供 break**。否则循环就无法停下来。这样有可能令浏览器崩溃。请在本教程稍后的章节阅读有关 break 的内容。

### 19.3.3 语句 3

**通常语句 3 会增加初始变量的值。**
语句 3 也是可选的。
语句 3 有多种用法。增量可以是负数 (i--)，或者更大 (i=i+15)。
**语句 3 也可以省略（比如当循环内部有相应的代码时）**

```js
var i=0,len=cars.length;
for (; i<len; )
{
    document.write(cars[i] + "<br>");
    i++;
}
```



## 19.4 For/In 循环

JavaScript **for/in 语句循环遍历对象的属性：**

实例

```js
    function myFunction(){
        var x = "";
        var txt = "";
        var person={fname:"Bill",lname:"Gates",age:56};

        for (x in person){

        txt = txt + person[x]; // 等号右边的txt是person[前面取出的值] + person[x]就变成个键值对：age:56
        }
        document.getElementById("demo").innerHTML = txt;
    }

```



# 20 JavaScript while 循环

**只要指定条件为 true，循环就可以一直执行代码块。**

## 20.1 while 循环

while 循环会在指定条件为真时循环执行代码块。
语法

```
while (条件)
{
    需要执行的代码
}
```

```js
<button onclick="myFunction()">按钮</button>

<p id="mode"></p>
<script>
    function myFunction() {
        var x="",i=0;
        while(i<5)
        {
            x=x +"the number is" + i + "<br>";
                i++;
        }
        document.getElementById("mode").innerHTML =x;
    }
</script>
```
如果您忘记增加条件中所用变量的值，该循环永远不会结束。这可能导致浏览器崩溃。


## 20.2 do/while 循环
do/while 循环是 while 循环的变体。**该循环会在检查条件是否为真之前执行一次代码块，然后如果条件为真的话，就会重复这个循环。**

```js
do
{
    需要执行的代码
}
while (条件);
```


下面的例子使用 do/while 循环。该循环至少会执行一次，即使条件为 false 它也会执行一次，因为代码块会在条件被测试前执行：

```js
do
{
    x=x + "The number is " + i + "<br>";
    i++;
}
while (i<5);
```

别忘记增加条件中所用变量的值，否则循环永远不会结束！



## 20.3 比较 for 和 while

如果您已经阅读了前面那一章关于 for 循环的内容，您会发现 while 循环与 for 循环很像。

本例中的循环使用 for 循环来显示 cars 数组中的所有值：

```js
cars=["BMW","Volvo","Saab","Ford"];
var i=0;
for (;cars[i];)
{
    document.write(cars[i] + "<br>");
    i++;
}
```



本例中的循环使用 while 循环来显示 cars 数组中的所有值：
```js
cars=["BMW","Volvo","Saab","Ford"];
var i=0;
while (cars[i])
{
    document.write(cars[i] + "<br>");
    i++;
}
```



# 21 JavaScript break 和 continue 语句

**break 语句用于跳出循环。**
**continue 用于跳过循环中的一个迭代。**

## 21.1 break 语句
我们已经在本教程之前的章节中见到过 break 语句。它用于跳出 switch() 语句。
break 语句可用于跳出循环。
**break 语句跳出循环后，会继续执行该循环之后的代码（如果有的话）**：
```js
<button onclick="myFunction()">按钮</button>

<p id="demo"></p>
<script>
    function myFunction(){
        var x=""; i=0;
        for(i=0; i<10; i++){
            if(i==3){
                break
            }
            x=x +"The number is" + i +"<br>"
        }
        document.getElementById("demo").innerHTML=x;
    }
</script>
```

由于这个 if 语句只有一行代码，所以可以省略花括号：
```js
for (i=0;i<10;i++)
{
    if (i==3) break;
    x=x + "The number is " + i + "<br>";
}
```

## 21.2 continue 语句
continue 语句中断当前的循环中的迭代，然后继续循环下一个迭代。 以下例子在值为 3 时，直接跳过：
```js
for (i=0;i<=10;i++)
{
    if (i==3) continue;
    x=x + "The number is " + i + "<br>";
}
```

```js
function myFunction{
var x = "",i = 0;
while (i < 10){
  if (i == 3){
    i++;    //加入i++不会进入死循环
    continue;
  }
  x= x + "该数字为 " + i + "<br>";
  i++;
}
}
<button type="button" onclick="myFunction()">点击循环</button>
```

## 21.3 JavaScript 标签
正如您在 switch 语句那一章中看到的，可以对 JavaScript 语句进行标记。

如需标记 JavaScript 语句，请在语句之前加上冒号：
```js
label:
statements
```

**break 和 continue 语句仅仅是能够跳出代码块的语句。**

语法:
```js
break labelname;
continue labelname;
```
continue 语句（带有或不带标签引用）只能用在循环中。
break 语句（不带标签引用），只能用在循环或 switch 中。
**通过标签引用，break 语句可用于跳出任何 JavaScript 代码块：**


# 22 JavaScript typeof, null, 和 undefined

## 22.1 typeof 操作符
你可以使用 typeof 操作符来检测变量的数据类型。
```js
<p id="demo"></p>
<p id="demo1"></p>
<p id="demo2"></p>
<p id="demo3"></p>
<p id="demo4"></p>
<script>
    x= typeof"john"
    x1= typeof 1
    x2= typeof false
    x3= typeof [1, 2, 3]
    x4= typeof {name:'johe'}
    document.getElementById("demo").innerHTML=x
    document.getElementById("demo1").innerHTML=x1
    document.getElementById("demo2").innerHTML=x2
    document.getElementById("demo2").innerHTML=x3
    document.getElementById("demo4").innerHTML=x4
</script>
```
在JavaScript中，数组是一种特殊的对象类型。 因此 typeof [1,2,3,4] 返回 object。

## 22.2 null
在 JavaScript 中 <kbd> null </kbd>表示 "**什么都没有**"。
null是一个只有一个值的特殊类型。**表示一个空对象引用。**
用 **typeof 检测 null 返回是object。**
你可以设置为 null 来清空对象:
```js
<p id="mode"></p>
<p id="mode1"></p>
<script>
    var person = null;   // 值为 null(空), 但类型为对象;可以设置为 null 来清空对象:
    x = typeof person
    document.getElementById("mode").innerHTML = x

    var person1 = undefined;    //可以设置为 undefined 来清空对象:
    y = typeof person1
    document.getElementById("mode1").innerHTML = y
</script>
```

## 22.3 undefined
在 JavaScript 中, **undefined 是一个没有设置值的变量。**
**typeof 一个没有值的变量会返回 undefined。**
```js
var person;                  // 值为 undefined(空), 类型是undefined
```

**任何变量都可以通过设置值为 undefined 来清空。 类型为 undefined.**
```js
person = undefined;          // 值为 undefined, 类型是undefined
```

## 22.4 undefined 和 null 的区别

**null 和 undefined 的值相等，但类型不等：**
```js
<p id="un"></p>
<p id="un1"></p>
<p id="un2"></p>
<p id="un3"></p>
<script>
    x = typeof undefined    // 数据类型undefined
    y = typeof null         // 数据类型object
    z = null === undefined  // false
    c = null == undefined   // 数据类型也要相同true
    document.getElementById("un").innerHTML= x
    document.getElementById("un1").innerHTML= y
    document.getElementById("un2").innerHTML= z
    document.getElementById("un3").innerHTML= c
```

## 23 JavaScript 类型转换
Number() 转换为数字， String() 转换为字符串， Boolean() 转换为布尔值。

## 23.1 JavaScript 数据类型
在 JavaScript 中有 6 种不同的数据类型：
    string
    number
    boolean
    object
    function
    symbol
3 种对象类型：
    Object
    Date
    Array
2 个不包含任何值的数据类型：
    null
    undefined

23.2.typeof 操作符
你可以使用 typeof 操作符来查看 JavaScript 变量的数据类型。
```js
<p id="demo"></p>
<p id="demo1"></p>
<p id="demo2"></p>
<p id="demo3"></p>
<p id="demo4"></p>
<p id="demo5"></p>
<p id="demo6"></p>
<p id="demo7"></p>
<p id="demo8"></p>
<p id="demo9"></p>
<script>
    x = typeof 'Johe'   // 返回 string
    x1 = typeof 3       // 返回 number
    x2 = typeof NaN     // 返回 number
    x3 = typeof false   // 返回 boolean
    x4 = typeof [1,2,3] // 返回 object
    x5 = typeof {name:"Johe", age:30}   // 返回 object
    x6 = typeof new Date()          // 返回 object
    x7 = typeof function (){}       // 返回 function
    x8 = typeof myCar                // 返回 undefined (如果 myCar 没有声明)
    x9 = typeof null                // 返回 object
    document.getElementById("demo").innerHTML= x;
    document.getElementById("demo1").innerHTML= x1;
    document.getElementById("demo2").innerHTML= x2;
    document.getElementById("demo3").innerHTML= x3;
    document.getElementById("demo4").innerHTML= x4;
    document.getElementById("demo5").innerHTML= x5;
    document.getElementById("demo6").innerHTML= x6;
    document.getElementById("demo7").innerHTML= x7;
    document.getElementById("demo8").innerHTML= x8;
    document.getElementById("demo9").innerHTML= x9;
</script>
```
请注意：
    NaN 的数据类型是 number
    数组(Array)的数据类型是 object
    日期(Date)的数据类型为 object
    null 的数据类型是 object
    未定义变量的数据类型为 undefined
    
如果对象是 JavaScript Array 或 JavaScript Date ，我们就无法通过 typeof 来判断他们的类型，因为都是 返回 object。

## 23.3 constructor 属性
constructor 属性返回所有 JavaScript 变量的构造函数。
Function() { [native code] }: 返回函数Function()；[native code]：构造函数
```js
<p  id="mo"></p>
<script>
document.getElementById("mo").innerHTML=
    "jihe".constructor + "<br>" +   //返回函数 String() { [native code] }
    (3.14).constructor + "<br>" +   //       Number() { [native code] }
    false.constructor + "<br>" +     //       Boolean() { [native code] }
    [1, 2, 3].constructor + "<br>"+  //     String() { [native code] }
    {name:'John', age:34}.constructor + "<br>" + //Object() { [native code] }
    new Date().constructor + "<br>" +   //Date() { [native code] }
    function () {}.constructor + "<br>" //Function() { [native code] }

</script>
```

## 23.4 JavaScript 类型转换
JavaScript 变量可以转换为新变量或其他数据类型：
    通过使用 JavaScript 函数
    通过 JavaScript 自身自动转换
    
```js
<p id="m"></p>
<p id="m1"></p>

<script>
    document.getElementById("m").innerHTML=
        typeof(String(x)) + "<br>" +     // 将变量 x 转换为字符串并返回
        typeof(String(123)) + "<br>" +   // 将数字 123 转换为字符串并返回
        typeof(String(123 + 1))         // 将数字表达式转换为字符串并返回
    //Number 方法 toString() 也是有同样的效果。
    document.getElementById("m1").innerHTML=
        x.toString() + "<br>" +
        (123).toString() + "<br>" + //toString() 方法将数字转换为字符串。
        (100 + 25).toString()
</script>
```
更多数字转换为字符串的方法：
方法	            描述
toExponential()	把对象的值转换为指数计数法。
toFixed()	    把数字转换为字符串，结果的小数点后有指定位数的数字。
toPrecision()	把数字格式化为指定的长度。

## 23.5 将布尔值转换为字符串
全局方法 String() 可以将布尔值转换为字符串。
```js
<p id="mode"></p>
<script>
    document.getElementById("mode").innerHTML=
        typeof String(false) + "<br>" +
        String(false) + "<br>" +  //全局方法 String() 可以将布尔值转换为字符串。
        false.toString()
</script>
```

## 23.6 将日期转换为字符串
Date() 返回字符串。
```js
<p id="cc"></p>
<script>
    document.getElementById("cc").innerHTML=
        Date() + "<br>" +
        String(new Date())  //全局方法 String() 可以将日期对象转换为字符串。
</script>
```
查看更多关于日期转换为字符串的函数：

方法	       |         描述
-|-
getDate()	        |从 Date 对象返回一个月中的某一天 (1 ~ 31)。
getDay()	        |从 Date 对象返回一周中的某一天 (0 ~ 6)。
getFullYear()	    |从 Date 对象以四位数字返回年份。
getHours()	        |返回 Date 对象的小时 (0 ~ 23)。
getMilliseconds()	|返回 Date 对象的毫秒(0 ~ 999)。
getMinutes()	    |返回 Date 对象的分钟 (0 ~ 59)。
getMonth()	        |从 Date 对象返回月份 (0 ~ 11)。
getSeconds()	    |返回 Date 对象的秒数 (0 ~ 59)。
getTime()	        |返回 1970 年 1 月 1 日至今的毫秒数。

## 23.7 将字符串转换为数字
全局方法 Number() 可以将字符串转换为数字。
字符串包含数字(如 "3.14") 转换为数字 (如 3.14).
空字符串转换为 0。
其他的字符串会转换为 NaN (不是个数字)。
```js
<p id="xx"></p>
<script>
    document.getElementById("xx").innerHTML=
        Number("3.14") + "<br>" +
        Number("")  + "<br>" +  // 返回 0
        Number(" ") + "<br>" +  // 返回 0
        Number("99 88")         // 返回 NaN
</script>
```
查看到更多关于字符串转为数字的方法：
方法	  |          描述
-|-
parseFloat()	|解析一个字符串，并返回一个浮点数。
parseInt()	   | 解析一个字符串，并返回一个整数。



## 23.8 一元运算符 +

**Operator + 可用于将变量转换为数字：**

```js
<p id="xxx"></p>
<script>
    document.getElementById("xxx").innerHTML=
        // Operator + 可用于将变量转换为数字：
        typeof( y="5") +" <br>" +
        typeof( x= + y) + "<br>" +
        //如果变量不能转换，它仍然会是一个数字，但值为 NaN (不是一个数字):
        typeof (z = "johe") + "<br>" +
        typeof (z1 = + z)
</script>
```
## 23.9 将布尔值转换为数字
全局方法 Number() 可将布尔值转换为数字。
```js
Number(false)     // 返回 0
Number(true)      // 返回 1
```

## 23.10 将日期转换为数字

全局方法 Number() 可将日期转换为数字。
日期方法 getTime() 也有相同的效果。
```js
<p id="z"></p>
<script>
    d= new Date();
    d1= Number(d)   //全局方法 Number() 可将日期转换为数字。
    d2= d.getTime() //日期方法 getTime() 也有相同的效果。
    document.getElementById("z").innerHTML=
        typeof d1 + "<br>" +
        d2
</script>
```

## 23.11 自动转换类型
当 JavaScript 尝试操作一个 "错误" 的数据类型时，会自动转换为 "正确" 的数据类型。
以下输出结果不是你所期望的：
```js
<p id="zz"></p>
<script>
    document.getElementById("zz").innerHTML=
        (5 + null) + "<br>" + // 返回 5         null 转换为 0
        ("5" + null) + "<br>" + // 返回"5null"   null 转换为 "null"
        ("5" + 1) + "<br>" +    // 返回 "51"      1 转换为 "1"
        ("5" - 1) + "<br>"       // 返回 4         "5" 转换为 5
</script>
```

## 23.12 自动转换为字符串

当你尝试输出一个对象或一个变量时 JavaScript 会自动调用变量的 **toString() **方法：
```js
document.getElementById("demo").innerHTML = myVar;

myVar = {name:"Fjohn"}  // toString 转换为 "[object Object]"
myVar = [1,2,3,4]       // toString 转换为 "1,2,3,4"
myVar = new Date()      // toString 转换为 "Sun Mar 24 2024 16:08:52 GMT+0800 (中国标准时间)"
```

## 23.13 下表展示了使用不同的数值转换为数字(Number), 字符串(String), 布尔值(Boolean):

原始值	  |  转换为数字	|转换为字符串	|转换为布尔值	|实例
-|-|-|-|-
false	 |   0	      |  "false"	 |     false	|尝试一下 »
true	 |   1	     |   "true"	     |   true	|尝试一下 »
0	     |   0	     |   "0"	     |       false	|尝试一下 »
1	     |  1	     |  "1"	         |  true	|尝试一下 »
"0"	     |   0	     |   "0"	     |      true	|尝试一下 »
"000"	 |   0	    |    "000"	    |    true	|尝试一下 »
"1"	      |  1	     |   "1"	    |        true	|尝试一下 »
NaN	     |   NaN	 |       "NaN"	 |       false	|尝试一下 »
Infinity|	Infinity|	"Infinity"	 |   true	|尝试一下 »
-Infinity|	-Infinity|	"-Infinity"|	    true	|尝试一下 »
""	 |       0	    |    ""	    |        false	|尝试一下 »
"20"	|    20	    |    "20"	 |       true	|尝试一下 »
"Runoob"|	NaN	     |   "Runoob"	|    true	|尝试一下 »
[ ]	  |      0	    |    ""	    |        true	|尝试一下 »
[20]	|    20	    |    "20"	 |      true	|尝试一下 »
[10,20]	|    NaN	|        "10,20"	|     true	|尝试一下 »
["Runoob"]|	NaN||	        "Runoob"|	    true|	尝试一下 »
["Runoob","Google"]|	NaN|	"Runoob,Google"	|true	|尝试一下 »
function(){}|	NaN	   | "function(){}"|	true|	尝试一下 »
{ }	  |      NaN	|    "[object Object]"|	true	|尝试一下 »
null	|    0	    |    "null"	  |      false|	尝试一下 »
undefined|	NaN	    |    "undefined"|	    false|



# 24 JavaScript 正则表达式（re）

正则表达式（英语：Regular Expression，在代码中常简写为regex、regexp或RE）使用单个字符串来描述、匹配一系列符合某个句法规则的字符串搜索模式。
搜索模式可用于文本搜索和文本替换。

## 24.1.什么是正则表达式？
正则表达式是**由一个字符序列形成的搜索模式**。
当你在文本中搜索数据时，你可以用**搜索模式来描述你要查询的内容**。
正则表达式可以是**一个简单的字符，或一个更复杂的模式。**
正则表达式可用于**所有文本搜索和文本替换的操作**。



<span style="color:red; font-size:25px">**语法：**</span>
```js
/正则表达式主体/修饰符(可选)
```
其中修饰符是可选的。
```js
var patt = /runoob/i
```
实例解析：
```js
/runoob/i  是一个正则表达式。
runoob  是一个正则表达式主体 (用于检索)。
i  是一个修饰符 (搜索不区分大小写)。
```


## 24.2 使用字符串方法
在 JavaScript 中，正则表达式通常用于两个字符串方法 : **search() **和 **replace()**。
**search() 方法用于检索字符串中指定的子字符串**，或检索与正则表达式相匹配的子字符串，并**返回子串的起始位置。**
**replace()** 方法用于**在字符串中用一些字符串替换另一些字符串**，或替换一个与正则表达式匹配的子串。

```js
<p id="demo"></p>
<script>
    var str = "visit runoob"
    var n =str.search(/runoob/i)    //使用正则表达式搜索 "Runoob" 字符串，且不区分大小写：
    var c =str.search("runoob")     //search 方法可使用字符串作为参数。字符串参数会转换为正则表达式：
    document.getElementById("demo").innerHTML=
        n + "<br>" + c;
</script>
```

## 24.3 search() 方法使用字符串
search 方法可使用字符串作为参数。字符串参数会转换为正则表达式：
```js
var str = "Visit Runoob!";
var n = str.search("Runoob");
```

## 24.4 replace() 方法使用正则表达式
使用正则表达式且不区分大小写将字符串中的 Microsoft 替换为 Runoob :<br>
```js
<button onclick="myFunction()">按钮</button>
<p id="dem">Visit Microsoft!</p>
<script>
    function myFunction(){
        var str = document.getElementById("dem").innerHTML;
        var txt = str.replace(/microsoft/i,"Runoob")
        document.getElementById("dem").innerHTML=txt
        }
</script>
```

## 24.5 replace() 方法使用字符串
replace() 方法将接收字符串作为参数：
```js
var str = document.getElementById("demo").innerHTML;
var txt = str.replace("Microsoft","Runoob");
```
    正则表达式参数可用在以上方法中 (替代字符串参数)。
    正则表达式使得搜索功能更加强大(如实例中不区分大小写)。

## 24.6 正则表达式修饰符
修饰符 可以在全局搜索中不区分大小写:

修饰符|	描述
-|-
i	|   执行对大小写不敏感的匹配。
g	|   执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。
m	|   执行多行匹配。

## 24.7 正则表达式模式
方括号用于查找某个范围内的字符：

表达式	|	描述
-|-
[abc]|	查找方括号之间的任何字符。
[0-9]|	查找任何从 0 至 9 的数字。
(x|y)|	查找任何以 \| 分隔的选项。

## 24.8 元字符是拥有特殊含义的字符：

元字符	|描述
-|-
\d	   | 查找数字。
\s	   | 查找空白字符。
\b	   | 匹配单词边界。
\uxxxx	|查找以十六进制数 xxxx 规定的 Unicode 字符。

## 24.9 量词:

量词	|描述
-|-
n+	|匹配任何包含至少一个 n 的字符串。
n*	|匹配任何包含零个或多个 n 的字符串。
n?	|匹配任何包含零个或一个 n 的字符串。

## 24.10 使用 RegExp 对象
在 JavaScript 中，RegExp 对象是一个预定义了属性和方法的正则表达式对象。

## 24.11 使用 test()
test() 方法是一个正则表达式方法。
test() 方法用于检测一个字符串是否匹配某个模式，如果字符串中含有匹配的文本，则返回 true，否则返回 false。
以下实例用于搜索字符串中的字符 "e"：
```js
var patt = /e/;
patt.test("The best things in life are free!");
```
## 24.12 使用 exec()
exec() 方法是一个正则表达式方法。
exec() 方法用于检索字符串中的正则表达式的匹配。
该函数返回一个数组，其中存放匹配的结果。如果未找到匹配，则返回值为 null。
以下实例用于搜索字符串中的字母 "e":
```js
/e/.exec("The best things in life are free!");
```



# 25 JavaScript 错误 - throw、try 和 catch
JavaScript 错误 - throw、try 和 catch
```
try 语句测试代码块的错误。
catch 语句处理错误。
throw 语句创建自定义错误。
```
**finally **语句在 try 和 catch 语句之后，**无论是否有触发异常，该语句都会执行。**

## 25.1. JavaScript 错误
当 JavaScript 引擎执行 JavaScript 代码时，会发生各种错误。
可能是**语法错误**，通常是程序员造成的编码错误或错别字。
可能是**拼写错误或语言中缺少的功能**（可能由于浏览器差异）。
可能是由于来自**服务器或用户的错误输出**而导致的错误。
当然，也可能是由于许多其他不可预知的因素。

## 25.2 JavaScript 抛出（throw）错误
当错误发生时，当事情出问题时，JavaScript 引擎通常会停止，并生成一个错误消息。
描述这种情况的技术术语是：JavaScript 将抛出一个错误。

## 25.3 JavaScript try 和 catch
try 语句允许我们定义**在执行时进行错误测试的代码块。**
**catch** 语句允许我们定义**当 try 代码块发生错误时，所执行的代码块。**
JavaScript 语句 try 和 catch 是成对出现的。
语法
```js
try {
    ...    //异常的抛出
} catch(e) {
    ...    //异常的捕获与处理
} finally {
    ...    //结束处理
}
```
```js
<input type="button" value="查看信息" onclick="message()">

<p>不管输入是否正确，输入框都会再输入后清空。</p><br>
<p>请输入 5 ~ 10 之间的数字：</p><br>

<input id="demo" type="text">
<button type="button" onclick="myFunction()">点击</button>

<p id="p01"></p>

<script>
    function myFunction(){
        var message, x;
        message= document.getElementById("p01");
        message.innerHTML= "";
        x= document.getElementById("demo").value;
        try{
            if(x == "") throw "值为空";
            if(isNaN(x)) throw "值不是个数字";
            x= Number(x);
            if(x > 10) throw "太大"
            if(x < 5) throw "太小"
        }
        catch (err){
            message.innerHTML= "错误：" + err + ".";
        }
        finally {
            document.getElementById("demo").value= "";
        }
    }
</script>
```

## 25.4 Throw 语句
**throw 语句允许我们创建自定义错误**。

正确的技术术语是：**创建或抛出异常（exception）。**

如果把 **throw 与 try 和 catch 一起使用，那么您能够控制程序流，并生成自定义的错误消息。**

语法

**throw exception**
**异常可以是 JavaScript 字符串、数字、逻辑值或对象。**

实例
本例检测输入变量的值。如果值是错误的，会抛出一个异常（错误）。catch 会捕捉到这个错误，并显示一段自定义的错误消息：
```js
function myFunction() {
    var message, x;
    message = document.getElementById("message");
    message.innerHTML = "";
    x = document.getElementById("demo").value;
    try {
        if(x == "")  throw "值为空";
        if(isNaN(x)) throw "不是数字";
        x = Number(x);
        if(x < 5)    throw "太小";
        if(x > 10)   throw "太大";
    }
    catch(err) {
        message.innerHTML = "错误: " + err;
    }
}
```
请注意，如果 getElementById 函数出错，上面的例子也会抛出一个错误。
\</body>

# 26 JavaScript 调试
在编写 JavaScript 时，如果没有调试工具将是一件很痛苦的事情。

JavaScript 调试
没有调试工具是很难去编写 JavaScript 程序的。
你的代码可能包含语法错误，逻辑错误，如果没有调试工具，这些错误比较难于发现。
通常，如果 JavaScript 出现错误，是不会有提示信息，这样你就无法找到代码错误的位置。

## 26.1 JavaScript 调试工具

**在程序代码中寻找错误叫做代码调试。**
调试很难，但幸运的是，很多浏览器都内置了调试工具。
内置的调试工具可以开始或关闭，严重的错误信息会发送给用户。
有了调试工具，我们就可以设置断点 (代码停止执行的位置), 且可以在代码执行时检测变量。
**浏览器启用调试工具一般是按下 F12 键，并在调试菜单中选择 "Console" 。**

## 26.2 console.log() 方法
如果浏览器支持调试，你可以使用 console.log() 方法在调试窗口上打印 JavaScript 值：
```js
<script>
    a= 5;
    b= 6;
    c= a + b;
    console.log(c);
</script>
```


### 26.2.1 设置断点
在调试窗口中，你可以设置 JavaScript 代码的断点。
在每个断点上，都会停止执行 JavaScript 代码，以便于我们检查 JavaScript 变量的值。
在检查完毕后，可以重新执行代码（如播放按钮）


### 26.2.2 debugger 关键字
**debugger 关键字用于停止执行 JavaScript，并调用调试函数**。
这个关键字与在调试工具中设置断点的效果是一样的。
如果没有调试可用，debugger 语句将无法工作。
开启 debugger ，代码在第三行前停止执行。
```js
var x = 15 * 5;
debugger;
document.getElementbyId("demo").innerHTML = x;
```



## 26.3 主要浏览器的调试工具

通常，浏览器启用调试工具一般是按下 F12 键，并在调试菜单中选择 "Console" 。
各浏览器的步骤如下:
    Chrome 浏览器
    打开浏览器。
    在菜单中选择 "更多工具"。
    在 "更多工具" 中选择 "开发者工具"。
    最后，选择 Console。

![img](https://www.runoob.com/wp-content/uploads/2014/10/chrome1.png)

或者你可以右击鼠标选择 **"检查"**，如下图：

![img](https://www.runoob.com/wp-content/uploads/2014/10/chrome2.png)







# 27.JavaScript 声明提升
JavaScript 中，**函数及变量的声明都将被提升到函数的最顶部**。
JavaScript 中，**变量可以在使用后声明，也就是变量可以先使用再声明**。

以下两个实例将获得相同的结果：
案例1：
```js
x = 5; // 变量 x 设置为 5

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x;                     // 在元素中显示 x

var x; // 声明 x
```
案例2：
```js
var x; // 声明 x
x = 5; // 变量 x 设置为 5

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x;                     // 在元素中显示 x
```

要理解以上实例就需要理解 "hoisting(声明提升)"。
**声明提升：函数声明和变量声明总是会被解释器悄悄地被"提升"到方法体的最顶部。**

## 27.1 JavaScript 初始化不会提升
JavaScript 只有声明的变量会提升，初始化的不会。

以下两个实例结果结果不相同：
案例1；
```js
var x = 5; // 初始化 x
var y = 7; // 初始化 y

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y
```
案例2；
```js
var x = 5; // 初始化 x

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y

var y = 7; // 初始化 y
```
实例 2 的 y 输出了 undefined，**这是因为变量声明 (var y) 提升了，但是初始化(y = 7) 并不会提升，所以 y 变量是一个未定义的变量。**

实例 2 类似以下代码:
```js
var x = 5; // 初始化 x
var y;     // 声明 y

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y

y = 7;    // 设置 y 为 7
```

## 27.2 在头部声明你的变量
对于大多数程序员来说并不知道 JavaScript 声明提升。

如果程序员不能很好的理解声明提升，他们写的程序就容易出现一些问题。

为了避免这些问题，通常我们在每个作用域开始前声明这些变量，这也是正常的 JavaScript 解析步骤，易于我们理解

**avaScript 严格模式(strict mode)不允许使用未声明的变量。**
在下一个章节中我们将会学习到 "严格模式(strict mode)" 。


# 28.JavaScript 使用误区

## 28.1 赋值运算符应用错误
在 JavaScript 程序中如果你在 if 条件语句中使用赋值运算符的等号 (=) 将会产生一个错误结果, 正确的方法是使用比较运算符的两个等号 (==)。

### 1.1 if 条件语句返回 false (是我们预期的)因为 x 不等于 10:
var x = 0;
if (x == 10)

### 1.2 if 条件语句返回 true (不是我们预期的)因为条件语句执行为 x 赋值 10，10 为 true:
var x = 0;
if (x = 10)

### 1.3 if 条件语句返回 false (不是我们预期的)因为条件语句执行为 x 赋值 0，0 为 false:
var x = 0;
if (x = 0)

赋值语句返回变量的值。

## 28.2 比较运算符常见错误
### 28.2.1 在常规的比较中，数据类型是被忽略的，以下 if 条件语句返回 true：
var x = 10;
var y = "10";
if (x == y)

###28.2.2 在严格的比较运算中，=== 为恒等计算符，同时检查表达式的值与类型，以下 if 条件语句返回 false：
var x = 10;
var y = "10";
if (x === y)
这种错误经常会在 switch 语句中出现，switch 语句会使用恒等计算符(===)进行比较:

### 28.2.3 以下实例会执行 alert 弹窗：
```js
var x = 10;
switch(x) {
    case 10: alert("Hello");
}
```

### 28.2.4 以下实例由于**类型不一致**不会执行 alert 弹窗：
var x = 10;
switch(x) {
    case "10": alert("Hello");
}

## 28.3 加法与连接注意事项
加法是两个数字相加。
连接是两个字符串连接。
JavaScript 的加法和连接都使用 + 运算符。

### 28.3.1接下来我们可以通过实例查看两个数字相加及数字与字符串连接的区别：
```js
var x = 10 + 5;          // x 的结果为 15
var x = 10 + "5";        // x 的结果为 "105"
```
### 28.3.2 使用变量相加结果也不一致:
```js
var x = 10;
var y = 5;
var z = x + y;           // z 的结果为 15

var x = 10;
var y = "5";
var z = x + y;           // z 的结果为 "105"
```
## 28.4 浮点型数据使用注意事项

JavaScript 中的所有数据都是以 64 位浮点型数据(float) 来存储。

所有的编程语言，包括 JavaScript，**对浮点型数据的精确度都很难确定：**
```js
var x = 0.1;
var y = 0.2;
var z = x + y            // z 的结果为 0.30000000000000004
if (z == 0.3)            // 返回 false
```
为解决以上问题，可以用整数的乘除法来解决：

实例
```js
var z = (x * 10 + y * 10) / 10;       // z 的结果为 0.3
```
## 28.5 JavaScript 字符串分行

JavaScript 允许我们在字符串中使用断行语句:

实例 1
```js
var x =
"Hello World!";
```
但是，**在字符串中直接使用回车换行是会报错的：**

实例 2
```js
var x = "Hello
World!";
```

**字符串断行需要使用反斜杠(\)**，如下所示:

实例 3
```js
var x = "Hello \
World!";
```
## 28.6 错误的使用分号
以下实例中，**if 语句失去方法体，原 if 语句的方法体作为独立的代码块被执行，导致错误的输出结果。**

由于分号使用错误，if 语句中的代码块就一定会执行：
```js
if (x == 19);
{
    // code block
}
```

## 28.7 return 语句使用注意事项

JavaScript 默认是在一行的末尾自动结束。

以下两个实例返回结果是一样的(**一个有分号一个没有**):

实例 1
```js
function myFunction(a) {
    var power = 10
    return a * power
}
```

实例 2
```js
function myFunction(a) {
    var power = 10;
    return a * power;
}
```
JavaScript 也可以使用多行来表示一个语句，也就是说一个语句是可以分行的。

以下实例返回相同的结果:

实例 3
```js
function myFunction(a) {
    var
    power = 10;
    return a * power;
}
```

但是，以下实例结果会返回 undefined：
```js
function myFunction(a) {
    var
    power = 10;
    return
}
```
为什么会有这样的结果呢？因为在 JavaScript 中，实例 4 的代码与下面的代码一致：
```js
function myFunction(a) {
    var
    power = 10;
    return;       // 分号结束，返回 undefined
    a * power;
}
```
解析
如果是一个不完整的语句，如下所示:

```js
var
```

JavaScript 将尝试读取第二行的语句：
```js
power = 10;
```
但是由于这样的语句是完整的:
```js
return
```
JavaScript 将自动关闭语句:
```js
return;
```
在 JavaScript 中，分号是可选的 。

由于 return 是一个完整的语句，所以 JavaScript 将关闭 return 语句。
**不用对 return 语句进行断行。**

## 28.8 数组中使用名字来索引
许多程序语言都允许使用名字来作为数组的索引。
使用名字来作为索引的数组称为关联数组(或哈希)。
**JavaScript 不支持使用名字来索引数组，只允许使用数字索引。**
```js
var person = [];
person[0] = "John";
person[1] = "Doe";
person[2] = 46;
var x = person.length;         // person.length 返回 3
var y = person[0];             // person[0] 返回 "John"
```
在 JavaScript 中, **对象** 使用 **名字作为索引**。
**如果你使用名字作为索引，当访问数组时，JavaScript 会把数组重新定义为标准对象。**
执行这样操作后，数组的方法及属性将不能再使用，否则会产生错误:
```js
var person = [];
person["firstName"] = "John";
person["lastName"] = "Doe";
person["age"] = 46;
var x = person.length;         // person.length 返回 0
var y = person[0];             // person[0] 返回 undefined
```

## 28.9 定义数组元素，最后不能添加逗号
数组最后一个值的后面添加逗号虽然语法没有问题，但是在不同的浏览器可能得到不同的结果。
```js
var colors = [5, 6, 7,]; //这样数组的长度可能为3 也可能为4。
```
正确的定义方式：
```js
points = [40, 100, 1, 5, 25, 10];
```
## 28.10 定义对象，最后不能添加逗号
错误的定义方式：
```js
websites = {site:"菜鸟教程", url:"www.runoob.com", like:460,}
```
正确的定义方式：
```js
websites = {site:"菜鸟教程", url:"www.runoob.com", like:460}
```
## 28.11 Undefined 不是 Null
在 JavaScript 中,** null 用于对象, undefined 用于变量，属性和方法。**

对象只有被定义才有可能为 null，否则为 undefined。

如果我们想测试对象是否存在，在对象还没定义时将会抛出一个错误。

错误的使用方式：
```js
if (myObj !== null && typeof myObj !== "undefined")
```
正确的方式是我们需要先使用 typeof 来检测对象是否已定义：
```js
if (typeof myObj !== "undefined" && myObj !== null) 
```
## 28.12 程序块作用域
在每个代码块中 JavaScript 不会创建一个新的作用域，一般各个代码块的作用域都是全局的。

以下代码的的变量 i 返回 10，而不是 undefined：

实例
```js
for (var i = 0; i < 10; i++) {
    // some code
}
return i
```


# 29 JavaScript 表单
## 29.1.JavaScript 表单验证
HTML 表单验证可以通过 JavaScript 来完成。

以下实例代码用于判断表单字段(fname)值是否存在， 如果不存在，就弹出信息，阻止表单提交：
```js
function validateForm() {
    var x = document.forms["myForm"]["fname"].value;
    if (x == null || x == "") {
        alert("需要输入名字。");
        return false;
    }
}
```
以上 JavaScript 代码可以通过 HTML 代码来调用：

HTML 表单实例
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>form</title>
    <script>
        function validateForm(){
            var x = document.forms["myForm"]["fname"].value;
            if(x == null || x == ""){
                alert("你需要输入名字！");
                return false;
            }
        }
    </script>
</head>
<body>
<form action="demo_form.php" name="myForm" onsubmit="return validateForm()" method="post">
名字：<input type="text" name="fname">
<input type="submit" value="提交">
</form>
</body>
</html>
```

## 29.2 JavaScript 验证输入的数字
JavaScript 常用于对输入数字的验证：
```js
<h1>输出1到10之间的数字</h1>
<input id="numb">
<button type="button" onclick="myFunction()">提交</button>

<p id="demo"></p>
<script>
    function myFunction(){
        var x, text;
        // 获取 id="numb" 的值
        x= document.getElementById("numb").value;


         // 如果输入的值 x 不是数字或者小于 1 或者大于 10，则提示错误 Not a Number or less than one or greater than 10
        if(isNaN(x) || x < 1 || x > 10){
            text= "输出错误"
        }
        else{
            text= "输出正确"
        }
        document.getElementById("demo").innerHTML= text;
    }

</script>
```



## 29.3 HTML 表单自动验证
HTML 表单验证也可以通过浏览器来自动完成。
如果表单字段 (fname) 的值为空, **required 属性会阻止表单提交**：

```js
<form action="demo_form.php" method="post">
 <input type="text" name="fname" required="required">
<input type="submit" value="提交">-->
</form>
```



## 29.4 数据验证

数据验证用于确保用户输入的数据是有效的。

典型的数据验证有：

- 必需字段是否有输入?

- 用户是否输入了合法的数据?

- 在数字字段是否输入了文本?

  

大多数情况下，**数据验证用于确保用户正确输入数据。**

数据验证可以使用不同方法来定义，并通过多种方式来调用。

服务端数据验证是在数据提交到服务器上后再验证。

客户端数据验证是在数据发送到服务器前，在浏览器上完成验证。



### 29.5 HTML 约束验证

HTML5 新增了 HTML 表单的验证方式：约束验证（constraint validation）。
约束验证是表单被提交时浏览器用来实现验证的一种算法。
HTML 约束验证基于：

- HTML 输入属性
- CSS 伪类选择器
-  DOM 属性和方法 

### 29.5.1 约束验证 HTML 输入属性

属性	|描述
-|-
disabled	|规定输入的元素不可用
max	|规定输入元素的最大值
min	|规定输入元素的最小值
pattern	|规定输入元素值的模式
required	|规定输入元素字段是必需的
type 	|规定输入元素的类型

### 29.5.2 约束验证 CSS 伪类选择器

选择器	  |  描述
-|-
:disabled	|选取属性为 "disabled" 属性的 input 元素
:invalid	|选取无效的 input 元素
:optional	|选择没有"optional"属性的 input 元素
:required	|选择有"required"属性的 input 元素
:valid		|选取有效值的 input 元素



# 30 JavaScript 表单验证

## 30.1 JavaScript 表单验证

JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。

表单数据经常需要使用 JavaScript 来验证其正确性：

- 验证表单数据是否为空？
- 验证输入是否是一个正确的email地址？
- 验证日期是否输入正确？
- 验证表单输入内容是否为数字型

## 30.2 必填（或必选）项目

下面的函数用来检查用户是否已填写表单中的必填（或必选）项目。假如必填或必选项为空，那么警告框会弹出，并且函数的返回值为 false，否则函数的返回值则为 true（意味着数据没有问题）：
```js
<script>
    function myForm(){
    var x = document.forms["Form"]["inpForm"].value;
    if (x==null || x==""){
        alert("请输入名字");
        return false;
    }
}
</script>
```
以上函数在 form 表单提交时被调用:

实例
```js
<form name="Form" action="form.php"  onsubmit="return myForm()" method="post">
名字：<input type="text" name="inpForm">
<input type="submit"    value="提交">
</form>
```

## 30.3 E-mail 验证
下面的函数检查输入的数据是否符合电子邮件地址的基本语法。

意思就是说，输入的数据必须包含 @ 符号和点号(.)。同时，@ 不可以是邮件地址的首字符，并且 @ 之后需有至少一个点号：
```js
function validateForm(){
  var x=document.forms["myForm"]["email"].value;
  var atpos=x.indexOf("@");
  var dotpos=x.lastIndexOf(".");
  if (atpos<1 || dotpos<atpos+2 || dotpos+2>=x.length){
    alert("不是一个有效的 e-mail 地址");
    return false;
  }
}
```
下面是连同 HTML 表单的完整代码：

实例
```js
<form name="myForm" action="demo-form.php" onsubmit="return validateForm();" method="post">
    Email: <input type="text" name="email">
    <input type="submit" value="提交">
</form>
```


# 31 JavaScript 验证 API

## 31.1 约束验证 DOM 方法

Property	    |       Description
-|-
checkValidity()	 |      如果 input 元素中的数据是合法的返回 true，否则返回 false。
setCustomValidity() |   设置 input 元素的 validationMessage 属性，用于自定义错误提示信息的方法。
||使用 setCustomValidity 设置了自定义提示后，validity.customError 就会变成 true，checkValidity 总是会返回 false。如果要重新判断需要取消自定义提示，方式如下：
||setCustomValidity('')
||setCustomValidity(null)
||setCustomValidity(undefined)

以下实例如果输入信息不合法，则返回错误信息：
```js
<p>输入数字并点击验证按钮:</p>

<input id="id1" type="number" min="100" max="300" required>
<button onclick="myFunction()">验证</button>

<p>如果输入的数字小于 100 或大于300，会提示错误信息。</p>
<p id="demo"></p>
<script>
    function myFunction(){
        var inpObj= document.getElementById("id1")//定义inpObj,获取输入值id1
        if(inpObj.checkValidity() == false){
            document.getElementById("demo").innerHTML =inpObj.validationMessage;
        }
        else{
            document.getElementById("demo").innerHTML= "输出正确"
        }
    }
</script>
```



## 31.2.约束验证 DOM 属性

属性	          |      描述
-|-
validity	  |      布尔属性值，返回 input 输入值是否合法
validationMessage|	浏览器错误提示信息
willValidate	 |   指定 input 是否需要验证

31.2.1Validity 属性
input 元素的 validity 属性包含一系列关于 validity 数据属性:

属性	    |       描述
-|-	
customError	|   设置为 true, 如果设置了自定义的 validity 信息。
patternMismatch|设置为 true, 如果元素的值不匹配它的模式属性。
rangeOverflow|	设置为 true, 如果元素的值大于设置的最大值。
rangeUnderflow|	设置为 true, 如果元素的值小于它的最小值。
stepMismatch|	设置为 true, 如果元素的值不是按照规定的 step 属性设置。
tooLong	  |     设置为 true, 如果元素的值超过了 maxLength 属性设置的长度。
typeMismatch|	设置为 true, 如果元素的值不是预期相匹配的类型。
valueMissing|	设置为 true，如果元素 (required 属性) 没有值。
valid	|       设置为 true，如果元素的值是合法的。

如果输入的值大于 100，显示一个信息：

```js
<input id="id1" type="number" max="100">
<button onclick="myFunction()">验证</button>
 
<p id="demo"></p>
 
<script>
function myFunction() {
    var txt = "";
    if (document.getElementById("id1").validity.rangeOverflow) {
       txt = "输入的值太大了";
    }
    document.getElementById("demo").innerHTML = txt;
}
</script>
```



如果输入的值小于 100，显示一个信息：

```js
<input id="id1" type="number" min="100" required>
<button onclick="myFunction()">OK</button>
 
<p id="demo"></p>
 
<script>function myFunction() {
    var txt = "";
    var inpObj = document.getElementById("id1");
    if(!isNumeric(inpObj.value)) {
        txt = "你输入的不是数字";
    } else if (inpObj.validity.rangeUnderflow) {
        txt = "输入的值太小了";
    } else {
        txt = "输入正确";
    }
    document.getElementById("demo").innerHTML = txt;
}
 
// 判断输入是否为数字
function isNumeric(n) {
    return !isNaN(parseFloat(n)) && isFinite(n);
}</script>
```





## 32 javascript保留关键字：https://www.runoob.com/js/js-reserved.html

 JavaScript 保留关键字、JavaScript 对象、属性和方法、Java 保留关键字、Windows 保留关键字



# 33 JavaScript let 和 const

ECMAScript 2015(ECMAScript 6)
ES2015(ES6) 新增加了两个重要的 JavaScript **关键字: let 和 const。**
**let 声明的变量只在 let 命令所在的代码块内有效。**
**const 声明一个只读的常量，一旦声明，常量的值就不能改变。**
在 ES6 之前，JavaScript 只有两种作用域： 全局变量 与 函数内的局部变量。

## 33.1 全局变量
在函数外声明的变量作用域是全局的：
```js
<p id="demo"></p>
<script>
    var carName= "Volvo";
    // 这里可以使用 carName 变量
    function myFuncion(){
        // 这里也可以使用 carName 变量
    }
</script>
```

全局变量在 JavaScript 程序的任何地方都可以访问。

## 33.2 局部变量
在函数内声明的变量作用域是局部的（函数内）：
```js
// 这里不能使用 carName 变量

function myFunction() {
    var carName = "Volvo";
    // 这里可以使用 carName 变量
}

// 这里不能使用 carName 变量
```
函数内使用 var 声明的变量只能在函数内访问，如果不使用 var 则是全局变量。

## 33.3 JavaScript 块级作用域(Block Scope)
使用** var 关键字声明的变量不具备块级作用域的特性**，它在 {} 外依然能被访问到。
```js
{
    var x = 2;
}
// 这里可以使用 x 变量
```
在 ES6 之前，是没有块级作用域的概念的。

ES6 可以使用 let 关键字来实现块级作用域。

**let 声明的变量只在 let 命令所在的代码块 {} 内有效，在 {} 之外不能访问。**

```js
{
    let x = 2;
}
// 这里不能使用 x 变量
```

## 33.4 重新定义变量
使用 var 关键字重新声明变量可能会带来问题。

在块中重新声明变量也会重新声明块外的变量：
```js
var x = 10;
// 这里输出 x 为 10
{
    var x = 2;
    // 这里输出 x 为 2
}
// 这里输出 x 为 2
let 关键字就可以解决这个问题，因为它只在 let 命令所在的代码块 {} 内有效。
var x = 10;
// 这里输出 x 为 10
{
    let x = 2;
    // 这里输出 x 为 2
}
// 这里输出 x 为 10
```
## 33.5 循环作用域
使用 var 关键字：

实例
```js
var i = 5;
for (var i = 0; i < 10; i++) {
    // 一些代码...
}
// 这里输出 i 为 10
```
使用 let 关键字：
实例
```js
var i = 5;
for (let i = 0; i < 10; i++) {
    // 一些代码...
}
// 这里输出 i 为 5
```
在第一个实例中，使用了 var 关键字，它声明的变量是全局的，包括循环体内与循环体外。

在第二个实例中，使用 let 关键字， 它声明的变量作用域只在循环体内，循环体外的变量不受影响。

## 33.6 局部变量
在函数体内使用 var 和 let 关键字声明的变量有点类似。

它们的作用域都是 局部的:
```js
// 使用 var
function myFunction() {
    var carName = "Volvo";   // 局部作用域
}

// 使用 let
function myFunction() {
    let carName = "Volvo";   //  局部作用域
}
```
## 33.7 全局变量
在函数体外或代码块外使用 var 和 let 关键字声明的变量也有点类似。

它们的作用域都是 全局的:
```js
// 使用 var
var x = 2;       // 全局作用域

// 使用 let
let x = 2;       // 全局作用域
```
HTML 代码中使用全局变量
在 JavaScript 中, 全局作用域是针对 JavaScript 环境。

在 HTML 中, 全局作用域是针对 window 对象。

使用 var 关键字声明的全局作用域变量属于 window 对象:

实例
```js
var carName = "Volvo";
// 可以使用 window.carName 访问变量

使用 let 关键字声明的全局作用域变量不属于 window 对象:
let carName = "Volvo";
// 不能使用 window.carName 访问变量
```
重置变量
使用 var 关键字声明的变量在任何地方都可以修改：

实例
```js
var x = 2;

// x 为 2

var x = 3;

// 现在 x 为 3
```
在相同的作用域或块级作用域中，不能使用 let 关键字来重置 var 关键字声明的变量:
```js
    var x = 2;       // 合法
    let x = 3;       // 不合法

    {
        var x = 4;   // 合法
        let x = 5   // 不合法
    }
```

在相同的作用域或块级作用域中，**不能使用 let 关键字来重置 let 关键字声明的变量**:
```js
    let x = 2;       // 合法
    let x = 3;       // 不合法

    {
        let x = 4;   // 合法
        let x = 5;   // 不合法
    }

在相同的作用域或块级作用域中，不能使用 var 关键字来重置 let 关键字声明的变量:

    let x = 2;       // 合法
    var x = 3;       // 不合法
    
    {
        let x = 4;   // 合法
        var x = 5;   // 不合法
    }
```
let 关键字在**不同作用域，或不同块级作用域中是可以重新声明赋值的:**
```js
    let x = 2;       // 合法

    {
        let x = 3;   // 合法
    }
    
    {
        let x = 4;   // 合法
    }
```
## 33.8 变量提升
JavaScript 中，**var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明**（JavaScript 变量提升）。
实例
```js
// 在这里可以使用 carName 变量

var carName;
```
**let 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。**
```
    // 在这里不可以使用 carName 变量
    let carName;
```

const 关键字

**const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改：**
实例
```
const PI = 3.141592653589793;
PI = 3.14;      // 报错
PI = PI + 10;   // 报错
```
const定义常量与使用let 定义的变量相似：
- 二者都是块级作用域
- 都不能和它所在作用域内的其他变量或函数拥有相同的名称

两者还有以下两点区别：
- const 声明的常量必须初始化，而let声明的变量不用
- const 定义常量的值不能通过再赋值修改，也不能再次声明。而 let 定义的变量值可以修改。
```js
var x = 10;
// 这里输出 x 为 10
{
    const x = 2;
    // 这里输出 x 为 2
}
// 这里输出 x 为 10
```

const 声明的常量必须初始化：
```js
// 错误写法
const PI;
PI = 3.14159265359;

// 正确写法
const PI = 3.14159265359;
```

## 33.9 并非真正的常量
const 的本质: const 定义的变量并非常量，并非不可变，它定义了一个常量引用一个值。**使用 const 定义的对象或者数组，其实是可变的。**下面的代码并不会报错：
```js
// 创建常量对象
const car = {type:"Fiat", model:"500", color:"white"};

// 修改属性:
car.color = "red";

// 添加属性
car.owner = "Johnson";
```
但是我们不能对常量对象重新赋值：
```js
const car = {type:"Fiat", model:"500", color:"white"};
car = {type:"Volvo", model:"EX60", color:"red"};    // 错误
```
以下实例修改常量数组：
```js
// 创建常量数组
const cars = ["Saab", "Volvo", "BMW"];

// 修改元素
cars[0] = "Toyota";

// 添加元素
cars.push("Audi");
```
是我们不能对常量数组重新赋值：
实例
```js
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"];    // 错误
```

## 33.10 重置变量
使用 var 关键字声明的变量在任何地方都可以修改：
实例
```js
var x = 2;    //  合法
var x = 3;    //  合法
x = 4;        //  合法
```
在相同的作用域或块级作用域中，不能使用 const 关键字来重置 var 和 let关键字声明的变量:
```js
    var x = 2;         // 合法
    const x = 2;       // 不合法
    {
        let x = 2;     // 合法
        const x = 2;   // 不合法
    }
```
在相同的作用域或块级作用域中，不能使用 const 关键字来重置 const 关键字声明的变量:
```js
    const x = 2;       // 合法
    const x = 3;       // 不合法
    x = 3;             // 不合法
    var x = 3;         // 不合法
    let x = 3;         // 不合法

    {
        const x = 2;   // 合法
        const x = 3;   // 不合法
        x = 3;         // 不合法
        var x = 3;     // 不合法
        let x = 3;     // 不合法
    }
```
const 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的:
```js
    const x = 2;       // 合法

    {
        const x = 3;   // 合法
    }
    
    {
        const x = 4;   // 合法
    }
```

## 33.11 变量提升
JavaScript var 关键字定义的**变量可以在使用后声明，也就是变量可以先使用再声明**（JavaScript 变量提升）。
```js
    carName = "Volvo";    // 这里可以使用 carName 变量
    var carName;
```
const 关键字定义的变量则**不可以在使用后声明，也就是变量需要先声明再使用。**
```js
    carName = "Volvo";    // 在这里不可以使用 carName 变量
    const carName = "Volvo";
```
# 34 JavaScript JSON
JSON 是用于**存储和传输数据**的**格式**。
JSON 通常用于**服务端向网页传递数据** 。

## 34.1 什么是 JSON?
JSON 英文全称 JavaScript Object Notation
JSON 是一种**轻量级的数据交换格式**。
JSON是独立的语言 *
JSON 易于理解。

**JSON 使用 JavaScript 语法，但是 JSON 格式仅仅是一个文本。**
文本可以被任何编程语言读取及作为数据格式传递。



## 34.2. JSON 实例

以下 JSON 语法定义了 sites 对象: 3 条网站信息（对象）的数组:

```json
{"sites":[
    {"name":"Runoob", "url":"www.runoob.com"},
    {"name":"Google", "url":"www.google.com"},
    {"name":"Taobao", "url":"www.taobao.com"}
]}
```

## 34.3 JSON 语法规则
- 数据为 键/值 对。
- 数据由逗号分隔。
- 大括号保存对象
- 方括号保存数组

## 34.4 JSON 数据 - 一个名称对应一个值
JSON 数据格式为 键/值 对，就像 JavaScript 对象属性。

键/值对包括字段名称（在双引号中），后面一个冒号，然后是值：
```
"name":"Runoob"
```

## 34.5 JSON 对象
**JSON 对象保存在大括号内。**
就像在 JavaScript 中, 对象可以保存多个 键/值 对：
```
{"name":"Runoob", "url":"www.runoob.com"}
```

## 34.6 JSON 数组
JSON 数组保存在中括号内。

就像在 JavaScript 中, 数组可以包含对象：
```json
"sites":[
    {"name":"Runoob", "url":"www.runoob.com"},
    {"name":"Google", "url":"www.google.com"},
    {"name":"Taobao", "url":"www.taobao.com"}
]
```
在以上实例中，对象 "sites" 是一个数组，包含了三个对象。
每个对象为站点的信息（网站名和网站地址）。

## 34.7 SON 字符串转换为 JavaScript 对象
通常我们从服务器中读取 JSON 数据，并在网页中显示数据。

简单起见，我们网页中直接设置 JSON 字符串 (你还可以阅读我们的 JSON 教程):

首先，**创建 JavaScript 字符串，字符串为 JSON 格式的数据：**
```js
var text = '{ "sites" : [' +
'{ "name":"Runoob" , "url":"www.runoob.com" },' +
'{ "name":"Google" , "url":"www.google.com" },' +
'{ "name":"Taobao" , "url":"www.taobao.com" } ]}';
```
然后，使用 JavaScript 内置函数 JSON.parse() 将字符串转换为 JavaScript 对象:
```
var obj = JSON.parse(text);
```

最后，在你的页面中使用新的 JavaScript 对象：
```js
<h2>为 JSON 字符串创建对象</h2>
<p id="demo"></p>
<script>
    var text='{ "sites" : [' +
        '{"name":"Runoob", "url":"www.runoob.com"},' +
        '{"name":"Google", "url":"www.google.com"},' +
        '{"name":"Taobao", "url":"www.taobao.com"} ]}';
    obj = JSON.parse(text);
    document.getElementById("demo").innerHTML= obj.sites[1].name + " " +obj.sites[1].url;
</script>
```


## 34.8 相关函数
函数|	描述
-|-
JSON.parse()|	用于将一个 JSON 字符串转换为 JavaScript 对象。
JSON.stringify()|	用于将 JavaScript 值转换为 JSON 字符串。


# 35 javascript:void
## 35.1 javascript:void(0) 含义

我们经常会使用到 javascript:void(0) 这样的代码，那么在 JavaScript 中 javascript:void(0) 代表的是什么意思呢？

javascript:void(0) 中最关键的是 void 关键字， void 是 JavaScript 中非常重要的关键字，**该操作符指定要计算一个表达式但是不返回值。**

语法格式如下：
```js
void func()
javascript:void func()
或者
void(func())
javascript:void(func())

```
下面的代码创建了一个超级链接，当用户点击以后不会发生任何事。
```js
<a href="javascript:void(0)">单击此处什么也不会发生</a>
```

当用户链接时，void(0) 计算为 0，但 Javascript 上没有任何效果。

以下实例中，**在用户点击链接后显示警告信息**：
```js
<p>点击以下链接查看结果：</p>
<a href="javascript:void(alert('Warning!!!'))">点我!</a>
```
以下实例中参数 a 将返回 undefined :
```js
<script type="text/javascript">
function getValue(){
   var a,b,c;
   a = void ( b = 5, c = 7 );
   document.write('a = ' + a + ' b = ' + b +' c = ' + c );
}
</script>

<p>点击以下按钮查看结果：</p>
<form>
<input type="button" value="点我" onclick="getValue();" />
</form>
```


## 35.2 href="#"与href="javascript:void(0)"的区别

**<kbd>#</kbd> 包含了一个位置信息，默认的锚是<kbd>#top</kbd>> 也就是网页的上端。**

而<kbd>javascript:void(0)</kbd>>, 仅仅表示一个死链接。
**在页面很长的时候会使用 # 来定位页面的具体位置，格式为：<kbd># + id</kbd>>。**
如果你要定义一个死链接请使用 javascript:void(0) 。

```js
<body>
<a href="javascript:void(0);">点我没有反应的!</a>
<a href="#pos">点我定位到指定位置!</a>
<br>
...
<br>

<p id="pos">尾部定位点</p>

</body>
```

# 36.JavaScript 异步编程
## 36.1.异步的概念

​    异步（Asynchronous, async）是与同步（Synchronous, sync）相对的概念。
​    在我们学习的传统单线程编程中，程序的运行是同步的（同步不意味着所有步骤同时运行，而是指步骤在一个控制流序列中按顺序执行）。而异步的概念则是不保证同步的概念，也就是说，一个异步过程的执行将不再与原有的序列有顺序关系。
​    简单来理解就是：**同步按你的代码顺序执行，异步不按照代码顺序执行，异步的执行效率更高。**
​    以上是关于异步的概念的解释，接下来我们通俗地解释一下异步：**异步就是从主线程发射一个子线程来完成任务。**

## ![img](https://www.runoob.com/wp-content/uploads/2020/07/async-sync.png)

## 36.2 什么时候用异步编程

​    在前端编程中（甚至后端有时也是这样)，我们在处理一些简短、快速的操作时，例如计算 1 + 1 的结果，往往在主线程中就可以完成。主线程作为一个线程，不能够同时接受多方面的请求。所以，当一个事件没有结束时，界面将无法处理其他请求。
​    现在有一个按钮，如果我们设置它的 onclick 事件为一个死循环，那么当这个按钮按下，整个网页将失去响应。
​    为了避免这种情况的发生，我们常常用子线程来完成一些可能消耗时间足够长以至于被用户察觉的事情，比如读取一个大文件或者发出一个网络请求。因为子线程独立于主线程，所以即使出现阻塞也不会影响主线程的运行。但是子线程有一个局限：一旦发射了以后就会与主线程失去同步，我们无法确定它的结束，如果结束之后需要处理一些事情，比如处理来自服务器的信息，我们是无法将它合并到主线程中去的。
​    为了解决这个问题，JavaScript 中的异步操作函数往往通过回调函数来实现异步任务的结果处理。



## 36.3 回调函数

回调函数就是一个函数，它是在我们启动一个异步任务的时候就告诉它：**等你完成了这个任务之后要干什么。**这样一来主线程几乎不用关心异步任务的状态了，他自己会善始善终。

<p>回调函数等待 3 秒后执行。</p>
<p id="demo"></p>
<script>
    function  print(){
        document.getElementById("demo").innerHTML="OOB"
    }
    setTimeout(print, 3000);
</script>

这段程序中的 setTimeout 就是一个消耗时间较长（3 秒）的过程，它的第一个参数是个回调函数，第二个参数是毫秒数，这个函数执行之后会产生一个子线程，子线程会等待 3 秒，然后执行回调函数 "print"，在命令行输出 "RUNOOB!"。

当然，JavaScript 语法十分友好，我们不必单独定义一个函数 print ，我们常常将上面的程序写成：

```js
setTimeout(function () {
    document.getElementById("demo").innerHTML="RUNOOB!";
}, 3000);
```

注意：既然 setTimeout 会在子线程中等待 3 秒，在 **setTimeout 函数执行之后主线程并没有停止**，所以：

```js
setTimeout(function () {
    document.getElementById("demo1").innerHTML="RUNOOB-1!";  // 三秒后子线程执行
}, 3000);
document.getElementById("demo2").innerHTML="RUNOOB-2!";      // 主线程先执行
```





## 36.4 异步 AJAX

(https://www.runoob.com/ajax/ajax-tutorial.html)

除了 setTimeout 函数以外，异步回调广泛应用于 AJAX 编程。
XMLHttpRequest 常常用于请求来自远程服务器上的 XML 或 JSON 数据。一个标准的 XMLHttpRequest 对象往往包含多个回调：

```js
var xhr = new XMLHttpRequest();

xhr.onload = function () {
    // 输出接收到的文字数据
    document.getElementById("demo").innerHTML=xhr.responseText;
}

xhr.onerror = function () {
    document.getElementById("demo").innerHTML="请求出错";
}

// 发送异步 GET 请求
xhr.open("GET", "https://www.runoob.com/try/ajax/ajax_info.txt", true);
xhr.send();
```



XMLHttpRequest 的 onload 和 onerror 属性都是函数，分别在它请求成功和请求失败时被调用。如果你使用完整的 jQuery 库，也可以更加优雅的使用异步 AJAX：

```jQuery
$.get("https://www.runoob.com/try/ajax/demo_test.php",function(data,status){
    alert("数据: " + data + "\n状态: " + status);
});
```



# 37 JavaScript Promise(是个类)

在学习本章节内容前，你需要先了解什么是异步编程，
Promise 是一个 ECMAScript 6 提供的类，目的是更加优雅地书写复杂的异步任务。

## 37.1 构造 Promise

现在我们新建一个 Promise 对象：

```js
new Promise(function (resolve, reject) {
    // 要做的事情...
});
```



通过新建一个 Promise 对象好像并没有看出它怎样 "更加优雅地书写复杂的异步任务"。**我们之前遇到的异步任务都是一次异步，如果需要多次调用异步函数呢？**例如，如果我想分三次输出字符串，第一次间隔 1 秒，第二次间隔 4 秒，第三次间隔 3 秒：

```js
setTimeout(function () {
    console.log("First");
    setTimeout(function () {
        console.log("Second");
        setTimeout(function () {
            console.log("Third");
        }, 3000);
    }, 4000);
}, 1000);
```



这段程序实现了这个功能，但是它是用 "函数瀑布" 来实现的。可想而知，在一个复杂的程序当中，用 "函数瀑布" 实现的程序无论是维护还是异常处理都是一件特别繁琐的事情，而且会让缩进格式变得非常冗赘。

现在我们用 Promise 来实现同样的功能：
```js
new Promise(function (resolve, reject) {
    setTimeout(function () {
        console.log("First");
        resolve();
    }, 1000);
}).then(function () {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            console.log("Second");
            resolve();
        }, 4000);
    });
}).then(function () {
    setTimeout(function () {
        console.log("Third");
    }, 3000);
});
```
这段代码较长，所以还不需要完全理解它，我想引起注意的是 **Promise 将嵌套格式的代码变成了顺序格式的代码。**




## 37.2 Promise 的构造函数
Promise 构造函数是 JavaScript 中用于创建 Promise 对象的内置构造函数。

Promise 构造函数接受一个函数作为参数，该函数是同步的并且会被立即执行，所以我们称之为起始函数。起始函数包含两个参数 resolve 和 reject，分别表示 Promise 成功和失败的状态。

起始函数执行成功时，它应该调用 resolve 函数并传递成功的结果。当起始函数执行失败时，它应该调用 reject 函数并传递失败的原因。

Promise 构造函数返回一个 Promise 对象，该对象具有以下几个方法：

-  then：用于处理 Promise 成功状态的回调函数。

-  catch：用于处理 Promise 失败状态的回调函数。

-  finally：无论 Promise 是成功还是失败，都会执行的回调函数。

  

下面是一个使用 Promise 构造函数创建 Promise 对象的例子：
当 Promise 被构造时，起始函数会被同步执行：

```js
const promise = new Promise((resolve, reject) => {
  // 异步操作
  setTimeout(() => {
    if (Math.random() < 0.5) {
      resolve('success');
    } else {
      reject('error');
    }
  }, 1000);
});

promise.then(result => {
  console.log(result);
}).catch(error => {
  console.log(error);
});
```



在上面的例子中，我们使用 Promise 构造函数创建了一个 Promise 对象，并使用 setTimeout 模拟了一个异步操作。**如果异步操作成功，则调用 resolve 函数并传递成功的结果；如果异步操作失败，则调用 reject 函数并传递失败的原因。**然后我们使用 then 方法处理 Promise 成功状态的回调函数，使用 catch 方法处理 Promise 失败状态的回调函数。
这段程序会直接输出 **error** 或**success**。



resolve 和 reject 都是函数，其中调用 resolve 代表一切正常，reject 是出现异常时所调用的：
```js
new Promise(function (resolve, reject) {
    var a = 0;
    var b = 1;
    if (b == 0) reject("Divide zero");
    else resolve(a / b);
}).then(function (value) {
    console.log("a / b = " + value);
}).catch(function (err) {
    console.log(err);
}).finally(function () {
    console.log("End");
});
```
这段程序执行结果是:
```js
    a / b = 0
    End
```

Promise 类有 .then() .catch() 和 .finally() 三个方法，这三个方法的参数都是一个函数，.then() 可以将参数中的函数添加到当前 Promise 的正常执行序列，.catch() 则是设定 Promise 的异常处理序列，.finally() 是在 Promise 执行的最后一定会执行的序列。 .then() 传入的函数会按顺序依次执行，有任何异常都会直接跳到 catch 序列：
```js
new Promise(function (resolve, reject) {
    console.log(1111);
    resolve(2222);
}).then(function (value) {
    console.log(value);
    return 3333;
}).then(function (value) {
    console.log(value);
    throw "An error";
}).catch(function (err) {
    console.log(err);
});
```
执行结果：

    1111
    2222
    3333
    An error

resolve() 中可以放置一个参数用于向下一个 then 传递一个值，then 中的函数也可以返回一个值传递给 then。但是，如果 then 中返回的是一个 Promise 对象，那么下一个 then 将相当于对这个返回的 Promise 进行操作，这一点从刚才的计时器的例子中可以看出来。

reject() 参数中一般会传递一个异常给之后的 catch 函数用于处理异常。

但是请注意以下两点：

-  **resolve 和 reject 的作用域只有起始函数，不包括 then 以及其他序列；**
-  resolve 和 reject 并不能够使起始函数停止运行，别忘了 return。



## 37.3 Promise 函数

上述的 "计时器" 程序看上去比函数瀑布还要长，所以我们可以将它的核心部分写成一个 Promise 函数：
```js
function print(delay, message) {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            console.log(message);
            resolve();
        }, delay);
    });
}
```



然后我们就可以放心大胆的实现程序功能了：

实例

```js
print(1000, "First").then(function () {
    return print(4000, "Second");
}).then(function () {
    print(3000, "Third");
});
```



这种返回值为一个 Promise 对象的函数称作 Promise 函数，它常常用于开发基于异步操作的库。



## 37.4 回答常见的问题（FAQ）
Q: then、catch 和 finally 序列能否顺序颠倒？

A: 可以，效果完全一样。但不建议这样做，最好按 then-catch-finally 的顺序编写程序。

Q: 除了 then 块以外，其它两种块能否多次使用？

A: 可以，finally 与 then 一样会按顺序执行，但是 catch 块只会执行第一个，除非 catch 块里有异常。所以最好只安排一个 catch 和 finally 块。

Q: then 块如何中断？

A: then 块默认会向下顺序执行，return 是不能中断的，可以通过 throw 来跳转至 catch 实现中断。

Q: 什么时候适合用 Promise 而不是传统回调函数？

A: 当需要多次顺序执行异步操作的时候，例如，如果想通过异步方法先后检测用户名和密码，需要先异步检测用户名，然后再异步检测密码的情况下就很适合 Promise。

Q: Promise 是一种将异步转换为同步的方法吗？

A: 完全不是。Promise 只不过是一种更良好的编程风格。

Q: 什么时候我们需要再写一个 then 而不是在当前的 then 接着编程？

A: 当你又需要调用一个异步任务的时候。

## 37.5 异步函数
异步函数（async function）是 ECMAScript 2017 (ECMA-262) 标准的规范，几乎被所有浏览器所支持，除了 Internet Explorer。

在 Promise 中我们编写过一个 Promise 函数：

实例
```js
function print(delay, message) {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            console.log(message);
            resolve();
        }, delay);
    });
}
```

然后用不同的时间间隔输出了三行文本：
```js
print(1000, "First").then(function () {
    return print(4000, "Second");
}).then(function () {
    print(3000, "Third");
});
```
我们可以将这段代码变得更好看：
```js
async function asyncFunc() {
    await print(1000, "First");
    await print(4000, "Second");
    await print(3000, "Third");
}
asyncFunc();
```

哈！这岂不是将异步操作变得像同步操作一样容易了吗！

这次的回答是肯定的，异步函数 async function 中可以使用 await 指令，await 指令后必须跟着一个 Promise，异步函数会在这个 Promise 运行中暂停，直到其运行结束再继续运行。

异步函数实际上原理与 Promise 原生 API 的机制是一模一样的，只不过更便于程序员阅读。

处理异常的机制将用 try-catch 块实现：
```js
async function asyncFunc() {
    try {
        await new Promise(function (resolve, reject) {
            throw "Some error"; // 或者 reject("Some error")
        });
    } catch (err) {
        console.log(err);
        // 会输出 Some error
    }
}
asyncFunc();
```
如果 Promise 有一个正常的返回值，await 语句也会返回它：
```js
async function asyncFunc() {
    let value = await new Promise(
        function (resolve, reject) {
            resolve("Return value");
        }
    );
    console.log(value);
}
asyncFunc();
```
程序会输出:
```
Return value
```


# 38.JavaScript 代码规范
所有的 JavaScript 项目适用同一种规范。

## 38.1.JavaScript 代码规范

代码规范通常包括以下几个方面:

- 变量和函数的命名规则
- 空格，缩进，注释的使用规则 。
- 其他常用规范……
- 规范的代码可以更易于阅读与维护。

代码规范一般在开发前规定，可以跟你的团队成员来协商设置。



## 38.2 变量名

变量名推荐使用**驼峰法来命名(camelCase):**

```js
firstName = "John";
lastName = "Doe";

price = 19.90;
tax = 0.20;

fullPrice = price + (price * tax);
```



## 38.3 空格与运算符

通常运算符 ( = + - * / ) 前后需要添加空格:

实例:
```js
var x = y + z;
var values = ["Volvo", "Saab", "Fiat"];
```
## 38.4 代码缩进
通常使用 4 个空格符号来缩进代码块：

函数:
```js
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
```
不推荐使用 TAB 键来缩进，因为不同编辑器 TAB 键的解析不一样。

## 38.5 语句规则
简单语句的通用规则:

一条语句通常以分号作为结束符。
实例:
```js
var values = ["Volvo", "Saab", "Fiat"];

var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
};
```
复杂语句的通用规则:
- 将左花括号放在第一行的结尾。
- 左花括号前添加一空格。
- 将右花括号独立放在一行。
- 以分号结束一个复杂的声明。

函数:
```js
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
循环:
for (i = 0; i < 5; i++) {
    x += i;
}
条件语句:
if (time < 20) {
    greeting = "Good day";
} else {
    greeting = "Good evening";
}
```

## 38.6 对象规则
对象定义的规则:
- 将左花括号与类名放在同一行。
- 冒号与属性值间有个空格。
- 字符串使用双引号，数字不需要。
- 最后一个属性-值对后面不要添加逗号。
- 将右花括号独立放在一行，并以分号作为结束符号。
实例:
```js
var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
};
```
短的对象代码可以直接写成一行:

实例:
```js
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
```

## 38.7 每行代码字符小于 80
为了便于阅读每行字符建议小于数 80 个。

如果一个 JavaScript 语句超过了 80 个字符，建议在 运算符或者逗号后换行。

实例:
```js
document.getElementById("demo").innerHTML =
    "Hello Runoob.";
```

## 38.8 命名规则
一般很多代码语言的命名规则都是类似的，例如:

**变量和函数为小驼峰法标识, 即除第一个单词之外，其他单词首字母大写（ lowerCamelCase）
全局变量为大写 (UPPERCASE )**

**常量 **(如 PI) 为大写 (UPPERCASE )
变量命名你是否使用这几种规则： hyp-hens, camelCase, 或 under_scores ?

**HTML 和 CSS 的横杠(-)字符:**

HTML5 属性可以以 data- (如：data-quantity, data-price) **作为前缀**。

CSS 使用 - **来连接属性名 (font-size)**。
    通常在 JavaScript 中被认为是减法，所以不允许使用。

**下划线:**

很多程序员比较喜欢使用下划线(如：date_of_birth), 特别是在 SQL 数据库中。

PHP 语言通常都使用下划线。

帕斯卡拼写法(PascalCase):

帕斯卡拼写法(PascalCase) 在 C 语言中语言较多。

**驼峰法：**

JavaScript 中通常推荐使用驼峰法，jQuery 及其他 JavaScript 库都使用驼峰法。
    **变量名不要以 $ 作为开始标记**，会与很多 JavaScript 库冲突。

## 38.9 HTML 载入外部 JavaScript 文件
使用简洁的格式载入 JavaScript 文件 ( type 属性不是必须的):
script src="myscript.js"

## 38.10 使用 JavaScript 访问 HTML 元素
一个糟糕的 HTML 格式可能会导致 JavaScript 执行错误。

以下两个 JavaScript 语句会输出不同结果:

实例
```js
var obj = getElementById("Demo")

var obj = getElementById("demo")
```

## 38.11 文件扩展名
```
HTML 文件后缀可以是 .html (或 .htm)。

CSS 文件后缀是 .css 。

JavaScript 文件后缀是 .js 。
```

## 38.12 使用小写文件名
大多 Web 服务器 (Apache, Unix) 对大小写敏感： london.jpg 不能通过 London.jpg 访问。

其他 Web 服务器 (Microsoft, IIS) 对大小写不敏感： london.jpg 可以通过 London.jpg 或 london.jpg 访问。

你必须保持统一的风格，我们建议统一使用小写的文件名。
