25.<head>
    <meta charset="UTF-8">
    <title>JavaScript 错误 - throw、try 和 catch</title>
<!--    <script>-->
<!--    var txt="";-->
<!--    function message(){-->
<!--        try{-->
<!--            adddlert("Welcome guest!");-->
<!--        }-->
<!--        catch (err){-->
<!--            txt="本页有个错误"-->
<!--            txt+="错误描述：" + err.message + "\n\n";-->
<!--            txt+="点击确定继续。\n\n";-->
<!--            alert(txt);-->
<!--        }-->
<!--    }-->
<!--</script>-->
</head>
<body>
JavaScript 错误 - throw、try 和 catch
try 语句测试代码块的错误。
catch 语句处理错误。
throw 语句创建自定义错误。
finally 语句在 try 和 catch 语句之后，无论是否有触发异常，该语句都会执行。

25.1. JavaScript 错误
当 JavaScript 引擎执行 JavaScript 代码时，会发生各种错误。
可能是语法错误，通常是程序员造成的编码错误或错别字。
可能是拼写错误或语言中缺少的功能（可能由于浏览器差异）。
可能是由于来自服务器或用户的错误输出而导致的错误。
当然，也可能是由于许多其他不可预知的因素。

25.2.JavaScript 抛出（throw）错误
当错误发生时，当事情出问题时，JavaScript 引擎通常会停止，并生成一个错误消息。
描述这种情况的技术术语是：JavaScript 将抛出一个错误。

25.3.JavaScript try 和 catch
try 语句允许我们定义在执行时进行错误测试的代码块。
catch 语句允许我们定义当 try 代码块发生错误时，所执行的代码块。
JavaScript 语句 try 和 catch 是成对出现的。
语法
try {
    ...    //异常的抛出
} catch(e) {
    ...    //异常的捕获与处理
} finally {
    ...    //结束处理
}
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

25.4.Throw 语句
throw 语句允许我们创建自定义错误。

正确的技术术语是：创建或抛出异常（exception）。

如果把 throw 与 try 和 catch 一起使用，那么您能够控制程序流，并生成自定义的错误消息。

语法
throw exception
异常可以是 JavaScript 字符串、数字、逻辑值或对象。

实例
本例检测输入变量的值。如果值是错误的，会抛出一个异常（错误）。catch 会捕捉到这个错误，并显示一段自定义的错误消息：
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
请注意，如果 getElementById 函数出错，上面的例子也会抛出一个错误。
</body>

26.JavaScript 调试
在编写 JavaScript 时，如果没有调试工具将是一件很痛苦的事情。

JavaScript 调试
没有调试工具是很难去编写 JavaScript 程序的。
你的代码可能包含语法错误，逻辑错误，如果没有调试工具，这些错误比较难于发现。
通常，如果 JavaScript 出现错误，是不会有提示信息，这样你就无法找到代码错误的位置。

26.1.JavaScript 调试工具
在程序代码中寻找错误叫做代码调试。
调试很难，但幸运的是，很多浏览器都内置了调试工具。
内置的调试工具可以开始或关闭，严重的错误信息会发送给用户。
有了调试工具，我们就可以设置断点 (代码停止执行的位置), 且可以在代码执行时检测变量。
浏览器启用调试工具一般是按下 F12 键，并在调试菜单中选择 "Console" 。

26.2.console.log() 方法
如果浏览器支持调试，你可以使用 console.log() 方法在调试窗口上打印 JavaScript 值：
<script>
    a= 5;
    b= 6;
    c= a + b;
    console.log(c);
</script>

26.2.1设置断点
在调试窗口中，你可以设置 JavaScript 代码的断点。
在每个断点上，都会停止执行 JavaScript 代码，以便于我们检查 JavaScript 变量的值。
在检查完毕后，可以重新执行代码（如播放按钮）


26.2.2debugger 关键字
debugger 关键字用于停止执行 JavaScript，并调用调试函数。
这个关键字与在调试工具中设置断点的效果是一样的。
如果没有调试可用，debugger 语句将无法工作。
开启 debugger ，代码在第三行前停止执行。

var x = 15 * 5;
debugger;
document.getElementbyId("demo").innerHTML = x;

26.3.主要浏览器的调试工具
通常，浏览器启用调试工具一般是按下 F12 键，并在调试菜单中选择 "Console" 。
各浏览器的步骤如下:
    Chrome 浏览器
    打开浏览器。
    在菜单中选择 "更多工具"。
    在 "更多工具" 中选择 "开发者工具"。
    最后，选择 Console。

27.JavaScript 声明提升
JavaScript 中，函数及变量的声明都将被提升到函数的最顶部。
JavaScript 中，变量可以在使用后声明，也就是变量可以先使用再声明。
以下两个实例将获得相同的结果：
案例1：
x = 5; // 变量 x 设置为 5

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x;                     // 在元素中显示 x

var x; // 声明 x

案例2：
var x; // 声明 x
x = 5; // 变量 x 设置为 5

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x;                     // 在元素中显示 x

要理解以上实例就需要理解 "hoisting(声明提升)"。
声明提升：函数声明和变量声明总是会被解释器悄悄地被"提升"到方法体的最顶部。

27.1.JavaScript 初始化不会提升
JavaScript 只有声明的变量会提升，初始化的不会。

以下两个实例结果结果不相同：
案例1；
var x = 5; // 初始化 x
var y = 7; // 初始化 y

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y

案例2；
var x = 5; // 初始化 x

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y

