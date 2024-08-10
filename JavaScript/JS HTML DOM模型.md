1.JavaScript HTML DOM
通过 HTML DOM，可访问 JavaScript HTML 文档的所有元素

1.1.HTML DOM (文档对象模型)<br>
当网页被加载时，浏览器会创建页面的文档对象模型（Document Object Model）。<br>
HTML DOM 模型被构造为对象的树：<br>
<img src="html_dom模型.gif"><br>

通过可编程的对象模型，JavaScript 获得了足够的能力来创建动态的 HTML。<br>
    JavaScript 能够改变页面中的所有 HTML 元素<br>
    JavaScript 能够改变页面中的所有 HTML 属性<br>
    JavaScript 能够改变页面中的所有 CSS 样式<br>
    JavaScript 能够对页面中的所有事件做出反应<br>

1.2.查找 HTML 元素
通常，通过 JavaScript，您需要操作 HTML 元素。
为了做到这件事情，您必须首先找到该元素。有三种方法来做这件事：
    通过 id 找到 HTML 元素
    通过标签名找到 HTML 元素
    通过类名找到 HTML 元素

1.3.通过 id 查找 HTML 元素
在 DOM 中查找 HTML 元素的最简单的方法，是通过使用元素的 id。
本例查找 id="intro" 元素：
<p id="intro">你好世界!</p>
<p>该实例展示了 <b>getElementById</b> 方法!</p>

<script>
    x= document.getElementById("intro");
    document.write("<p>文本来自 id 为 intro 段落:" + x.innerHTML + "</p>");
</script>
如果找到该元素，则该方法将以对象（在 x 中）的形式返回该元素。

如果未找到该元素，则 x 将包含 null。


1.4.通过标签名查找 HTML 元素
本例查找 id="main" 的元素，然后查找 id="main" 元素中的所有 p 元素：
<p>你好世界!</p>
<div id="main">
<p> DOM 是非常有用的。</p>
<p>该实例展示了  <b>getElementsByTagName</b> 方法</p>
</div>
<script>
    var x=document.getElementById("main");
    var y=x.getElementsByTagName("p");
    document.write('id="main"元素中的第一个段落为：' + y[0].innerHTML);
</script>

1.5.通过类名找到 HTML 元素
本例通过 getElementsByClassName 函数来查找 class="intro" 的元素：
<p class="intro1">你好世界!</p>
<p>该实例展示了 <b>getElementsByClassName</b> 方法!</p>
<script>
x=document.getElementsByClassName("intro1");
document.write("<p>文本来自 class 为 intro 段落: " + x[0].innerHTML + "</p>");
</script>
<p><b>注意：</b>Internet Explorer 8 及更早 IE 版本不支持 getElementsByClassName() 方法。</p>

1.6.HTML DOM 教程
在本教程接下来的篇幅中，您将学到：
    如何改变 HTML 元素的内容 (innerHTML)
    如何改变 HTML 元素的样式 (CSS)
    如何对 HTML DOM 事件做出反应
    如何添加或删除 HTML 元素


2.JavaScript HTML DOM - 改变 HTML
HTML DOM 允许 JavaScript 改变 HTML 元素的内容。

2.1.改变 HTML 输出流
JavaScript 能够创建动态的 HTML 内容：
今天的日期是：
在 JavaScript 中，document.write() 可用于直接向 HTML 输出流写内容。<br>
<script>
    document.write(Date());
</script><br>
绝对不要在文档(DOM)加载完成之后使用 document.write()。这会覆盖该文档。


2.2.改变 HTML 内容
修改 HTML 内容的最简单的方法是使用 innerHTML 属性。
如需改变 HTML 元素的内容，请使用这个语法：
document.getElementById(id).innerHTML=新的 HTML
<p id="p1">hello world</p>
<script>
    document.getElementById("p1").innerHTML = "新文本"//HTML 元素的内容
</script>

下面这例改变了 h1 元素的内容：
<h1 id="header">老标题</h1>
<script>
    var element = document.getElementById("header");
    element.innerHTML = "新标题";
</script>
实例讲解：
上面的 HTML 文档含有 id="header" 的 h1 元素
我们使用 HTML DOM 来获得 id="header" 的元素
JavaScript 更改此元素的内容 (innerHTML)

