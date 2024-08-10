1.JavaScript 库
JavaScript 库 - jQuery、Prototype、MooTools。

1.1.JavaScript 框架（库）
JavaScript 高级程序设计（特别是对浏览器差异的复杂处理），通常很困难也很耗时。

为了应对这些调整，许多的 JavaScript (helper) 库应运而生。

这些 JavaScript 库常被称为 JavaScript 框架。

在本教程中，我们将了解到一些广受欢迎的 JavaScript 框架：

jQuery
Prototype
MooTools
所有这些框架都提供针对常见 JavaScript 任务的函数，包括动画、DOM 操作以及 Ajax 处理。

在本教程中，您将学习到如何开始使用它们，来使得 JavaScript 编程更容易、更安全且更有乐趣。

1.2.Prototype
Prototype 是一种库，提供用于执行常见 web 任务的简单 API。

API 是应用程序编程接口（Application Programming Interface）的缩写。它是包含属性和方法的库，用于操作 HTML DOM。

Prototype 通过提供类和继承，实现了对 JavaScript 的增强。

3.MooTools
MooTools 也是一个框架，提供了可使常见的 JavaScript 编程更为简单的 API。

MooTools 也含有一些轻量级的效果和动画函数。

1.4.其他框架
下面是其他一些在上面未涉及的框架：

YUI - Yahoo! User Interface Framework，涵盖大量函数的大型库，从简单的 JavaScript 功能到完整的 internet widget。

Ext JS - 可定制的 widget，用于构建富因特网应用程序（rich Internet applications）。

Dojo - 用于 DOM 操作、事件、widget 等的工具包。

script.aculo.us - 开源的 JavaScript 框架，针对可视效果和界面行为。

UIZE - Widget、AJAX、DOM、模板等等。

1.5.CDN -内容分发网络
您总是希望网页可以尽可能地快。您希望页面的容量尽可能地小，同时您希望浏览器尽可能多地进行缓存。

如果许多不同的网站使用相同的 JavaScript 框架，那么把框架库存放在一个通用的位置供每个网页分享就变得很有意义了。

CDN (Content Delivery Network) 解决了这个问题。CDN 是包含可分享代码库的服务器网络。

国内免费的 CDN 资源有：

Staticfile CDN：https://staticfile.net/
海外免费的 CDN 资源有：

cdnjs：https://cdnjs.com/
如需在您的网页中使用 JavaScript 框架库，只需在 script 标签中引用该库即可：
引用 jQuery
<!--<script src="https://cdn.staticfile.net/jquery/3.4.0/jquery.min.js">-->
<!--</script>-->

使用框架
在您决定为网页使用 JavaScript 框架之前，首先对框架进行测试是明智的。

JavaScript 框架很容易进行测试。您无需在计算机上安装它们，同时也没有安装程序。

通常您只需从网页中引用一个库文件。

2.JavaScript - 测试 jQuery
测试 JavaScript 框架库 - jQuery

2.1.引用 jQuery
如需测试 JavaScript 库，您需要在网页中引用它。

为了引用某个库，请使用 \< script> 标签，其 src 属性设置为库的 URL：
引用 jQuery:

\< script src="https://cdn.staticfile.org/jquery/1.8.3/jquery.min.js">

2.2.jQuery 描述
主要的 jQuery 函数是 $() 函数（jQuery 函数）。如果您向该函数传递 DOM 对象，它会返回 jQuery 对象，带有向其添加的 jQuery 功能。

jQuery 允许您通过 CSS 选择器来选取元素。

在 JavaScript 中，您可以分配一个函数以处理窗口加载事件：

JavaScript 方式：
function myFunction()
{
    var obj=document.getElementById("h01");
    obj.innerHTML="Hello jQuery";
}
onload=myFunction;


等价的 jQuery 是不同的：
jQuery 方式：
function myFunction()
{
    $("#h01").html("Hello jQuery");
}
$(document).ready(myFunction);
上面代码的最后一行，HTML DOM 文档对象被传递到 jQuery ：$(document)。

当您向 jQuery 传递 DOM 对象时，jQuery 会返回以 HTML DOM 对象包装的 jQuery 对象。

jQuery 函数会返回新的 jQuery 对象，其中的 ready() 是一个方法。

由于在 JavaScript 中函数就是变量，因此可以把 myFunction 作为变量传递给 jQuery 的 ready 方法。
	jQuery 返回 jQuery 对象，与已传递的 DOM 对象不同。
    jQuery 对象拥有的属性和方法，与 DOM 对象的不同。
    您不能在 jQuery 对象上使用 HTML DOM 的属性和方法。

2.3.测试 jQuery
请试一下下面这个例子：
<!--<head>-->
<!--<script src="https://cdn.staticfile.org/jquery/1.8.3/jquery.min.js">-->
<!--</script>-->
<!--<script>-->
<!--function myFunction()-->
<!--{-->
<!--    $("#h01").html("Hello jQuery")-->
<!--}-->
<!--$(document).ready(myFunction);-->
<!--</script>-->
<!--</head>-->
<!--<body>-->
<!--<h1 id="h01"></h1>-->
<!--</body>-->

正如您在上面的例子中看到的，jQuery 允许链接（链式语法）。

3.JavaScript - 测试 Prototype
测试 JavaScript 框架库 - Prototype

3.1.引用 Prototype
如需测试 JavaScript 库，您需要在网页中引用它。

为了引用某个库，请使用 \< script> 标签，其 src 属性设置为库的 URL：
<script
src="https://cdn.staticfile.org/prototype/1.7.3/prototype.min.js">
</script>

3.2.Prototype 描述
Prototype 提供的函数可使 HTML DOM 编程更容易。

与 jQuery 类似，Prototype 也有自己的 $() 函数。

$() 函数接受 HTML DOM 元素的 id 值（或 DOM 元素），并会向 DOM 对象添加新的功能。

与 jQuery 不同，Prototype 没有用以取代 window.onload() 的 ready() 方法。相反，Prototype 会向浏览器及 HTML DOM 添加扩展。

在 JavaScript 中，您可以分配一个函数以处理窗口加载事件：
JavaScript 方式：
function myFunction()
{
    var obj=document.getElementById("h01");
    obj.innerHTML="Hello Prototype";
}
onload=myFunction;
等价的 Prototype 是不同的：

Prototype 方式：
function myFunction()
{
    $("h01").insert("Hello Prototype!");
}
Event.observe(window,"load",myFunction);

Event.observe() 接受三个参数：

您希望处理的 HTML DOM 或 BOM（浏览器对象模型）对象
您希望处理的事件
您希望调用的函数

3.3.测试 Prototype
请试一下下面这个例子：
<!--<html>-->
<!--<script src="https://cdn.staticfile.org/prototype/1.7.3/prototype.min.js">-->
<!--</script>-->
<!--<script>-->
<!--function myFunction()-->
<!--{-->
<!--    $("h01").insert("Hello Prototype!");-->
<!--}-->
<!--Event.observe(window,"load",myFunction);-->
<!--</script>-->
<!--</head>-->
<!--<body>-->
<!--<h1 id="h01"></h1>-->
<!--</body>-->
<!--</html>-->