var y = 7; // 初始化 y

实例 2 的 y 输出了 undefined，这是因为变量声明 (var y) 提升了，但是初始化(y = 7) 并不会提升，所以 y 变量是一个未定义的变量。

实例 2 类似以下代码:
var x = 5; // 初始化 x
var y;     // 声明 y

elem = document.getElementById("demo"); // 查找元素
elem.innerHTML = x + " " + y;           // 显示 x 和 y

y = 7;    // 设置 y 为 7

在头部声明你的变量
对于大多数程序员来说并不知道 JavaScript 声明提升。

如果程序员不能很好的理解声明提升，他们写的程序就容易出现一些问题。

为了避免这些问题，通常我们在每个作用域开始前声明这些变量，这也是正常的 JavaScript 解析步骤，易于我们理解

avaScript 严格模式(strict mode)不允许使用未声明的变量。
在下一个章节中我们将会学习到 "严格模式(strict mode)" 。

28.JavaScript 使用误区

28.1.赋值运算符应用错误
在 JavaScript 程序中如果你在 if 条件语句中使用赋值运算符的等号 (=) 将会产生一个错误结果, 正确的方法是使用比较运算符的两个等号 (==)。

1.1.if 条件语句返回 false (是我们预期的)因为 x 不等于 10:
var x = 0;
if (x == 10)

1.2.if 条件语句返回 true (不是我们预期的)因为条件语句执行为 x 赋值 10，10 为 true:
var x = 0;
if (x = 10)

1.3if 条件语句返回 false (不是我们预期的)因为条件语句执行为 x 赋值 0，0 为 false:
var x = 0;
if (x = 0)

赋值语句返回变量的值。

28.2.比较运算符常见错误
28.2.1在常规的比较中，数据类型是被忽略的，以下 if 条件语句返回 true：
var x = 10;
var y = "10";
if (x == y)

28.2.2在严格的比较运算中，=== 为恒等计算符，同时检查表达式的值与类型，以下 if 条件语句返回 false：
var x = 10;
var y = "10";
if (x === y)
这种错误经常会在 switch 语句中出现，switch 语句会使用恒等计算符(===)进行比较:

28.2.3以下实例会执行 alert 弹窗：
var x = 10;
switch(x) {
    case 10: alert("Hello");
}

2.4以下实例由于类型不一致不会执行 alert 弹窗：
var x = 10;
switch(x) {
    case "10": alert("Hello");
}

28.3.加法与连接注意事项
加法是两个数字相加。
连接是两个字符串连接。
JavaScript 的加法和连接都使用 + 运算符。

28.3.1接下来我们可以通过实例查看两个数字相加及数字与字符串连接的区别：
var x = 10 + 5;          // x 的结果为 15
var x = 10 + "5";        // x 的结果为 "105"

28.3.2使用变量相加结果也不一致:

var x = 10;
var y = 5;
var z = x + y;           // z 的结果为 15

var x = 10;
var y = "5";
var z = x + y;           // z 的结果为 "105"

28.4.浮点型数据使用注意事项
JavaScript 中的所有数据都是以 64 位浮点型数据(float) 来存储。

所有的编程语言，包括 JavaScript，对浮点型数据的精确度都很难确定：

var x = 0.1;
var y = 0.2;
var z = x + y            // z 的结果为 0.30000000000000004
if (z == 0.3)            // 返回 false
为解决以上问题，可以用整数的乘除法来解决：

实例
var z = (x * 10 + y * 10) / 10;       // z 的结果为 0.3

28.5.JavaScript 字符串分行
JavaScript 允许我们在字符串中使用断行语句:

实例 1
var x =
"Hello World!";
但是，在字符串中直接使用回车换行是会报错的：

实例 2
var x = "Hello
World!";

字符串断行需要使用反斜杠(\)，如下所示:

实例 3
var x = "Hello \
World!";

28.6.错误的使用分号
以下实例中，if 语句失去方法体，原 if 语句的方法体作为独立的代码块被执行，导致错误的输出结果。

由于分号使用错误，if 语句中的代码块就一定会执行：

if (x == 19);
{
    // code block
}

28.7.return 语句使用注意事项
JavaScript 默认是在一行的末尾自动结束。

以下两个实例返回结果是一样的(一个有分号一个没有):

实例 1
function myFunction(a) {
    var power = 10
    return a * power
}

实例 2
function myFunction(a) {
    var power = 10;
    return a * power;
}
JavaScript 也可以使用多行来表示一个语句，也就是说一个语句是可以分行的。

以下实例返回相同的结果:

实例 3
function myFunction(a) {
    var
    power = 10;
    return a * power;
}

但是，以下实例结果会返回 undefined：
function myFunction(a) {
    var
    power = 10;
    return
}

为什么会有这样的结果呢？因为在 JavaScript 中，实例 4 的代码与下面的代码一致：

function myFunction(a) {
    var
    power = 10;
    return;       // 分号结束，返回 undefined
    a * power;
}

解析
如果是一个不完整的语句，如下所示:

var
JavaScript 将尝试读取第二行的语句：

power = 10;
但是由于这样的语句是完整的:

return
JavaScript 将自动关闭语句:

return;
在 JavaScript 中，分号是可选的 。

由于 return 是一个完整的语句，所以 JavaScript 将关闭 return 语句。
不用对 return 语句进行断行。