2.3.改变 HTML 属性
如需改变 HTML 元素的属性，请使用这个语法：

document.getElementById(id).attribute=新属性值
本例改变了 img 元素的 src 属性：

<img id="imags" src="html_dom模型.gif" >
<script>
    document.getElementById("imags").src="dom模型.gif";
</script>
<p>原图片为 html_dom模型.gif,脚本将图片修改为 dom模型.gif</p>

上面的 HTML 文档含有 id="image" 的 img 元素
我们使用 HTML DOM 来获得 id="image" 的元素
JavaScript 更改此元素的属性（把 "html_dom模型.gif" 改为 "dom模型.gif"）


3.JavaScript HTML DOM - 改变CSS
HTML DOM 允许 JavaScript 改变 HTML 元素的样式。

3.1.改变 HTML 样式
如需改变 HTML 元素的样式，请使用这个语法：

document.getElementById(id).style.property=新样式
下面的例子会改变 p 元素的样式：

<p id="p1">Hello World</p>
<p id="p2">Hello World</p>
<script>
    document.getElementById("p2").style.color = "blue";
    document.getElementById("p2").style.fontFamily = "Arial";
    document.getElementById("p2").style.fontSize = "larger";
</script>
<p>以上段落通过脚本修改。</p>

使用事件
HTML DOM 允许我们通过触发事件来执行代码。

比如以下事件：
元素被点击。
页面加载完成。
输入框被修改。
……
在接下来的章节，你会学到更多关于事件的知识。

本例改变了 id="id1" 的 HTML 元素的样式，当用户点击按钮时
<h1 id="id1">标题</h1>
<button type="button"
onclick="document.getElementById('id1').style.color = 'red'">点击，这个动作就是一个事件</button>

3.2.如何使元素不可见。您希望元素显示或消失。
<p id="p3">这是一个文本。 这是一个文本。 这是一个文本。 这是一个文本。></p>
<input type="button" value="隐藏文本" onclick="document.getElementById('p3').style.visibility='hidden'">
<input type="button" value="显示文本" onclick="document.getElementById('p3').style.visibility='visible'">


4.<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JavaScript HTML DOM 事件</title>
    <script>
        function changetext(id){
            id.innerHTML = "新内容";
        }
    </script>
</head>
<body onload="checkCookies()">
JavaScript HTML DOM 事件
HTML DOM 使 JavaScript 有能力对 HTML 事件做出反应

4.1.对事件做出反应
我们可以在事件发生时执行 JavaScript，比如当用户在 HTML 元素上点击时。

如需在用户点击某个元素时执行代码，请向一个 HTML 事件属性添加 JavaScript 代码：

onclick=JavaScript
HTML 事件的例子：
    当用户点击鼠标时
    当网页已加载时
    当图像已加载时
    当鼠标移动到元素上时
    当输入字段被改变时
    当提交 HTML 表单时
    当用户触发按键时
在本例中，当用户在 h1 元素上点击时，会改变其内容：
<h1 onclick="this.innerHTML='新内容啦'">点击文本 会其改变内容</h1>

本例从事件处理器调用一个函数(相同的效果)：
<h1 onclick="changetext(this)">点击文本！</h1>

4.2.HTML 事件属性
如需向 HTML 元素分配 事件，您可以使用事件属性
向 button 元素分配 onclick 事件：
<p>点击按钮执行 <em>displayDate()</em> 函数.</p>
<p id="demo"></p>
<button onclick="displayDate()">点击一下，向 button 元素分配 onclick 事件演示</button>
<script>
    function displayDate(){
        document.getElementById("demo").innerHTML = Date();
    }
</script>
在上面的例子中，名为 displayDate 的函数将在按钮被点击时执行，<br>

4.3.使用 HTML DOM 来分配事件
HTML DOM 允许您使用 JavaScript 来向 HTML 元素分配事件：
向 button 元素分配 onclick 事件：
<p>点击按钮执行 <em>displayDate()</em> 函数.</p>
<button id="p1">点击执行</button>

<script>
    document.getElementById("p1").onclick=function(){displayDate()};
    function displayDate(){
        document.getElementById("p1").innerHTML = Date();
    }
</script>
在上面的例子中，名为 displayDate 的函数被分配给 id="p1" 的 HTML 元素。