28.8.数组中使用名字来索引
许多程序语言都允许使用名字来作为数组的索引。
使用名字来作为索引的数组称为关联数组(或哈希)。
JavaScript 不支持使用名字来索引数组，只允许使用数字索引。
var person = [];
person[0] = "John";
person[1] = "Doe";
person[2] = 46;
var x = person.length;         // person.length 返回 3
var y = person[0];             // person[0] 返回 "John"

在 JavaScript 中, 对象 使用 名字作为索引。
如果你使用名字作为索引，当访问数组时，JavaScript 会把数组重新定义为标准对象。
执行这样操作后，数组的方法及属性将不能再使用，否则会产生错误:
var person = [];
person["firstName"] = "John";
person["lastName"] = "Doe";
person["age"] = 46;
var x = person.length;         // person.length 返回 0
var y = person[0];             // person[0] 返回 undefined


28.9.定义数组元素，最后不能添加逗号
数组最后一个值的后面添加逗号虽然语法没有问题，但是在不同的浏览器可能得到不同的结果。

var colors = [5, 6, 7,]; //这样数组的长度可能为3 也可能为4。
正确的定义方式：

points = [40, 100, 1, 5, 25, 10];

28.10.定义对象，最后不能添加逗号
错误的定义方式：

websites = {site:"菜鸟教程", url:"www.runoob.com", like:460,}
正确的定义方式：

websites = {site:"菜鸟教程", url:"www.runoob.com", like:460}

28.11.Undefined 不是 Null
在 JavaScript 中, null 用于对象, undefined 用于变量，属性和方法。

对象只有被定义才有可能为 null，否则为 undefined。

如果我们想测试对象是否存在，在对象还没定义时将会抛出一个错误。

错误的使用方式：

if (myObj !== null && typeof myObj !== "undefined")
正确的方式是我们需要先使用 typeof 来检测对象是否已定义：

if (typeof myObj !== "undefined" && myObj !== null) 

28.12.程序块作用域
在每个代码块中 JavaScript 不会创建一个新的作用域，一般各个代码块的作用域都是全局的。

以下代码的的变量 i 返回 10，而不是 undefined：

实例
for (var i = 0; i < 10; i++) {
    // some code
}
return i


29.JavaScript 表单
29.1.JavaScript 表单验证
HTML 表单验证可以通过 JavaScript 来完成。

以下实例代码用于判断表单字段(fname)值是否存在， 如果不存在，就弹出信息，阻止表单提交：
function validateForm() {
    var x = document.forms["myForm"]["fname"].value;
    if (x == null || x == "") {
        alert("需要输入名字。");
        return false;
    }
}

以上 JavaScript 代码可以通过 HTML 代码来调用：

HTML 表单实例
<!--<form name="myForm" action="demo_form.php" onsubmit="return validateForm()" method="post">-->
<!--名字: <input type="text" name="fname">-->
<!--<input type="submit" value="提交">-->
<!--</form>-->

29.2.JavaScript 验证输入的数字
JavaScript 常用于对输入数字的验证：
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

29.3.HTML 表单自动验证
HTML 表单验证也可以通过浏览器来自动完成。
如果表单字段 (fname) 的值为空, required 属性会阻止表单提交：
<!--<form action="demo_form.php" method="post">-->
<!--  <input type="text" name="fname" required="required">-->
<!--  <input type="submit" value="提交">-->
<!--</form>-->

29.4.数据验证
数据验证用于确保用户输入的数据是有效的。

典型的数据验证有：

必需字段是否有输入?
用户是否输入了合法的数据?
在数字字段是否输入了文本?
大多数情况下，数据验证用于确保用户正确输入数据。

数据验证可以使用不同方法来定义，并通过多种方式来调用。

服务端数据验证是在数据提交到服务器上后再验证。

客户端数据验证是在数据发送到服务器前，在浏览器上完成验证。

29.5.HTML 约束验证
HTML5 新增了 HTML 表单的验证方式：约束验证（constraint validation）。
约束验证是表单被提交时浏览器用来实现验证的一种算法。
HTML 约束验证基于：
    HTML 输入属性
    CSS 伪类选择器
    DOM 属性和方法

29.5.1约束验证 HTML 输入属性
属性	描述
disabled	规定输入的元素不可用
max	规定输入元素的最大值
min	规定输入元素的最小值
pattern	规定输入元素值的模式
required	规定输入元素字段是必需的
type 	规定输入元素的类型

29.5.2约束验证 CSS 伪类选择器
选择器	    描述
:disabled	选取属性为 "disabled" 属性的 input 元素
:invalid	选取无效的 input 元素
:optional	选择没有"optional"属性的 input 元素
:required	选择有"required"属性的 input 元素
:valid	选取有效值的 input 元素

30.JavaScript 表单验证
30.1JavaScript 表单验证
JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。

表单数据经常需要使用 JavaScript 来验证其正确性：

验证表单数据是否为空？
验证输入是否是一个正确的email地址？
验证日期是否输入正确？
验证表单输入内容是否为数字型

30.2必填（或必选）项目
下面的函数用来检查用户是否已填写表单中的必填（或必选）项目。假如必填或必选项为空，那么警告框会弹出，并且函数的返回值为 false，否则函数的返回值则为 true（意味着数据没有问题）：

function validateForm()
{
  var x=document.forms["myForm"]["fname"].value;
  if (x==null || x=="")
  {
    alert("姓必须填
以上函数在 form 表单提交时被调用:

实例
<form name="myForm" action="demo-form.php" onsubmit="return validateForm()" method="post">
姓: <input type="text" name="fname">
<input type="submit" value="提交">
</form>写");
    return false;
  }
}

30.3E-mail 验证
下面的函数检查输入的数据是否符合电子邮件地址的基本语法。

意思就是说，输入的数据必须包含 @ 符号和点号(.)。同时，@ 不可以是邮件地址的首字符，并且 @ 之后需有至少一个点号：

function validateForm(){
  var x=document.forms["myForm"]["email"].value;
  var atpos=x.indexOf("@");
  var dotpos=x.lastIndexOf(".");
  if (atpos<1 || dotpos<atpos+2 || dotpos+2>=x.length){
    alert("不是一个有效的 e-mail 地址");
    return false;
  }
}
下面是连同 HTML 表单的完整代码：

实例
<form name="myForm" action="demo-form.php" onsubmit="return validateForm();" method="post">
    Email: <input type="text" name="email">
    <input type="submit" value="提交">
</form>

31.JavaScript 验证 API

31.1.约束验证 DOM 方法
Property	            Description
checkValidity()	        如果 input 元素中的数据是合法的返回 true，否则返回 false。
setCustomValidity()     设置 input 元素的 validationMessage 属性，用于自定义错误提示信息的方法。
                        使用 setCustomValidity 设置了自定义提示后，validity.customError 就会变成 true，checkValidity 总是会返回 false。如果要重新判断需要取消自定义提示，方式如下：
                        setCustomValidity('')
                        setCustomValidity(null)
                        setCustomValidity(undefined)

以下实例如果输入信息不合法，则返回错误信息：
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

31.2.约束验证 DOM 属性
属性	                描述
validity	        布尔属性值，返回 input 输入值是否合法
validationMessage	浏览器错误提示信息
willValidate	    指定 input 是否需要验证

31.2.1Validity 属性
input 元素的 validity 属性包含一系列关于 validity 数据属性:

属性	            描述
customError	    设置为 true, 如果设置了自定义的 validity 信息。
patternMismatch	设置为 true, 如果元素的值不匹配它的模式属性。
rangeOverflow	设置为 true, 如果元素的值大于设置的最大值。
rangeUnderflow	设置为 true, 如果元素的值小于它的最小值。
stepMismatch	设置为 true, 如果元素的值不是按照规定的 step 属性设置。
tooLong	        设置为 true, 如果元素的值超过了 maxLength 属性设置的长度。
typeMismatch	设置为 true, 如果元素的值不是预期相匹配的类型。
valueMissing	设置为 true，如果元素 (required 属性) 没有值。
valid	        设置为 true，如果元素的值是合法的。

32.javascript保留关键字：https://www.runoob.com/js/js-reserved.html

33.JavaScript let 和 const
ECMAScript 2015(ECMAScript 6)
ES2015(ES6) 新增加了两个重要的 JavaScript 关键字: let 和 const。
let 声明的变量只在 let 命令所在的代码块内有效。
const 声明一个只读的常量，一旦声明，常量的值就不能改变。
在 ES6 之前，JavaScript 只有两种作用域： 全局变量 与 函数内的局部变量。

33.1.全局变量
在函数外声明的变量作用域是全局的：
<p id="demo"></p>
<script>
    var carName= "Volvo";
    // 这里可以使用 carName 变量
    function myFuncion(){
        // 这里也可以使用 carName 变量
    }
</script>
全局变量在 JavaScript 程序的任何地方都可以访问。

33.2.局部变量
在函数内声明的变量作用域是局部的（函数内）：
// 这里不能使用 carName 变量

function myFunction() {
    var carName = "Volvo";
    // 这里可以使用 carName 变量
}

// 这里不能使用 carName 变量
函数内使用 var 声明的变量只能在函数内访问，如果不使用 var 则是全局变量。

33.3.JavaScript 块级作用域(Block Scope)
使用 var 关键字声明的变量不具备块级作用域的特性，它在 {} 外依然能被访问到。
{
    var x = 2;
}
// 这里可以使用 x 变量
在 ES6 之前，是没有块级作用域的概念的。

ES6 可以使用 let 关键字来实现块级作用域。

let 声明的变量只在 let 命令所在的代码块 {} 内有效，在 {} 之外不能访问。

{
    let x = 2;
}
// 这里不能使用 x 变量

33.4.重新定义变量
使用 var 关键字重新声明变量可能会带来问题。

在块中重新声明变量也会重新声明块外的变量：
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

33.5.循环作用域
使用 var 关键字：

实例
var i = 5;
for (var i = 0; i < 10; i++) {
    // 一些代码...
}
// 这里输出 i 为 10

使用 let 关键字：
实例
var i = 5;
for (let i = 0; i < 10; i++) {
    // 一些代码...
}
// 这里输出 i 为 5
在第一个实例中，使用了 var 关键字，它声明的变量是全局的，包括循环体内与循环体外。

在第二个实例中，使用 let 关键字， 它声明的变量作用域只在循环体内，循环体外的变量不受影响。

33.6.局部变量
在函数体内使用 var 和 let 关键字声明的变量有点类似。

它们的作用域都是 局部的:

// 使用 var
function myFunction() {
    var carName = "Volvo";   // 局部作用域
}

// 使用 let
function myFunction() {
    let carName = "Volvo";   //  局部作用域
}

33.7.全局变量
在函数体外或代码块外使用 var 和 let 关键字声明的变量也有点类似。

它们的作用域都是 全局的:

// 使用 var
var x = 2;       // 全局作用域

// 使用 let
let x = 2;       // 全局作用域

HTML 代码中使用全局变量
在 JavaScript 中, 全局作用域是针对 JavaScript 环境。

在 HTML 中, 全局作用域是针对 window 对象。

使用 var 关键字声明的全局作用域变量属于 window 对象:

实例
var carName = "Volvo";
// 可以使用 window.carName 访问变量

使用 let 关键字声明的全局作用域变量不属于 window 对象:
let carName = "Volvo";
// 不能使用 window.carName 访问变量

重置变量
使用 var 关键字声明的变量在任何地方都可以修改：

实例
var x = 2;

// x 为 2

var x = 3;

// 现在 x 为 3

在相同的作用域或块级作用域中，不能使用 let 关键字来重置 var 关键字声明的变量:
    var x = 2;       // 合法
    let x = 3;       // 不合法

    {
        var x = 4;   // 合法
        let x = 5   // 不合法
    }

在相同的作用域或块级作用域中，不能使用 let 关键字来重置 let 关键字声明的变量:
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

let 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的:
    let x = 2;       // 合法

    {
        let x = 3;   // 合法
    }

    {
        let x = 4;   // 合法
    }

33.8.变量提升
JavaScript 中，var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明（JavaScript 变量提升）。
实例
// 在这里可以使用 carName 变量

var carName;

let 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。
    // 在这里不可以使用 carName 变量
    let carName;

const 关键字
const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改：
实例
const PI = 3.141592653589793;
PI = 3.14;      // 报错
PI = PI + 10;   // 报错

const定义常量与使用let 定义的变量相似：
    二者都是块级作用域
    都不能和它所在作用域内的其他变量或函数拥有相同的名称
两者还有以下两点区别：
    const声明的常量必须初始化，而let声明的变量不用
    const 定义常量的值不能通过再赋值修改，也不能再次声明。而 let 定义的变量值可以修改。
var x = 10;
// 这里输出 x 为 10
{
    const x = 2;
    // 这里输出 x 为 2
}
// 这里输出 x 为 10


const 声明的常量必须初始化：
// 错误写法
const PI;
PI = 3.14159265359;

// 正确写法
const PI = 3.14159265359;

33.9.并非真正的常量
const 的本质: const 定义的变量并非常量，并非不可变，它定义了一个常量引用一个值。使用 const 定义的对象或者数组，其实是可变的。下面的代码并不会报错：
// 创建常量对象
const car = {type:"Fiat", model:"500", color:"white"};

// 修改属性:
car.color = "red";

// 添加属性
car.owner = "Johnson";

但是我们不能对常量对象重新赋值：
const car = {type:"Fiat", model:"500", color:"white"};
car = {type:"Volvo", model:"EX60", color:"red"};    // 错误

以下实例修改常量数组：
// 创建常量数组
const cars = ["Saab", "Volvo", "BMW"];

// 修改元素
cars[0] = "Toyota";

// 添加元素
cars.push("Audi");

是我们不能对常量数组重新赋值：
实例
const cars = ["Saab", "Volvo", "BMW"];
cars = ["Toyota", "Volvo", "Audi"];    // 错误

33.10.重置变量
使用 var 关键字声明的变量在任何地方都可以修改：
实例
var x = 2;    //  合法
var x = 3;    //  合法
x = 4;        //  合法
在相同的作用域或块级作用域中，不能使用 const 关键字来重置 var 和 let关键字声明的变量:
    var x = 2;         // 合法
    const x = 2;       // 不合法
    {
        let x = 2;     // 合法
        const x = 2;   // 不合法
    }
在相同的作用域或块级作用域中，不能使用 const 关键字来重置 const 关键字声明的变量:
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
const 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的:
    const x = 2;       // 合法

    {
        const x = 3;   // 合法
    }

    {
        const x = 4;   // 合法
    }

33.11.变量提升
JavaScript var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明（JavaScript 变量提升）。
    carName = "Volvo";    // 这里可以使用 carName 变量
    var carName;
const 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。
    carName = "Volvo";    // 在这里不可以使用 carName 变量
    const carName = "Volvo";

34.JavaScript JSON
JSON 是用于存储和传输数据的格式。
JSON 通常用于服务端向网页传递数据 。

34.1.什么是 JSON?
JSON 英文全称 JavaScript Object Notation
JSON 是一种轻量级的数据交换格式。
JSON是独立的语言 *
JSON 易于理解。
    JSON 使用 JavaScript 语法，但是 JSON 格式仅仅是一个文本。
文本可以被任何编程语言读取及作为数据格式传递。

34.2. JSON 实例
以下 JSON 语法定义了 sites 对象: 3 条网站信息（对象）的数组:
{"sites":[
    {"name":"Runoob", "url":"www.runoob.com"},
    {"name":"Google", "url":"www.google.com"},
    {"name":"Taobao", "url":"www.taobao.com"}
]}

34.3.JSON 语法规则
数据为 键/值 对。
数据由逗号分隔。
大括号保存对象
方括号保存数组

34.4.JSON 数据 - 一个名称对应一个值
JSON 数据格式为 键/值 对，就像 JavaScript 对象属性。
键/值对包括字段名称（在双引号中），后面一个冒号，然后是值：
"name":"Runoob"

34.5.JSON 对象
JSON 对象保存在大括号内。
就像在 JavaScript 中, 对象可以保存多个 键/值 对：
{"name":"Runoob", "url":"www.runoob.com"}

34.6.JSON 数组
JSON 数组保存在中括号内。

就像在 JavaScript 中, 数组可以包含对象：

"sites":[
    {"name":"Runoob", "url":"www.runoob.com"},
    {"name":"Google", "url":"www.google.com"},
    {"name":"Taobao", "url":"www.taobao.com"}
]
在以上实例中，对象 "sites" 是一个数组，包含了三个对象。
每个对象为站点的信息（网站名和网站地址）。

34.7.SON 字符串转换为 JavaScript 对象
通常我们从服务器中读取 JSON 数据，并在网页中显示数据。

简单起见，我们网页中直接设置 JSON 字符串 (你还可以阅读我们的 JSON 教程):

首先，创建 JavaScript 字符串，字符串为 JSON 格式的数据：

var text = '{ "sites" : [' +
'{ "name":"Runoob" , "url":"www.runoob.com" },' +
'{ "name":"Google" , "url":"www.google.com" },' +
'{ "name":"Taobao" , "url":"www.taobao.com" } ]}';

然后，使用 JavaScript 内置函数 JSON.parse() 将字符串转换为 JavaScript 对象:
var obj = JSON.parse(text);

最后，在你的页面中使用新的 JavaScript 对象：
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

34.8.相关函数
函数	描述
JSON.parse()	用于将一个 JSON 字符串转换为 JavaScript 对象。
JSON.stringify()	用于将 JavaScript 值转换为 JSON 字符串。

35.</head>
    <script type="text/javascript">
        function getValue(){
            var a, b,c;
            a= void( b = 5, c = 7);
            document.write('a = ' + a + ' b = ' + b +' c = ' + c);
        }
    </script>
</head>
<body>
javascript:void(0) 含义
我们经常会使用到 javascript:void(0) 这样的代码，那么在 JavaScript 中 javascript:void(0) 代表的是什么意思呢？

javascript:void(0) 中最关键的是 void 关键字， void 是 JavaScript 中非常重要的关键字，该操作符指定要计算一个表达式但是不返回值。

语法格式如下：
    void func()
    javascript:void func()
或者
    void(func())
    javascript:void(func())
下面的代码创建了一个超级链接，当用户点击以后不会发生任何事。<br>
<a href="javascript:void(0)">当用户点击以后不会发生任何事</a><br>
当用户链接时，void(0) 计算为 0，但 Javascript 上没有任何效果。<br><br><br>

<p>点击以下链接查看结果</p><br>
<a href="javascript:void(alert('warning!'))">重新点击</a><br><br>


以下实例中参数 a 将返回 undefined :<br>
<form>
    <input type="button" value="点我" onclick="getValue();">
</form>

href="#"与href="javascript:void(0)"的区别
# 包含了一个位置信息，默认的锚是#top 也就是网页的上端。
而javascript:void(0), 仅仅表示一个死链接。
在页面很长的时候会使用 # 来定位页面的具体位置，格式为：# + id。
如果你要定义一个死链接请使用 javascript:void(0) 。


<a href="javascript:void(0);">点我没有反应的!</a>
<a href="#pos">点我定位到指定位置!</a>
<br>
...
<br>
<p id="pos">尾部定位点</p>
<body>

36.JavaScript 异步编程
36.1.异步的概念
    异步（Asynchronous, async）是与同步（Synchronous, sync）相对的概念。
    在我们学习的传统单线程编程中，程序的运行是同步的（同步不意味着所有步骤同时运行，而是指步骤在一个控制流序列中按顺序执行）。而异步的概念则是不保证同步的概念，也就是说，一个异步过程的执行将不再与原有的序列有顺序关系。
    简单来理解就是：同步按你的代码顺序执行，异步不按照代码顺序执行，异步的执行效率更高。
    以上是关于异步的概念的解释，接下来我们通俗地解释一下异步：异步就是从主线程发射一个子线程来完成任务。
36.2.什么时候用异步编程
    在前端编程中（甚至后端有时也是这样），我们在处理一些简短、快速的操作时，例如计算 1 + 1 的结果，往往在主线程中就可以完成。主线程作为一个线程，不能够同时接受多方面的请求。所以，当一个事件没有结束时，界面将无法处理其他请求。
    现在有一个按钮，如果我们设置它的 onclick 事件为一个死循环，那么当这个按钮按下，整个网页将失去响应。
    为了避免这种情况的发生，我们常常用子线程来完成一些可能消耗时间足够长以至于被用户察觉的事情，比如读取一个大文件或者发出一个网络请求。因为子线程独立于主线程，所以即使出现阻塞也不会影响主线程的运行。但是子线程有一个局限：一旦发射了以后就会与主线程失去同步，我们无法确定它的结束，如果结束之后需要处理一些事情，比如处理来自服务器的信息，我们是无法将它合并到主线程中去的。
    为了解决这个问题，JavaScript 中的异步操作函数往往通过回调函数来实现异步任务的结果处理。

36.3.回调函数
回调函数就是一个函数，它是在我们启动一个异步任务的时候就告诉它：等你完成了这个任务之后要干什么。这样一来主线程几乎不用关心异步任务的状态了，他自己会善始善终。
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
setTimeout(function () {
    document.getElementById("demo").innerHTML="RUNOOB!";
}, 3000);

注意：既然 setTimeout 会在子线程中等待 3 秒，在 setTimeout 函数执行之后主线程并没有停止，所以：

setTimeout(function () {
    document.getElementById("demo1").innerHTML="RUNOOB-1!";  // 三秒后子线程执行
}, 3000);
document.getElementById("demo2").innerHTML="RUNOOB-2!";      // 主线程先执行

36.4.异步 AJAX(https://www.runoob.com/ajax/ajax-tutorial.html)
除了 setTimeout 函数以外，异步回调广泛应用于 AJAX 编程。
XMLHttpRequest 常常用于请求来自远程服务器上的 XML 或 JSON 数据。一个标准的 XMLHttpRequest 对象往往包含多个回调：
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



XMLHttpRequest 的 onload 和 onerror 属性都是函数，分别在它请求成功和请求失败时被调用。如果你使用完整的 jQuery 库，也可以更加优雅的使用异步 AJAX：
$.get("https://www.runoob.com/try/ajax/demo_test.php",function(data,status){
    alert("数据: " + data + "\n状态: " + status);
});

37.JavaScript Promise
在学习本章节内容前，你需要先了解什么是异步编程，
Promise 是一个 ECMAScript 6 提供的类，目的是更加优雅地书写复杂的异步任务。

37.1.构造 Promise
现在我们新建一个 Promise 对象：

new Promise(function (resolve, reject) {
    // 要做的事情...
});
通过新建一个 Promise 对象好像并没有看出它怎样 "更加优雅地书写复杂的异步任务"。我们之前遇到的异步任务都是一次异步，如果需要多次调用异步函数呢？例如，如果我想分三次输出字符串，第一次间隔 1 秒，第二次间隔 4 秒，第三次间隔 3 秒：
setTimeout(function () {
    console.log("First");
    setTimeout(function () {
        console.log("Second");
        setTimeout(function () {
            console.log("Third");
        }, 3000);
    }, 4000);
}, 1000);
这段程序实现了这个功能，但是它是用 "函数瀑布" 来实现的。可想而知，在一个复杂的程序当中，用 "函数瀑布" 实现的程序无论是维护还是异常处理都是一件特别繁琐的事情，而且会让缩进格式变得非常冗赘。

现在我们用 Promise 来实现同样的功能：
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
这段代码较长，所以还不需要完全理解它，我想引起注意的是 Promise 将嵌套格式的代码变成了顺序格式的代码。


37.2.Promise 的构造函数
Promise 构造函数是 JavaScript 中用于创建 Promise 对象的内置构造函数。

Promise 构造函数接受一个函数作为参数，该函数是同步的并且会被立即执行，所以我们称之为起始函数。起始函数包含两个参数 resolve 和 reject，分别表示 Promise 成功和失败的状态。

起始函数执行成功时，它应该调用 resolve 函数并传递成功的结果。当起始函数执行失败时，它应该调用 reject 函数并传递失败的原因。

Promise 构造函数返回一个 Promise 对象，该对象具有以下几个方法：
    then：用于处理 Promise 成功状态的回调函数。
    catch：用于处理 Promise 失败状态的回调函数。
    finally：无论 Promise 是成功还是失败，都会执行的回调函数。

下面是一个使用 Promise 构造函数创建 Promise 对象的例子：
当 Promise 被构造时，起始函数会被同步执行：
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
在上面的例子中，我们使用 Promise 构造函数创建了一个 Promise 对象，并使用 setTimeout 模拟了一个异步操作。如果异步操作成功，则调用 resolve 函数并传递成功的结果；如果异步操作失败，则调用 reject 函数并传递失败的原因。然后我们使用 then 方法处理 Promise 成功状态的回调函数，使用 catch 方法处理 Promise 失败状态的回调函数。
这段程序会直接输出 error 或 success。

resolve 和 reject 都是函数，其中调用 resolve 代表一切正常，reject 是出现异常时所调用的：
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

这段程序执行结果是:
    a / b = 0
    End

Promise 类有 .then() .catch() 和 .finally() 三个方法，这三个方法的参数都是一个函数，.then() 可以将参数中的函数添加到当前 Promise 的正常执行序列，.catch() 则是设定 Promise 的异常处理序列，.finally() 是在 Promise 执行的最后一定会执行的序列。 .then() 传入的函数会按顺序依次执行，有任何异常都会直接跳到 catch 序列：
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
执行结果：

    1111
    2222
    3333
    An error

resolve() 中可以放置一个参数用于向下一个 then 传递一个值，then 中的函数也可以返回一个值传递给 then。但是，如果 then 中返回的是一个 Promise 对象，那么下一个 then 将相当于对这个返回的 Promise 进行操作，这一点从刚才的计时器的例子中可以看出来。

reject() 参数中一般会传递一个异常给之后的 catch 函数用于处理异常。

但是请注意以下两点：
    resolve 和 reject 的作用域只有起始函数，不包括 then 以及其他序列；
    resolve 和 reject 并不能够使起始函数停止运行，别忘了 return。

37.3.Promise 函数
上述的 "计时器" 程序看上去比函数瀑布还要长，所以我们可以将它的核心部分写成一个 Promise 函数：
function print(delay, message) {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            console.log(message);
            resolve();
        }, delay);
    });
}