按钮点击时Javascript函数将会被执行。

4.4.onload 和 onunload 事件
onload 和 onunload 事件会在用户进入或离开页面时被触发。
onload 事件可用于检测访问者的浏览器类型和浏览器版本，并基于这些信息来加载网页的正确版本。
onload 和 onunload 事件可用于处理 cookie。
<script>
    function checkCookies(){
        if (navigator.cookieEnabled == true){
            alert("Cookise可用")
        }
        else{
            alert("Cookise不可用")
        }
    }
</script>
<p>弹窗-提示浏览器 cookie 是否可用。</p>

<script>
    function myFunction(){
        var x=document.getElementById("fname");
        x.value = x.value.toUpperCase();
    }
</script>


4.5.onmouseover 和 onmouseout 事件
onmouseover 和 onmouseout 事件可用于在用户的鼠标移至 HTML 元素上方或移出元素时触发函数。
一个简单的 onmouseover-onmouseout 实例：
<div onmouseover="mOver(this)" onmouseout="mOut(this)"
style="background-color: red; width:120px; height: 20px; padding: 40px;">
逋抓鼠标移动，触发事件
</div>
<script>
    function mOver(obj){
        obj.innerHTML="来啦，老弟"
    }
    function mOut(obj){
        obj.innerHTML="走啦，老弟"
    }
</script>


4.6.onmousedown、onmouseup 以及 onclick 事件
onmousedown, onmouseup 以及 onclick 构成了鼠标点击事件的所有部分。首先当点击鼠标按钮时，会触发 onmousedown 事件，当释放鼠标按钮时，会触发 onmouseup 事件，最后，当完成鼠标点击时，会触发 onclick 事件。
一个简单的 onmousedown-onmouseup 实例：

4.7.onmousedown 和onmouseup
当用户按下鼠标按钮时，更换一幅图像。

onload
当页面完成加载时，显示一个提示框。

onfocus
当输入字段获得焦点时，改变其背景色。

鼠标事件
当指针移动到元素上方时，改变其颜色；当指针移出文本后，会再次改变其颜色。

</body>
输入你的名字：<input type="text" id="fname" onchange="myFunction()">
<p>当你离开输入框后，函数将被触发，将小写字母转为大写字母。</p>
</html>

5.JavaScript HTML DOM EventListener

5.1.addEventListener() 方法
<p>该实例使用 addEventListener() 方法在按钮中添加点击事件。 </p>
<button id="myBth">点击</button>
<p id="demo"></p>
<script>
    document.getElementById("myBth").addEventListener('click', displayDate)
    function displayDate(){
        document.getElementById("demo").innerHTML = Date();
    }
</script>
addEventListener() 方法用于向指定元素添加事件句柄。

addEventListener() 方法添加的事件句柄不会覆盖已存在的事件句柄。

你可以向一个元素添加多个事件句柄。

你可以向同个元素添加多个同类型的事件句柄，如：两个 "click" 事件。

你可以向任何 DOM 对象添加事件监听，不仅仅是 HTML 元素。如： window 对象。

addEventListener() 方法可以更简单的控制事件（冒泡与捕获）。

当你使用 addEventListener() 方法时, JavaScript 从 HTML 标记中分离开来，可读性更强， 在没有控制HTML标记时也可以添加事件监听。

你可以使用 removeEventListener() 方法来移除事件的监听。

5.2.语法
element.addEventListener(event, function, useCapture);
第一个参数是事件的类型 (如 "click" 或 "mousedown").

第二个参数是事件触发后调用的函数。

第三个参数是个布尔值用于描述事件是冒泡还是捕获。该参数是可选的。
    	注意:不要使用 "on" 前缀。 例如，使用 "click" ,而不是使用 "onclick"。

5.3.向原元素添加事件句柄
<p>该实例使用 addEventListener() 方法在按钮中添加点击事件。 </p>
<button id="myBth1">点击</button>
<script>
    document.getElementById("myBth1").addEventListener("click", function (){
        alert("hello woeld")
    })
</script>

你可以使用函数名，来引用外部函数:
当用户点击元素时弹出 "Hello World!"
element.addEventListener("click", myFunction);

function myFunction() {
    alert ("Hello World!");
}