然后我们就可以放心大胆的实现程序功能了：

实例
print(1000, "First").then(function () {
    return print(4000, "Second");
}).then(function () {
    print(3000, "Third");
});
这种返回值为一个 Promise 对象的函数称作 Promise 函数，它常常用于开发基于异步操作的库。

37.4.回答常见的问题（FAQ）
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

37.5.异步函数
异步函数（async function）是 ECMAScript 2017 (ECMA-262) 标准的规范，几乎被所有浏览器所支持，除了 Internet Explorer。

在 Promise 中我们编写过一个 Promise 函数：

实例
function print(delay, message) {
    return new Promise(function (resolve, reject) {
        setTimeout(function () {
            console.log(message);
            resolve();
        }, delay);
    });
}

然后用不同的时间间隔输出了三行文本：
print(1000, "First").then(function () {
    return print(4000, "Second");
}).then(function () {
    print(3000, "Third");
});

我们可以将这段代码变得更好看：
async function asyncFunc() {
    await print(1000, "First");
    await print(4000, "Second");
    await print(3000, "Third");
}
asyncFunc();

哈！这岂不是将异步操作变得像同步操作一样容易了吗！

这次的回答是肯定的，异步函数 async function 中可以使用 await 指令，await 指令后必须跟着一个 Promise，异步函数会在这个 Promise 运行中暂停，直到其运行结束再继续运行。

异步函数实际上原理与 Promise 原生 API 的机制是一模一样的，只不过更便于程序员阅读。

处理异常的机制将用 try-catch 块实现：
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

如果 Promise 有一个正常的返回值，await 语句也会返回它：
async function asyncFunc() {
    let value = await new Promise(
        function (resolve, reject) {
            resolve("Return value");
        }
    );
    console.log(value);
}
asyncFunc();

程序会输出:
Return value


38.JavaScript 代码规范
所有的 JavaScript 项目适用同一种规范。

38.1.JavaScript 代码规范
代码规范通常包括以下几个方面:
    变量和函数的命名规则
    空格，缩进，注释的使用规则。
    其他常用规范……
    规范的代码可以更易于阅读与维护。

代码规范一般在开发前规定，可以跟你的团队成员来协商设置。

38.2.变量名
变量名推荐使用驼峰法来命名(camelCase):

firstName = "John";
lastName = "Doe";

price = 19.90;
tax = 0.20;

fullPrice = price + (price * tax);

38.3.空格与运算符
通常运算符 ( = + - * / ) 前后需要添加空格:

实例:
var x = y + z;
var values = ["Volvo", "Saab", "Fiat"];

38.4.代码缩进
通常使用 4 个空格符号来缩进代码块：

函数:
function toCelsius(fahrenheit) {
    return (5 / 9) * (fahrenheit - 32);
}
不推荐使用 TAB 键来缩进，因为不同编辑器 TAB 键的解析不一样。