5.4.向同一个元素中添加多个事件句柄
element.addEventListener("click", myFunction);
element.addEventListener("click", mySecondFunction);

addEventListener() 方法允许向同一个元素添加多个事件，且不会覆盖已存在的事件：
<p>该实例使用 addEventListener() 方法向同个按钮中添加两个点击事件。</p>
<button id="myBtn2">点我</button>
<script>
    var x = document.getElementById("myBtn2");
    x.addEventListener("click", myFunction);
    x.addEventListener("click", someOtherFunction);
    function myFunction(){
        alert("Hello World!")
    }
    function someOtherFunction(){
        alert("函数已执行")
    }
</script>

你可以向同个元素添加不同类型的事件：
element.addEventListener("mouseover", myFunction);
element.addEventListener("click", mySecondFunction);
element.addEventListener("mouseout", myThirdFunction);
<p>实例使用 addEventListener() 方法在同一个按钮中添加多个事件。</p>
<button id="myBtn">点我</button>
<p id="demo1"></p>
<script>
var x = document.getElementById("myBtn");
x.addEventListener("mouseover", myFunction);
x.addEventListener("click", mySecondFunction);
x.addEventListener("mouseout", myThirdFunction);
function myFunction() {
    document.getElementById("demo1").innerHTML += "Moused over!<br>"
}
function mySecondFunction() {
    document.getElementById("demo").innerHTML += "Clicked!<br>"
}
function myThirdFunction() {
    document.getElementById("demo").innerHTML += "Moused out!<br>"
}
</script>


5.5.向 Window 对象添加事件句柄
addEventListener() 方法允许你在 HTML DOM 对象添加事件监听， HTML DOM 对象如： HTML 元素,
HTML 文档, window 对象。或者其他支持的事件对象如: xmlHttpRequest 对象。
<h2>当用户重置窗口大小时添加事件监听：</h2>
<p>实例在 window 对象中使用 addEventListener() 方法。</p>
<p>尝试重置浏览器的窗口触发 "resize" 事件句柄。</p>
<p id="demo3"></p>
<script>
    window.addEventListener("resize", function (){
        document.getElementById("demo3").innerHTML = Math.random();
    })
</script>

5.6.传递参数
当传递参数值时，使用"匿名函数"调用带参数的函数：
<p>实例演示了在使用 addEventListener() 方法时如何传递参数。</p>
<p>点击按钮执行计算。</p>
<button id="myBtn3">点我</button>
<p id="demo4"></p>
<script>
    var p1 = 5;
    var p2 = 8;
    document.getElementById("myBtn3").addEventListener("click", function (){
        myFunction(p1, p2);
    })
    function myFunction(a, b){
        var result = a * b;
        document.getElementById("demo4").innerHTML = result;
    }
</script>


5.7.事件冒泡或事件捕获？
事件传递有两种方式：冒泡与捕获。

事件传递定义了元素事件触发的顺序。 如果你将 p 元素插入到 div 元素中，用户点击 p 元素, 哪个元素的 "click" 事件先被触发呢？

在 冒泡 中，内部元素的事件会先被触发，然后再触发外部元素，即： p 元素的点击事件先触发，然后会触发 div 元素的点击事件。

在 捕获 中，外部元素的事件会先被触发，然后才会触发内部元素的事件，即： div 元素的点击事件先触发 ，然后再触发 p 元素的点击事件。

addEventListener() 方法可以指定 "useCapture" 参数来设置传递类型：<br>
addEventListener(event, function, useCapture);<br>
<br>
默认值为 false, 即冒泡传递，当值为 true 时, 事件使用捕获传递。<br>
<p>实例演示了在添加不同事件监听时，冒泡与捕获的不同。</p><br>
<div id="myDiv">
    <p id="myP">点击段落，我是冒泡</p>
</div><br>
<div id="myDiv2">
    <p id="myP2">点击段落，我是捕获</p>
</div><br>
<script>
    document.getElementById("myP").addEventListener("click", function (){
        alert("你点击P元素！");
    }, false);
    document.getElementById("myDiv").addEventListener("click", function (){
        alert("你点击了DIV元素！")
    }, false)
    document.getElementById("myP2").addEventListener("click", function (){
        alert("你点击了P2元素！")
    }, true)
    document.getElementById("myDiv2").addEventListener("click", function(){
        alert("你点击了DIV2元素!")
    }, true)