38.5.语句规则
简单语句的通用规则:

一条语句通常以分号作为结束符。
实例:
var values = ["Volvo", "Saab", "Fiat"];

var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
};
复杂语句的通用规则:
    将左花括号放在第一行的结尾。
    左花括号前添加一空格。
    将右花括号独立放在一行。
    以分号结束一个复杂的声明。

函数:
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

38.6.对象规则
对象定义的规则:

将左花括号与类名放在同一行。
冒号与属性值间有个空格。
字符串使用双引号，数字不需要。
最后一个属性-值对后面不要添加逗号。
将右花括号独立放在一行，并以分号作为结束符号。
实例:
var person = {
    firstName: "John",
    lastName: "Doe",
    age: 50,
    eyeColor: "blue"
};

短的对象代码可以直接写成一行:

实例:
var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

38.7.每行代码字符小于 80
为了便于阅读每行字符建议小于数 80 个。

如果一个 JavaScript 语句超过了 80 个字符，建议在 运算符或者逗号后换行。

实例:
document.getElementById("demo").innerHTML =
    "Hello Runoob.";

38.8.命名规则
一般很多代码语言的命名规则都是类似的，例如:

变量和函数为小驼峰法标识, 即除第一个单词之外，其他单词首字母大写（ lowerCamelCase）
全局变量为大写 (UPPERCASE )
常量 (如 PI) 为大写 (UPPERCASE )
变量命名你是否使用这几种规则： hyp-hens, camelCase, 或 under_scores ?