</script>


5.8.removeEventListener() 方法
removeEventListener() 方法移除由 addEventListener() 方法添加的事件句柄:


6.JavaScript HTML DOM 元素 (节点)
本章节介绍如何向文档中添加和移除元素(节点)。

6.1.创建新的 HTML 元素 (节点) - appendChild()(添加新元素到尾部）
要创建新的 HTML 元素 (节点)需要先创建一个元素，然后在已存在的元素中添加它
<div id="div1" >
    <p id="p1">这是个段落。</p>
    <p id="p2">这是另外一个段落</p>
</div>
<script>
    var para = document.createElement("p");
    var node = document.createTextNode("这是新增加的段落");
    para.appendChild(node);

    var element = document.getElementById("div1");
    var chid = document.getElementById("p1")
    element.appendChild(para);  //appendChild() 添加新元素到尾部
    element.insertBefore(para, chid);//insertBefore()（新元素// 添加到开始位置）
    // parent.removeChild(child);//removeChild,移除已存在的元素

</script>
实例解析
以下代码是用于创建 p 元素:

var para = document.createElement("p");
为 p 元素创建一个新的文本节点：

var node = document.createTextNode("这是一个新的段落。");
将文本节点添加到 p 元素中：

para.appendChild(node);
最后，在一个已存在的元素中添加 p 元素。

查找已存在的元素：

var element = document.getElementById("div1");
添加到已存在的元素中:

element.appendChild(para);


6.2.创建新的 HTML 元素 (节点) - insertBefore()（新元素添加到开始位置）
以上的例我们使用了 appendChild() 方法，它用于添加新元素到尾部。
如果我们需要将新元素添加到开始位置，可以使用 insertBefore() 方法:

移除已存在的元素
要移除一个元素，你需要知道该元素的父元素。
<!--<div id="div1">-->
<!--<p id="p1">这是一个段落。</p>-->
<!--<p id="p2">这是另外一个段落。</p>-->
<!--</div>-->
<!-- -->
<!--<script>-->
<!--var parent = document.getElementById("div1");-->
<!--var child = document.getElementById("p1");-->
<!--parent.removeChild(child);-->
<!--</script>-->
实例解析
<!--HTML 文档中 <div> 元素包含两个子节点 (两个 <p> 元素):-->

<!--<div id="div1">-->
<!--<p id="p1">这是一个段落。</p>-->
<!--<p id="p2">这是另外一个段落。</p>-->
<!--</div>-->
查找 id="div1" 的元素:

var parent = document.getElementById("div1");
查找 id="p1" 的 p 元素:

var child = document.getElementById("p1");
从父元素中移除子节点：

parent.removeChild(child);

	如果能够在不引用父元素的情况下删除某个元素，就太好了。
不过很遗憾。DOM 需要清楚您需要删除的元素，以及它的父元素。

以下代码是已知要查找的子元素，然后查找其父元素，再删除这个子元素（删除节点必须知道父节点）：
var child = document.getElementById("p1");
child.parentNode.removeChild(child);

6.3.替换 HTML 元素 - replaceChild()
我们可以使用 replaceChild() 方法来替换 HTML DOM 中的元素。

实例
<div id="div2">
<p id="p3">这是一个段落。</p>
<p id="p4">这是另外一个段落。</p>
</div>

<script>
var para = document.createElement("p");
var node = document.createTextNode("这是一个新的段落。");
para.appendChild(node);

var parent = document.getElementById("div2");
var child = document.getElementById("p3");
parent.replaceChild(para, child);
</script>

6.4.HTML DOM 教程
在我们的 JavaScript 教程的 HTML DOM 部分，您已经学到了：
    如何改变 HTML 元素的内容 (innerHTML)
    如何改变 HTML 元素的样式 (CSS)
    如何对 HTML DOM 事件作出反应
    如何添加或删除 HTML 元素


7.JavaScript HTML DOM 集合(Collection)
本章节介绍 DOM 集合的使用。

7.1.HTMLCollection 对象
getElementsByTagName() 方法返回 HTMLCollection 对象。
HTMLCollection 对象类似包含 HTML 元素的一个数组。
以下代码获取文档所有的 p 元素：
<p>狮子</p>
<p>熊猫</p>
<p id="de">老虎</p>
<p id="de1"></p>
<script>
    var x = document.getElementsByTagName("p")//获取文档所有的 <p> 元素

    //集合 length 属性常用于遍历集合中的元素。修改所有 <p> 元素的背景颜色:
    var i;
    for (i = 0; i < x.length; i++){
        x[i].style.backgroundColor = "red";
    }
    //代码获取文档所有的 <p> 元素：
    document.getElementById("de").innerHTML =
        "第二段落的内容为：<span style='color:red;'>" + x[1].innerHTML + '</span>' //获取第二p的标签的内容
    //HTMLCollection 对象的 length 属性定义了集合中元素的数量。
    document.getElementById("de1").innerHTML = "文档一共有" + x.length + "个段落 ";
</script>


7.2.HTMLCollection 对象 length 属性
HTMLCollection 对象的 length 属性定义了集合中元素的数量。
实例解析
获取 p 元素的集合：
var myCollection = document.getElementsByTagName("p");
显示集合元素个数：
document.getElementById("demo").innerHTML = myCollection.length;
集合 length 属性常用于遍历集合中的元素。
修改所有 p 元素的背景颜色:


注意
HTMLCollection 不是一个数组！

HTMLCollection 看起来可能是一个数组，但其实不是。

你可以像数组一样，使用索引来获取元素。

HTMLCollection 无法使用数组的方法： valueOf(), pop(), push(), 或 join() 。

8.JavaScript HTML DOM 节点列表
NodeList 对象是一个从文档中获取的节点列表 (集合) 。

NodeList 对象类似 HTMLCollection 对象。

一些旧版本浏览器中的方法（如：getElementsByClassName()）返回的是 NodeList 对象，而不是 HTMLCollection 对象。

所有浏览器的 childNodes 属性返回的是 NodeList 对象。

大部分浏览器的 querySelectorAll() 返回 NodeList 对象。

以下代码选取了文档中所有的 p 节点：
<p>熊猫</p>
<p>食铁兽</p>
<p>大熊猫</p>
<p id="demo"></p>
<p id="demo1"></p>
<script>
  //获取 p 元素的集合：
  var myNodelist = document.querySelectorAll("p");

  //length 属性常用于遍历节点列表。把每个p元素的背景颜色变为红色
  var i;
  for (i=0; i < myNodelist.length; i++){
    myNodelist[i].style.backgroundColor = "red"
  }
  //NodeList 中的元素可以通过索引(以 0 为起始位置)来访问。
  //访问第二个 <p> 元素可以是以下代码:
  var y = myNodelist[1];
  document.getElementById("demo").innerHTML = "集合中第二个标签内容为：" + y.innerHTML;
  //示节点列表的元素个数：
  document.getElementById("demo1").innerHTML= "集合一共有" + myNodelist.length + "个p元素"
</script>

实例解析
获取 p 元素的集合：
var myNodelist = document.querySelectorAll("p");
显示节点列表的元素个数：

document.getElementById("demo").innerHTML = myNodelist.length;


length 属性常用于遍历节点列表。
修改节点列表中所有 p 元素的背景颜色:
var myNodelist = document.querySelectorAll("p");
var i;
for (i = 0; i < myNodelist.length; i++) {
    myNodelist[i].style.backgroundColor = "red";
}

HTMLCollection 与 NodeList 的区别
HTMLCollection 是 HTML 元素的集合。
NodeList 是一个文档节点的集合。
NodeList 与 HTMLCollection 有很多类似的地方。
NodeList 与 HTMLCollection 都与数组对象有点类似，可以使用索引 (0, 1, 2, 3, 4, ...) 来获取元素。
NodeList 与 HTMLCollection 都有 length 属性。
HTMLCollection 元素可以通过 name，id 或索引来获取。
NodeList 只能通过索引来获取。.

只有 NodeList 对象有包含属性节点和文本节点。

节点列表不是一个数组！

节点列表看起来可能是一个数组，但其实不是。

你可以像数组一样，使用索引来获取元素。

节点列表无法使用数组的方法： valueOf(), pop(), push(), 或 join() 。