HTML 和 CSS 的横杠(-)字符:

HTML5 属性可以以 data- (如：data-quantity, data-price) 作为前缀。

CSS 使用 - 来连接属性名 (font-size)。
    通常在 JavaScript 中被认为是减法，所以不允许使用。

下划线:

很多程序员比较喜欢使用下划线(如：date_of_birth), 特别是在 SQL 数据库中。

PHP 语言通常都使用下划线。

帕斯卡拼写法(PascalCase):

帕斯卡拼写法(PascalCase) 在 C 语言中语言较多。

驼峰法：

JavaScript 中通常推荐使用驼峰法，jQuery 及其他 JavaScript 库都使用驼峰法。
    变量名不要以 $ 作为开始标记，会与很多 JavaScript 库冲突。

38.9.HTML 载入外部 JavaScript 文件
使用简洁的格式载入 JavaScript 文件 ( type 属性不是必须的):
script src="myscript.js"

38.10.使用 JavaScript 访问 HTML 元素
一个糟糕的 HTML 格式可能会导致 JavaScript 执行错误。

以下两个 JavaScript 语句会输出不同结果:

实例
var obj = getElementById("Demo")

var obj = getElementById("demo")

38.11.文件扩展名
HTML 文件后缀可以是 .html (或 .htm)。

CSS 文件后缀是 .css 。

JavaScript 文件后缀是 .js 。

38.12.使用小写文件名
大多 Web 服务器 (Apache, Unix) 对大小写敏感： london.jpg 不能通过 London.jpg 访问。

其他 Web 服务器 (Microsoft, IIS) 对大小写不敏感： london.jpg 可以通过 London.jpg 或 london.jpg 访问。

你必须保持统一的风格，我们建议统一使用小写的文件名。
