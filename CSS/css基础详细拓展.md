CSS参考手册：https://www.runoob.com/cssref/css-reference.html#text

# 1.什么是 CSS?

	  CSS 指层叠样式表 (Cascading Style Sheets)
	  样式定义如何显示 HTML 元素
	  样式通常存储在样式表中
	  把样式添加到 HTML 4.0 中，是为了解决内容与表现分离的问题
	  外部样式表可以极大提高工作效率
	  外部样式表通常存储在 CSS 文件中
	  多个样式定义可层叠为一个

  
# 2.CSS语法

```css
p {color:red;text-align:center;}
  CSS主要有两部分：选择器以及一条或者多条声明组成
  <!--P标签是一个选择器-->
  <!--color:red表示一个声明，color与red为属性-->
```

# 3 CSS id 和 class
id 和 class 选择器
**如果你要在HTML元素中设置CSS样式，你需要在元素中设置"id" 和 "class"选择器。**

## 3.1 id 选择器
**id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。**
**HTML元素以id属性来设置id选择器,CSS 中 id 选择器以 "#" 来定义**。
以下的样式规则应用于元素属性 id="para1":

演示
```css
<head>
    <meta charset="UTF-8">
    <title>CSS id和Class选择器</title>
    <style>
    #para1
    {
        text-align:center;
        color:red;
    }
    </style>
</head>
<body>
<p id="para1">用id选择CSS渲染</p>
<p>这是正常段落演示</p>
</body>
```

## 3.2 class 选择器
**class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用**。

**class 选择器在 HTML 中以 class 属性表示, 在 CSS 中，类选择器以一个点 . 号显示**：

在以下的例子中，所有拥有 center 类的 HTML 元素均为居中。
```css
 <style>
    .center
    {
        text-align: center;
    }
    </style>
<h1 class="center">标题居中利用classs选择器展示</h1>
<p class="center">段落居中利用classs选择器展示</p>
```

# 4.CSS 创建

当读到一个样式表时，浏览器会根据它来格式化 HTML 文档。

如何插入样式表
插入样式表的方法有三种:

	外部样式表(External style sheet)
	内部样式表(Internal style sheet)
	内联样式(Inline style)


## 4.1 外部样式表

**当样式需要应用于很多页面时，外部样式表将是理想的选择**。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用 \<link> 标签链接到样式表。 \<link> 标签在（文档的）头部：
```css
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```
浏览器会从文件 mystyle.css 中读到样式声明，并根据它来格式文档。


外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的 html 标签。**样式表应该以 .css 扩展名进行保存**。下面是一个样式表文件的例子：
```css
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("/images/back40.gif");}
```
**不要在属性值与单位之间留有空格**（如："margin-left: 20 px" ），正确的写法是 "margin-left: 20px" 

## 4.2 内部样式表
**当单个文档需要特殊的样式时，就应该使用内部样式表**。你可以**使用 <style> 标签在文档头部定义内部样式表**，就像这样:
```css
<head>
<style>
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("images/back40.gif");}
</style>
</head>
```

## 4.3 内联样式
**由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势**。**请慎用这种方法，例如当样式仅需要在一个元素上应用一次时**。

**要使用内联样式，你需要在相关的标签内使用样式（style）属性**。Style 属性可以包含任何 CSS 属性。本例展示如何改变段落的颜色和左外边距：
```css
<p style="color:sienna;margin-left:20px">这是一个段落。</p>
```

## 4.4 多重样式

**如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来**。 

例如，外部样式表拥有针对 h3 选择器的三个属性：
```css
h3
{
    color:red;
    text-align:left;
    font-size:8pt;
}
```

而内部样式表拥有针对 h3 选择器的两个属性：
```css
h3
{
    text-align:right;
    font-size:20pt;
}
```

**假如拥有内部样式表的这个页面同时与外部样式表链接，那么 h3 得到的样式是**：
```css
color:red;
text-align:right;
font-size:20pt;
```

**即颜色属性将被继承于外部样式表，而文字排列（text-alignment）和字体尺寸（font-size）会被内部样式表中的规则取代**。
```css
<head>
    <!-- 外部样式 style.css -->
    <link rel="stylesheet" type="text/css" href="style.css"/>
    <!-- 设置：h3{color:blue;} -->
    <style type="text/css">
      /* 内部样式 */
      h3{color:green;}
    </style>
</head>
<body>
    <h3>显示绿色，是内部样式</h3>
</body>
```

# 5.CSS 背景

CSS 背景属性用于定义HTML元素的背景。

CSS 属性定义背景效果:
```
background-color
background-image
background-repeat
background-attachment
background-position
```

## 5.1 背景颜色
background-color 属性定义了元素的背景颜色.

页面的背景颜色使用在body的选择器中:
```css
    <style>
        body{
           background-color:#b0c4de; /*设置网页背景颜色*/
        }
    </style>
```

CSS中，颜色值通常以以下方式定义:
  ```
  十六进制 - 如："#ff0000"
  RGB - 如："rgb(255,0,0)"
  颜色名称 - 如："red"
```

  以下实例中, h1, p, 和 div 元素拥有不同的背景颜色:
```css
 <body>
    <style>
        body{
           background-color:#b0c4de; /*设置网页背景颜色*/
        }
        h1{background-color:#6495ed}
        p{background-color: #e0ffff}
        div{background-color: #b0c3de}
    </style>
  </head>
  <body>
  <h1>背景颜色设置</h1>
  <p>段落背景颜色设置</p>
  <div>模块背景颜色设置</div>
  </body>
```

## 5.2 背景图像
background-image 属性描述了元素的背景图像.

**默认情况下，背景图像进行平铺重复显示，以覆盖整个元素实体**.

页面背景图片设置实例:

实例
```css
body {background-image:url('paper.gif');
	background-image:url("background-image:url('../../xx.jpg');") ;  /*路径写法，从当前文件夹开始写，向上或者向下开始找图*/
}

```

## 5.3 背景图像 - 水平或垂直平铺

默认情况下 background-image 属性会在页面的水平或者垂直方向平铺。

一些图像如果在水平方向与垂直方向平铺，这样看起来很不协调，如下所示: 
如果图像只在水平方向平铺 (repeat-x), 页面背景会更好些:

实例
```css
body
{
background-image:url('gradient2.png');
background-repeat:repeat-x;
}
```
## 5.4 背景图像- 设置定位与不平铺
Remark 让背景图像不影响文本的排版

如果你不想让图像平铺，你可以使用 background-repeat 属性:
```css
body
{
background-image:url('img_tree.png');
background-repeat:no-repeat;
}
```
以上实例中，背景图像与文本显示在同一个位置，为了让页面排版更加合理，不影响文本的阅读，我们可以改变图像的位置。

可以利用 background-position 属性改变图像在背景中的位置:
```css
body
{
background-image:url('img_tree.png');
background-repeat:no-repeat;
background-position:right top;
}
```

## 5.5 背景- 简写属性

在以上实例中我们可以看到页面的背景颜色通过了很多的属性来控制。

为了简化这些属性的代码，我们可以将这些属性合并在同一个属性中.

背景颜色的简写属性为 "background":
案例
```css
body {background:#ffffff url('img_tree.png') no-repeat right top;}
当使用简写属性时，属性值的顺序为：:
background-color
background-image
background-repeat
background-attachment
background-position
```
以上属性无需全部使用，你可以按照页面的实际需要使用.

## 5.6 CSS 背景属性

Property	|  描述
-|-
background	|简写属性，作用是将置在背景属性设一个声明中。
background-attachment|	背景图像是否固定或者随着页面的其余部分滚动。
background-color	|设置元素的背景颜色。
background-image|	把图像设置为背景。
background-position|	设置背景图像的起始位置。
background-repeat|	设置背景图像是否及如何重复。

# 6 文本颜色
**颜色属性被用来设置文字的颜色。**

颜色是通过CSS最经常的指定：

十六进制值 - 如: ＃FF0000
一个RGB值 - 如: RGB(255,0,0)
颜色的名称 - 如: red
参阅 CSS 颜色值 查看完整的颜色值。

一个网页的背景颜色是指在主体内的选择：
```css
<head>
    <meta charset="UTF-8">
    <title>文本篇</title>
    <style>
        body{color:red} /*设置文本默认颜色*/
        h1{color: #b0c3de}/*定义文本第一标题颜色*/
        h2{color: blue}
        p.ex{color:black}/*定义文本段落颜色，可以调用*/
    </style>
</head>

<body>

<p class="ex">在头部定义特定段落为黑色，class调用</p>
<p>这是一个普通的段落。请注意,本文是红色的。页面中定义默认的文本颜色选择器。</p>
<h1>标题1渲染上颜色</h1>
<h2>标题2渲染为蓝色</h2>

</body>
```

## 6.1 文本的对齐方式
**文本排列属性是用来设置文本的水平对齐方式。**

**文本可居中或对齐到左或右,两端对齐.**

**当text-align设置为"justify"，每一行被展开为宽度相等，左，右外边距是对齐（如杂志和报纸）。**
```css
h1 {text-align:center;}
p.date {text-align:right;}
p.main {text-align:justify;}
```

## 6.2 文本修饰

**text-decoration 属性用来设置或删除文本的装饰。**

从设计的角度看 **text-decoration**属性主要是用来删除链接的下划线：

a {text-decoration:none;}
也可以这样装饰文字：

实例
```css
 /*text-decoration 属性用来设置或删除文本的装饰。*/
        p.main{text-decoration: overline}/*添加上划线*/
        h1{text-decoration: line-through}/*添加中划线*/
        h2{text-decoration: underline}/*添加下划线*？
```

## 6.3 文本转换
**文本转换属性是用来指定在一个文本中的大写和小写字母。**

可用于所有字句变成大写或小写字母，或每个单词的首字母大写。
```
p.uppercase {text-transform:uppercase;} 将文本全变成大写
p.lowercase {text-transform:lowercase;}  将文本全变成小写
p.capitalize {text-transform:capitalize;}  将文本每个字首字母变成大写
```

## 6.4 文本缩进

文本缩进属性是用来指定文本的第一行的缩进

p.px{text-indent: 50px}

## 7 CSS 字体

CSS字体属性定义字体，加粗，大小，文字样式。

serif和sans-serif字体之间的区别
Serif vs. Sans-serif
Remark 在计算机屏幕上，sans-serif字体被认为是比serif字体容易阅读

## 7.1 CSS字型
在CSS中，有两种类型的字体系列名称：

通用字体系列 - 拥有相似外观的字体系统组合（如 "Serif" 或 "Monospace"）
特定字体系列 - 一个特定的字体系列（如 "Times" 或 "Courier"）


Generic     family	字体系列	说明
Serif	      Times New Roman
Georgia	    Serif字体中字符在行的末端拥有额外的装饰
Sans-serif	  Arial
Verdana	"  Sans"是指无 - 这些字体在末端没有额外的装饰
Monospace	  Courier New
Lucida     Console	所有的等宽字符具有相同的宽度


## 7.2 字体系列
font-family 属性设置文本的字体系列。

font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。

**注意: 如果字体系列的名称超过一个字，它必须用引号，如Font Family："宋体"。**

多个字体系列是用一个逗号分隔指明：
```
 p.ex{font-family:"Times New Roman", Times, serif;}
```

## 7.3 字体样式
主要是用于指定斜体文字的字体样式属性。

这个属性有三个值：
```css
正常 - 正常显示文本
斜体 - 以斜体字显示的文字
倾斜的文字 - 文字向一边倾斜（和斜体非常类似，但不太支持）
  /*字体样式；正常 斜体 半倾斜*/
    p.normal {font-style:normal;} /*正常体*/
    p.italic {font-style:italic;} /*斜体*/
    p.oblique {font-style:oblique;} 
```

## 7.4 字体大小

**font-size 属性设置文本的大小。**

能否管理文字的大小，在网页设计中是非常重要的。但是，你不能通过调整字体大小使段落看上去像标题，或者使标题看上去像段落。

请务必使用正确的HTML标签，就\<h1> - \<h6>表示标题和\<p>表示段落：

字体大小的值可以是绝对或相对的大小。

**绝对大小：**
```
设置一个指定大小的文本
不允许用户在所有浏览器中改变文本大小
```

## 7.5 设置字体大小像素

设置文字的大小与像素，让您完全控制文字大小：

实例
```css
h1 {font-size:40px;}
h2 {font-size:30px;}
p {font-size:14px;}
```

## 7.6 用em来设置字体大小
为了避免Internet Explorer 中无法调整文本的问题，许多开发者使用 em 单位代替像素。

em的尺寸单位由W3C建议。

**1em和当前字体大小相等。在浏览器中默认的文字大小是16px。**

**因此，1em的默认大小是16px。可以通过下面这个公式将像素转换为em：px/16=em**

实例
```css
h1 {font-size:2.5em;} /* 40px/16=2.5em */
h2 {font-size:1.875em;} /* 30px/16=1.875em */
p {font-size:0.875em;} /* 14px/16=0.875em */
```

在上面的例子，em的文字大小是与前面的例子中像素一样。不过，**如果使用 em 单位，则可以在所有浏览器中调整文本大小。**

不幸的是，仍然是IE浏览器的问题。调整文本的大小时，会比正常的尺寸更大或更小。
上面的例子可以在 Internet Explorer 9, Firefox, Chrome, Opera, 和 Safari 中通过缩放浏览器调整文本大小。

虽然可以通过浏览器的缩放工具调整文本大小，但是，这种调整是整个页面，而不仅仅是文本
确定了输出的物理尺寸时绝对大小很有用

相对大小：
```
相对于周围的元素来设置大小
允许用户在浏览器中改变文字大小
Remark 如果你不指定一个字体的大小，默认大小和普通文本段落一样，是16像素（16px=1em）。
```
## 7.7 使用百分比和EM组合
在所有浏览器的解决方案中，设置 \<body>元素的默认字体大小的是百分比：

实例
```css
body {font-size:100%;}
h1 {font-size:2.5em;}
h2 {font-size:1.875em;}
p {font-size:0.875em;}
```

# 8 CSS 链接
不同的链接可以有不同的样式。

**链接样式**
链接的样式，可以用任何CSS属性（如颜色，字体，背景等）。

特别的链接，可以有不同的样式，这取决于他们是什么状态。

这四个链接状态是：

```css
a:link - 正常，未访问过的链接
a:visited - 用户已访问过的链接
a:hover - 当用户鼠标放在链接上时
a:active - 链接被点击的那一刻

a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
```

当设置为若干链路状态的样式，也有一些顺序规则：

a:hover 必须跟在 a:link 和 a:visited后面
a:active 必须跟在 a:hover后面

# 9 CSS 列表

CSS 列表属性作用如下：

设置不同的列表项标记为有序列表
设置不同的列表项标记为无序列表
设置列表项标记为图像

## 9.1表

在 HTML中，有两种类型的列表：
```
无序列表 ul - 列表项标记用特殊图形（如小黑点、小方框等）
有序列表 ol - 列表项的标记有数字或字母
使用 CSS，可以列出进一步的样式，并可用图像作列表项标记。
```

无序列表如下所示:
```
Coffee
Tea
Coca Cola
Coffee
Tea
Coca Cola
```

有序列表如下所示:
```
Coffee
Tea
Coca Cola
Coffee
Tea
Coca Cola
```

## 9.3 不同的列表项标记

list-style-type属性指定列表项标记的类型是 ：无序列表，以及有些是有序列表。
```css
<head>
    <meta charset="UTF-8">
    <title>列表篇</title>
    <style>
        /*不同的列表项标记*/
        /*list-style-type属性指定列表项标记的类型是*/
        ul.a{list-style-type: circle}  /*无序列表*/
        ol.b{list-style-type: upper-alpha}  /*有序列表*/
    </style>
</head>
<body>
<ul class="a">
    <li>coffee</li>
    <li>tea</li>
    <li>coco</li>
</ul>
<ol class="b">
     <li>coffee</li>
    <li>tea</li>
    <li>coco</li>
</ol>
</body>
```

## 9.4 作为列表项标记的图像
**要指定列表项标记的图像，使用列表样式图像属性：**


实例
```css
ul
{
    list-style-image: url('sqpurple.gif');
}
```

## 9.5 列表 - 简写属性
**在单个属性中可以指定所有的列表属性。这就是所谓的简写属性。**

为列表使用简写属性，列表样式属性设置如下：

实例
```
ul
{
    list-style: square url("sqpurple.gif");
可以按顺序设置如下属性：
list-style-type
list-style-position (有关说明，请参见下面的CSS属性表)
list-style-image
```
如果上述值丢失一个，其余仍在指定的顺序，就没关系。

## 9.6 移除默认设置

list-style-type:none 属性可以用于移除小标记。**默认情况下列表 <ul> 或 <ol> 还设置了内边距和外边距，可使用 margin:0 和 padding:0 来移除:**

实例
```
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
```

## 9.7 所有的CSS列表属性

属性	|描述
-|-
list-style	|	简写属性。用于把所有用于列表的属性设置于一个声明中
list-style-image|	将图像设置为列表项标志。
list-style-position|	设置列表中列表项标志的位置。
list-style-type	|	设置列表项标志的类型。

# 10 CSS 表格
使用 CSS 可以使 HTML 表格更美观。（https://www.runoob.com/css/css-table.html）

Company|	Contact	|Country
-|-|-
Alfreds Futterkiste|	Maria Anders	|Germany
Berglunds snabbköp	|Christina Berglund|	Sweden
Centro comercial Moctezuma	|Francisco Chang	|Mexico
Ernst Handel	|Roland Mendel	|Austria
Island Trading	|Helen Bennett	|UK
Königlich Essen	|Philip Cramer	|Germany
Laughing Bacchus Winecellars	|Yoshi Tannamuri|	Canada
Magazzini Alimentari Riuniti|	Giovanni Rovelli|	Italy
North/South|	Simon Crowther|	UK
Paris spécialités|	Marie Bertrand|	France
The Big Cheese|	Liz Nixon|	USA
Vaffeljernet|	Palle Ibsen|	Denmark

## 10.1 表格边框
**指定CSS表格边框，使用border属性。**

下面的例子指定了一个表格的Th和TD元素的黑色边框：
```css
 table,th,td/*双边框*/
        {       /*指定CSS表格边框，使用border属性，表格的Th和TD元素的黑色边框*/
            border:1px solid black;
        }
```
**请注意，在上面的例子中的表格有双边框。这是因为表和th/ td元素有独立的边界。**

**为了显示一个表的单个边框，使用 border-collapse属性。**

## 10.2 折叠边框
border-collapse 属性设置表格的边框是否被折叠成一个单一的边框或隔开：

实例
```css
/*border-collapse 属性设置表格的边框是否被折叠成一个单一的边框或隔开：*/
          table{  /*添加下面这段变成单边框*/
            border-collapse: collapse;
```

## 10.3 表格宽度和高度
**Width和height属性定义表格的宽度和高度。**

下面的例子是设置100％的宽度，50像素的th元素的高度的表格：
```css
table 
{
    width:100%;
}
th
{
    height:50px;
}
```

## 10.3 表格文字对齐
表格中的文本对齐和垂直对齐属性。

**text-align属性设置水平对齐方式，向左，右，或中心：**
实例
```css
td
{
    text-align:right;
}
```

**垂直对齐属性设置垂直对齐，比如顶部，底部或中间：**
实例
```css
td
{
    height:50px;
    vertical-align:bottom;
}
```

## 10.4 表格填充
**如需控制边框和表格内容之间的间距，应使用td和th元素的填充属性：**

实例
```css
td
{
    padding:15px;
}
```

## 10.5 表格颜色
下面的例子指定边框的颜色，和th元素的文本和背景颜色：

实例
```css
table, td, th
{
    border:1px solid green;
}
th
{
    background-color:green;
    color:white;
}
```

# 11 CSS 盒子模型

CSS 盒子模型(Box Model)

**所有HTML元素可以看作盒子，在CSS中，"box model"这一术语是用来设计和布局时使用。**

**CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。**

**盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。**

下面的图片说明了盒子模型(Box Model)：

![Alt](img/box-model.gif)

不同部分的说明：
```
Margin(外边距) - 清除边框外的区域，外边距是透明的。
Border(边框) - 围绕在内边距和内容外的边框。
Padding(内边距) - 清除内容周围的区域，内边距是透明的。
Content(内容) - 盒子的内容，显示文本和图像。
为了正确设置元素在所有浏览器中的宽度和高度，你需要知道的盒模型是如何工作的。
```

## 11.1 元素的宽度和高度
**Remark重要: 当您指定一个 CSS 元素的宽度和高度属性时，你只是设置内容区域的宽度和高度。要知道，完整大小的元素，你还必须添加内边距，边框和外边距。**

下面的例子中的元素的总宽度为 450px
```
div {
    width: 300px;
    border: 25px solid green;
    padding: 25px;
    margin: 25px;
}

<body>
<p>CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。</p>
<div>这里是盒子内的实际内容。有 25px 内间距，25px 外间距、25px 绿色边框。</div>
</body>

```

让我们自己算算：
```
300px (宽)
+ 50px (左 + 右填充)
+ 50px (左 + 右边框)
+ 50px (左 + 右边距)
= 450px
```

试想一下，你只有 250 像素的空间。让我们设置总宽度为 250 像素的元素:
```css
div {
    width: 220px;
    padding: 10px;
    border: 5px solid gray;
    margin: 0; 
}
```
**最终元素的总宽度计算公式是这样的：**

**总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距**

**元素的总高度最终计算公式是这样的：**

**总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距**

# 12 CSS 边框
## 12.1 CSS 边框属性
**CSS边框属性允许你指定一个元素边框的样式和颜色。**
```
  在四边都有边框
  
  
  红色底部边框
  
  
  圆角边框
  
  
  左侧边框带宽度，颜色为蓝色
```

## 12.2 边框样式

**边框样式属性指定要显示什么样的边界**。

**Remark border-style属性用来定义边框的样式**

### 12.2.1 border-style 值:

none: 默认无边<br>

**dotted: 定义一个点线边框**<br>

**dashed: 定义一个虚线边框**<br>

**solid: 定义实线边框**<br>

**double: 定义两个边框**。 两个边框的宽度和 border-width 的值相同<br>

groove: 定义3D沟槽边框。效果取决于边框的颜色值<br>

ridge: 定义3D脊边框。效果取决于边框的颜色值<br>

inset:定义一个3D的嵌入边框。效果取决于边框的颜色值<br>

outset: 定义一个3D突出边框。 效果取决于边框的颜色值<br>

## 12.3 边框宽度

您可以通过 **border-width 属性为边框指定宽度**。

**为边框指定宽度有两种方法：可以指定长度值，比如 2px 或 0.1em(单位为 px, pt, cm, em 等)，或者使用 3 个关键字之一，它们分别是 thick 、medium（默认值） 和 thin。**

注意：CSS 没有定义 3 个关键字的具体宽度，所以一个用户可能把 thick 、medium 和 thin 分别设置为等于 5px、3px 和 2px，而另一个用户则分别设置为 3px、2px 和 1px。
```css
p.one
{
    border-style:solid;
    border-width:5px;
}
```

## 12.4 边框颜色
**border-color属性用于设置边框的颜色**。可以设置的颜色：

```
name - 指定颜色的名称，如 "red"
RGB - 指定 RGB 值, 如 "rgb(255,0,0)"
Hex - 指定16进制值, 如 "#ff0000"
您还可以设置边框的颜色为"transparent"。
```
p.one

## 12.5 边框-单独设置各边
在CSS中，可以指定不同的侧面不同的边框：
```css
p
{
    border-top-style:dotted;
    border-right-style:solid;
    border-bottom-style:dotted;
    border-left-style:solid;
}
border-style属性可以有1-4个值：
border-style:dotted solid double dashed;
  上边框是 dotted
  右边框是 solid
  底边框是 double
  左边框是 dashed

{
    border-style:solid;
    border-color:red;
}
```
**注意： border-color单独使用是不起作用的，必须得先使用border-style来设置边框样式。**

```
border-style:dotted solid double;
上边框是 dotted
左、右边框是 solid
底边框是 double

border-style:dotted solid;
上、底边框是 dotted
右、左边框是 solid

border-style:dotted;
四面边框是 dotted
```
上面的例子用了border-style。然而，它也可以和border-width 、 border-color一起使用。

## 12.6 边框-简写属性

上面的例子用了很多属性来设置边框。

你也可以在一个属性中设置边框。

你可以在"border"属性中设置：
```
border-width
border-style (required)
border-color
```

实例

border:5px solid red;

## 12.7 CSS 边框属性

属性	|	描述
-|-
border	|	简写属性，用于把针对四个边的属性设置在一个声明。
border-style|	用于设置元素所有边框的样式，或者单独地为各边设置边框样式。
border-width|	简写属性，用于为元素的所有边框设置宽度，或者单独地为各边边框设置宽度。
border-color|	简写属性，设置元素的所有边框中可见部分的颜色，或为 4 个边分别设置颜色。
border-bottom|	简写属性，用于把下边框的所有属性设置到一个声明中。
border-bottom-color|	设置元素的下边框的颜色。
border-bottom-style|	设置元素的下边框的样式。
border-bottom-width|	设置元素的下边框的宽度。
border-left	|	简写属性，用于把左边框的所有属性设置到一个声明中。
border-left-color|	设置元素的左边框的颜色。
border-left-style|	设置元素的左边框的样式。
border-left-width|	设置元素的左边框的宽度。
border-right	|	简写属性，用于把右边框的所有属性设置到一个声明中。
border-right-color|	设置元素的右边框的颜色。
border-right-style|	设置元素的右边框的样式。
border-right-width|	设置元素的右边框的宽度。
border-top	|	简写属性，用于把上边框的所有属性设置到一个声明中。
border-top-color|	设置元素的上边框的颜色。
border-top-style|	设置元素的上边框的样式。
border-top-width|	设置元素的上边框的宽度。
border-radius	|	设置圆角的边框。

# 13 CSS 轮廓（outline）
**轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。**

轮廓（outline）属性指定元素轮廓的样式、颜色和宽度。

# 14 CSS margin(外边距)
**CSS margin(外边距)属性定义元素周围的空间。**

margin

margin 清除周围的（外边框）元素区域。
margin 没有背景颜色，是完全透明的。
margin 可以单独改变元素的上，下，左，右边距，也可以一次改变所有的属性。

![alt](img/VlwVi.png)

可能的值

值	|说明
-|-
auto	|设置浏览器边距。这样做的结果会依赖于浏览器
length	|定义一个固定的margin（使用像素，pt，em等）
%	|定义一个使用百分比的边距

Remark Margin可以使用负值，重叠的内容。

# 13.1 Margin - 单边外边距属性
在CSS中，它可以指定不同的侧面不同的边距：

实例
margin-top:100px;
margin-bottom:100px;
margin-right:50px;
margin-left:50px;

13.2.Margin - 简写属性
为了缩短代码，有可能使用一个属性中margin指定的所有边距属性。这就是所谓的简写属性。

所有边距属性的简写属性是 margin :

实例
margin:100px 50px;
margin属性可以有一到四个值。

margin:25px 50px 75px 100px;
上边距为25px
右边距为50px
下边距为75px
左边距为100px

margin:25px 50px 75px;
上边距为25px
左右边距为50px
下边距为75px

margin:25px 50px;
上下边距为25px
左右边距为50px

margin:25px;
所有的4个边距都是25px

14.CSS padding（填充）
CSS padding（填充）是一个简写属性，定义元素边框与元素内容之间的空间，即上下左右的内边距。

padding（填充）
当元素的 padding（填充）内边距被清除时，所释放的区域将会受到元素背景颜色的填充。

单独使用 padding 属性可以改变上下左右的填充。

可能的值
值	说明
length	定义一个固定的填充(像素, pt, em,等)
%	使用百分比值定义一个填充

14.1.填充- 单边内边距属性
在CSS中，它可以指定不同的侧面不同的填充：

实例
padding-top:25px;
padding-bottom:25px;
padding-right:50px;
padding-left:50px;

14.2.填充 - 简写属性
为了缩短代码，它可以在一个属性中指定的所有填充属性。

这就是所谓的简写属性。所有的填充属性的简写属性是 padding :

实例
padding:25px 50px;



15.CSS 分组 和 嵌套 选择器
分组选择器
在样式表中有很多具有相同样式的元素。
分组选择器
在样式表中有很多具有相同样式的元素。

h1 {
    color:green;
}
h2 {

嵌套选择器
它可能适用于选择器内部的选择器的样式。

在下面的例子设置了四个样式：

p{ }: 为所有 p 元素指定一个样式。
.marked{ }: 为所有 class="marked" 的元素指定一个样式。
.marked p{ }: 为所有 class="marked" 元素内的 p 元素指定一个样式。
p.marked{ }: 为所有 class="marked" 的 p 元素指定一个样式。
    color:green;


}
p {
    color:green;
}
为了尽量减少代码，你可以使用分组选择器。

每个选择器用逗号分隔。

在下面的例子中，我们对以上代码使用分组选择器：
实例
h1,h2,p
{
    color:green;
}

嵌套选择器
它可能适用于选择器内部的选择器的样式。

在下面的例子设置了四个样式：

p{ }: 为所有 p 元素指定一个样式。
.marked{ }: 为所有 class="marked" 的元素指定一个样式。
.marked p{ }: 为所有 class="marked" 元素内的 p 元素指定一个样式。
p.marked{ }: 为所有 class="marked" 的 p 元素指定一个样式。

p
{
    color:blue;
    text-align:center;
}
.marked
{
    background-color:red;
}
.marked p
{
    color:white;
}
p.marked{
    text-decoration:underline;
}

16.所有CSS 尺寸 (Dimension)属性
属性	描述
height	设置元素的高度。
line-height	设置行高。
max-height	设置元素的最大高度。
max-width	设置元素的最大宽度。
min-height	设置元素的最小高度。
min-width	设置元素的最小宽度。
width	设置元素的宽度。

17.CSS Display(显示) 与 Visibility（可见性）
display属性设置一个元素应如何显示，visibility属性指定一个元素应可见还是隐藏。

17.1隐藏元素 - display:none或visibility:hidden
隐藏一个元素可以通过把display属性设置为"none"，或把visibility属性设置为"hidden"。但是请注意，这两种方法会产生不同的结果。

visibility:hidden可以隐藏某个元素，但隐藏的元素仍需占用与未隐藏之前一样的空间。也就是说，该元素虽然被隐藏了，但仍然会影响布局。
h1.hidden{visibility:hidden;}

display:none可以隐藏某个元素，且隐藏的元素不会占用任何空间。也就是说，该元素不但被隐藏了，而且该元素原本占用的空间也会从页面布局中消失。

实例
h1.hidden {display:none;}

17.1CSS Display - 块和内联元素
块元素是一个元素，占用了全部宽度，在前后都是换行符。

块元素的例子：

<h1>
<p>
<div>
内联元素只需要必要的宽度，不强制换行。

内联元素的例子：

<span>
<a>

17.2如何改变一个元素显示
可以更改内联元素和块元素，反之亦然，可以使页面看起来是以一种特定的方式组合，并仍然遵循web标准。

下面的示例把列表项显示为内联元素：

实例
li {display:inline;}

下面的示例把span元素作为块元素：

实例
span {display:block;}

注意：变更元素的显示类型看该元素是如何显示，它是什么样的元素。例如：一个内联元素设置为display:block是不允许有它内部的嵌套块元素。

18.position 属性指定了元素的定位类型。

position 属性的五个值：

static
relative
fixed
absolute
sticky
元素可以使用的顶部，底部，左侧和右侧属性定位。然而，这些属性无法工作，除非是先设定position属性。他们也有不同的工作方式，这取决于定位方法。

18.2static 定位
HTML 元素的默认值，即没有定位，遵循正常的文档流对象。

静态定位的元素不会受到 top, bottom, left, right影响。
div.static {
    position: static;
    border: 3px solid #73AD21;
}

18.3fixed 定位
元素的位置相对于浏览器窗口是固定位置。

即使窗口是滚动的它也不会移动：
p.pos_fixed
{
    position:fixed;
    top:30px;
    right:5px;
}
注意： Fixed 定位在 IE7 和 IE8 下需要描述 !DOCTYPE 才能支持。

Fixed定位使元素的位置与文档流无关，因此不占据空间。

Fixed定位的元素和其他元素重叠。

18.4relative 定位
相对定位元素的定位是相对其正常位置。
h2.pos_left
{
    position:relative;
    left:-20px;
}
h2.pos_right
{
    position:relative;
    left:20px;
}
移动相对定位元素，但它原本所占的空间不会改变。
相对定位元素经常被用来作为绝对定位元素的容器块。

18.5absolute 定位
绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于<html>:
h2
{
    position:absolute;
    left:100px;
    top:150px;
}
absolute 定位使元素的位置与文档流无关，因此不占据空间。

absolute 定位的元素和其他元素重叠。

18.6sticky 定位
sticky 英文字面意思是粘，粘贴，所以可以把它称之为粘性定位。

position: sticky; 基于用户的滚动位置来定位。

粘性定位的元素是依赖于用户的滚动，在 position:relative 与 position:fixed 定位之间切换。

它的行为就像 position:relative; 而当页面滚动超出目标区域时，它的表现就像 position:fixed;，它会固定在目标位置。

元素定位表现为在跨越特定阈值前为相对定位，之后为固定定位。

这个特定阈值指的是 top, right, bottom 或 left 之一，换言之，指定 top, right, bottom 或 left 四个阈值其中之一，才可使粘性定位生效。否则其行为与相对定位相同。

注意: Internet Explorer, Edge 15 及更早 IE 版本不支持 sticky 定位。 Safari 需要使用 -webkit- prefix (查看以下实例)。
div.sticky {
    position: -webkit-sticky; /* Safari */
    position: sticky;
    top: 0;
    background-color: green;
    border: 2px solid #4CAF50;
}

18.8重叠的元素
元素的定位与文档流无关，所以它们可以覆盖页面上的其它元素

z-index属性指定了一个元素的堆叠顺序（哪个元素应该放在前面，或后面）

一个元素可以有正数或负数的堆叠顺序：
img
{
    position:absolute;
    left:0px;
    top:0px;
    z-index:-1;
}
具有更高堆叠顺序的元素总是在较低的堆叠顺序元素的前面。

注意： 如果两个定位元素重叠，没有指定z - index，最后定位在HTML代码中的元素将被显示在最前面。

18.9所有的CSS定位属性
"CSS" 列中的数字表示哪个CSS(CSS1 或者CSS2)版本定义了该属性。

属性	说明	值	CSS
bottom	定义了定位元素下外边距边界与其包含块下边界之间的偏移。	auto
length
%
inherit	2
clip	剪辑一个绝对定位的元素	shape
auto
inherit	2
cursor	显示光标移动到指定的类型	url
auto
crosshair
default
pointer
move
e-resize
ne-resize
nw-resize
n-resize
se-resize
sw-resize
s-resize
w-resize
text
wait
help	2
left	定义了定位元素左外边距边界与其包含块左边界之间的偏移。	auto
length
%
inherit	2
overflow
设置当元素的内容溢出其区域时发生的事情。	auto
hidden
scroll
visible
inherit	2
overflow-y
指定如何处理顶部/底部边缘的内容溢出元素的内容区域	auto
hidden
scroll
visible
no-display
no-content	2
overflow-x
指定如何处理右边/左边边缘的内容溢出元素的内容区域	auto
hidden
scroll
visible
no-display
no-content	2
position	指定元素的定位类型	absolute
fixed
relative
static
inherit	2
right	定义了定位元素右外边距边界与其包含块右边界之间的偏移。	auto
length
%
inherit	2
top	定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。	auto
length
%
inherit	2
z-index	设置元素的堆叠顺序	number
auto
inherit	2

19.CSS Overflow
CSS overflow 属性可以控制内容溢出元素框时在对应的元素区间内添加滚动条。

overflow属性有以下值：

19.1CSS Overflow
CSS overflow 属性可以控制内容溢出元素框时在对应的元素区间内添加滚动条。

overflow属性有以下值：

值	描述
visible	默认值。内容不会被修剪，会呈现在元素框之外。
hidden	内容会被修剪，并且其余内容是不可见的。
scroll	内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。
auto	如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。
inherit	规定应该从父元素继承 overflow 属性的值。
注意:overflow 属性只工作于指定高度的块元素上。

注意: 在 OS X Lion ( Mac 系统) 系统上，滚动条默认是隐藏的，使用的时候才会显示 (设置 "overflow:scroll" 也是一样的)。


19.2overflow: visible
默认情况下，overflow 的值为 visible， 意思是内容溢出元素框：

这里的文本内容会溢出元素框。

这里的文本内容会溢出元素框。

这里的文本内容会溢出元素框。

这里的文本内容会溢出元素框。
案例：
<head>
    <meta charset="UTF-8">
    <title>CSS 布局 - Overflow</title>
    <style>
        div{
            width:200px;
            height:50px;
            background-color: #00FF00;
            overflow:visible;
        }
    </style>
</head>
<body>
<div>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
    <p>这里的文本内容会溢出元素框。</p><br>
</div>
</body>

20.什么是 CSS Float（浮动）？

CSS 的 Float（浮动），会使元素向左或向右移动，其周围的元素也会重新排列。
Float（浮动），往往是用于图像，但它在布局时一样非常有用。

20.1元素怎样浮动
元素的水平方向浮动，意味着元素只能左右移动而不能上下移动。

一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。

浮动元素之后的元素将围绕它。

浮动元素之前的元素将不会受到影响。

如果图像是右浮动，下面的文本流将环绕在它左边：
 img{
        float:right;
    }

20.2彼此相邻的浮动元素
如果你把几个浮动的元素放到一起，如果有空间的话，它们将彼此相邻。

在这里，我们对图片廊使用 float 属性：

实例
.thumbnail 
{
    float:left;
    width:110px;
    height:90px;
    margin:5px;
}

20.3清除浮动 - 使用 clear
元素浮动之后，周围的元素会重新排列，为了避免这种情况，使用 clear 属性。

clear 属性指定元素两侧不能出现浮动元素。

使用 clear 属性往文本中添加图片廊：
.text_line
{
    clear:both;
}

20.4CSS 中所有的浮动属性
"CSS" 列中的数字表示不同的 CSS 版本（CSS1 或 CSS2）定义了该属性。

属性	描述	值	CSS
clear	指定不允许元素周围有浮动元素。	left
right
both
none
inherit	1
float	指定一个盒子（元素）是否可以浮动。	left
right
none
inherit

21.CSS 布局 - 水平 & 垂直对齐
元素居中对齐
要水平居中对齐一个元素(如 <div>), 可以使用 margin: auto;。
设置到元素的宽度将防止它溢出到容器的边缘。
元素通过指定宽度，并将两边的空外边距平均分配：
.center {
    margin: auto;
    width: 50%;
    border: 3px solid green;
    padding: 10px;
}
注意: 如果没有设置 width 属性(或者设置 100%)，居中对齐将不起作用。

21.1文本居中对齐
如果仅仅是为了文本在元素内居中对齐，可以使用 text-align: center;

文本居中对齐


实例
.center {
    text-align: center;
    border: 3px solid green;
}
21.2图片居中对齐
要让图片居中对齐, 可以使用 margin: auto; 并将它放到 块 元素中:

实例
img {
    display: block;
    margin: auto;
    width: 40%;
}

21.3左右对齐 - 使用定位方式
我们可以使用 position: absolute; 属性来对齐元素:
.right {
    position: absolute;
    right: 0px;
    width: 300px;
    border: 3px solid #73AD21;
    padding: 10px;
}
注释：绝对定位元素会被从正常流中删除，并且能够交叠元素。

提示: 当使用 position 来对齐元素时, 通常 <body> 元素会设置 margin 和 padding 。 这样可以避免在不同的浏览器中出现可见的差异。

当使用 position 属性时，IE8 以及更早的版本存在一个问题。如果容器元素（在我们的案例中是 <div class="container">）设置了指定的宽度，并且省略了 !DOCTYPE 声明，那么 IE8 以及更早的版本会在右侧增加 17px 的外边距。这似乎是为滚动条预留的空间。当使用 position 属性时，请始终设置 !DOCTYPE 声明：
body {
    margin: 0;
    padding: 0;
}
 
.container {
    position: relative;
    width: 100%;
}
 
.right {
    position: absolute;
    right: 0px;
    width: 300px;
    background-color: #b0e0e6;
}

21.4左右对齐 - 使用 float 方式
我们也可以使用 float 属性来对齐元素:
.right {
    float: right;
    width: 300px;
    border: 3px solid #73AD21;
    padding: 10px;
}
当像这样对齐元素时，对 <body> 元素的外边距和内边距进行预定义是一个好主意。这样可以避免在不同的浏览器中出现可见的差异。

注意：如果子元素的高度大于父元素，且子元素设置了浮动，那么子元素将溢出，这时候你可以使用 "clearfix(清除浮动)" 来解决该问题。

我们可以在父元素上添加 overflow: auto; 来解决子元素溢出的问题:

21.5垂直居中对齐 - 使用 padding
CSS 中有很多方式可以实现垂直居中对齐。 一个简单的方式就是头部顶部使用 padding:
.center {
    padding: 70px 0;
    border: 3px solid green;
}

如果要水平和垂直都居中，可以使用 padding 和 text-align: center:
.center {
    padding: 70px 0;
    border: 3px solid green;
    text-align: center;
}

21.6垂直居中 - 使用 line-height
.center {
    line-height: 200px;
    height: 200px;
    border: 3px solid green;
    text-align: center;
}
 
/* 如果文本有多行，添加以下代码: */
.center p {
    line-height: 1.5;
    display: inline-block;
    vertical-align: middle;
}

21.7垂直居中 - 使用 position 和 transform
除了使用 padding 和 line-height 属性外,我们还可以使用 transform 属性来设置垂直居中:



22.CSS 组合选择符
CSS 组合选择符
	组合选择符说明了两个选择器之间的关系。
CSS组合选择符包括各种简单选择符的组合方式。
在 CSS3 中包含了四种组合方式:
  后代选择器(以空格     分隔)
  子元素选择器(以大于 > 号分隔）
  相邻兄弟选择器（以加号 + 分隔）
  普通兄弟选择器（以波浪号 ～ 分隔）

后代选择器
后代选择器用于选取某元素的后代元素。

以下实例选取所有 <p> 元素插入到 <div> 元素中: 

实例
div p
{
  background-color:yellow;
}

22.1子元素选择器
与后代选择器相比，子元素选择器（Child selectors）只能选择作为某元素直接/一级子元素的元素。

以下实例选择了<div>元素中所有直接子元素 <p> ：

实例
div>p
{
  background-color:yellow;
}


22.2相邻兄弟选择器
相邻兄弟选择器（Adjacent sibling selector）可选择紧接在另一元素后的元素，且二者有相同父元素。

如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。

以下实例选取了所有位于 <div> 元素后的第一个 <p> 元素:

22.3后续兄弟选择器
后续兄弟选择器选取所有指定元素之后的相邻兄弟元素。

以下实例选取了所有 <div> 元素之后的所有相邻兄弟元素 <p> : 

实例
div~p
{
  background-color:yellow;
}

23.CSS 伪类(Pseudo-classes)
CSS伪类是用来添加一些选择器的特殊效果。

23.1
语法
伪类的语法：
selector:pseudo-class {property:value;}
CSS类也可以使用伪类：
selector.class:pseudo-class {property:value;}
anchor伪类
在支持 CSS 的浏览器中，链接的不同状态都可以以不同的方式显示

实例
a:link {color:#FF0000;} /* 未访问的链接 */
a:visited {color:#00FF00;} /* 已访问的链接 */
a:hover {color:#FF00FF;} /* 鼠标划过链接 */
a:active {color:#0000FF;} /* 已选中的链接 */

注意： 在CSS定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
注意： 在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
注意：伪类的名称不区分大小写。

23.2伪类和CSS类
伪类可以与 CSS 类配合使用：
a.red:visited {color:#FF0000;}
<a class="red" href="css-syntax.html">CSS 语法</a>
如果在上面的例子的链接已被访问，它会显示为红色

23.3CSS :first-child 伪类
您可以使用 :first-child 伪类来选择父元素的第一个子元素。

注意：在IE8的之前版本必须声明<!DOCTYPE> ，这样 :first-child 才能生效。

23.4匹配第一个 <p> 元素
在下面的例子中，选择器匹配作为任何元素的第一个子元素的 <p> 元素：

实例
p:first-child
{
    color:blue;
}
23.5匹配所有<p> 元素中的第一个 <i> 元素
在下面的例子中，选择相匹配的所有<p>元素的第一个 <i> 元素：

实例
p > i:first-child
{
    color:blue;
}

23.6匹配所有作为第一个子元素的 <p> 元素中的所有 <i> 元素
在下面的例子中，选择器匹配所有作为元素的第一个子元素的 <p> 元素中的所有 <i> 元素：

实例
p:first-child i
{
    color:blue;
}
23.7CSS - :lang 伪类
:lang 伪类使你有能力为不同的语言定义特殊的规则

注意：IE8必须声明<!DOCTYPE>才能支持;lang伪类。

在下面的例子中，:lang 类为属性值为 no 的q元素定义引号的类型：

实例
q:lang(no) {quotes: "~" "~";}

24.CSS 伪元素
CSS 伪元素是用来添加一些选择器的特殊效果。

语法
伪元素的语法：
selector:pseudo-element {property:value;}
CSS类也可以使用伪元素：
selector.class:pseudo-element {property:value;}

24.1.:first-line 伪元素
"first-line" 伪元素用于向文本的首行设置特殊样式。

在下面的例子中，浏览器会根据 "first-line" 伪元素中的样式对 p 元素的第一行文本进行格式化：
p:first-line 
{
    color:#ff0000;
    font-variant:small-caps;
}
注意："first-line" 伪元素只能用于块级元素。

注意： 下面的属性可应用于 "first-line" 伪元素：
font properties
color properties 
background properties
word-spacing
letter-spacing
text-decoration
vertical-align
text-transform
line-height
clear

24.2.:first-letter 伪元素
"first-letter" 伪元素用于向文本的首字母设置特殊样式：

p:first-letter 
{
    color:#ff0000;
    font-size:xx-large;
}
注意： "first-letter" 伪元素只能用于块级元素。

注意： 下面的属性可应用于 "first-letter" 伪元素： 

font properties
color properties 
background properties
margin properties
padding properties
border properties
text-decoration
vertical-align (only if "float" is "none")
text-transform
line-height
float
clear

24.3.伪元素和CSS类
伪元素可以结合CSS类： 
p.article:first-letter {color:#ff0000;}
<p class="article">文章段落</p>
上面的例子会使所有 class 为 article 的段落的首字母变为红色。

24.4多个伪元素
可以结合多个伪元素来使用。

在下面的例子中，段落的第一个字母将显示为红色，其字体大小为 xx-large。第一行中的其余文本将为蓝色，并以小型大写字母显示。

段落中的其余文本将以默认字体大小和颜色来显示：
p:first-letter
{
    color:#ff0000;
    font-size:xx-large;
}
p:first-line 
{
    color:#0000ff;
    font-variant:small-caps;
}

24.5.CSS - :before 伪元素
":before" 伪元素可以在元素的内容前面插入新内容。

下面的例子在每个 <h1>元素前面插入一幅图片：
h1:before 
{
    content:url(smiley.gif);
}

24.6.所有CSS伪类/元素
选择器	示例	示例说明
:link	a:link	选择所有未访问链接
:visited	a:visited	选择所有访问过的链接
:active	a:active	选择正在活动链接
:hover	a:hover	把鼠标放在链接上的状态
:focus	input:focus	选择元素输入后具有焦点
:first-letter	p:first-letter	选择每个<p> 元素的第一个字母
:first-line	p:first-line	选择每个<p> 元素的第一行
:first-child	p:first-child	选择器匹配属于任意元素的第一个子元素的 <p> 元素
:before	p:before	在每个<p>元素之前插入内容
:after	p:after	在每个<p>元素之后插入内容
:lang(language)	p:lang(it)	为<p>元素的lang属性选择一个开始值

25.CSS 导航栏
导航栏
熟练使用导航栏，对于任何网站都非常重要。
使用CSS你可以转换成好看的导航栏而不是枯燥的HTML菜单。

25.1导航栏=链接列表
作为标准的 HTML 基础一个导航栏是必须的。

在我们的例子中我们将建立一个标准的 HTML 列表导航栏。

导航条基本上是一个链接列表，所以使用 <ul> 和 <li>元素非常有意义：
<ul>
  <li><a href="#home">主页</a></li>
  <li><a href="#news">新闻</a></li>
  <li><a href="#contact">联系</a></li>
  <li><a href="#about">关于</a></li>
</ul>

现在，让我们从列表中删除边距和填充：
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
}
例子解析：

list-style-type:none - 移除列表前小标志。一个导航栏并不需要列表标记
移除浏览器的默认设置将边距和填充设置为0
上面的例子中的代码是垂直和水平导航栏使用的标准代码。

25.2垂直导航栏
上面的代码，我们只需要 <a>元素的样式，建立一个垂直的导航栏：
a
{
    display:block;
    width:60px;
}
display:block - 显示块元素的链接，让整体变为可点击链接区域（不只是文本），它允许我们指定宽度
width:60px - 块元素默认情况下是最大宽度。我们要指定一个60像素的宽度
注意： 请务必指定 <a>元素在垂直导航栏的的宽度。如果省略宽度，IE6可能产生意想不到的效果。

25.3垂直导航条实例
创建一个简单的垂直导航条实例，在鼠标移动到选项时，修改背景颜色：
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    width: 200px;
    background-color: #f1f1f1;
}
 
li a {
    display: block;
    color: #000;
    padding: 8px 16px;
    text-decoration: none;
}
 
/* 鼠标移动到选项上修改背景颜色 */
li a:hover {
    background-color: #555;
    color: white;
}

25.4激活/当前导航条实例
在点击了选项后，我们可以添加 "active" 类来标注哪个选项被选中：
li a.active {
    background-color: #4CAF50;
    color: white;
}

25.5.创建链接并添加边框
可以在 <li> or <a> 上添加text-align:center 样式来让链接居中。

可以在 border <ul> 上添加 border 属性来让导航栏有边框。如果要在每个选项上添加边框，可以在每个 <li> 元素上添加border-bottom :
ul {
    border: 1px solid #555;
}
 
li {
    text-align: center;
    border-bottom: 1px solid #555;
}
 
li:last-child {
    border-bottom: none;
}

25.6.全屏高度的固定导航条
接下来我们创建一个左边是全屏高度的固定导航条，右边是可滚动的内容。
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    width: 25%;
    background-color: #f1f1f1;
    height: 100%; /* 全屏高度 */
    position: fixed; 
    overflow: auto; /* 如果导航栏选项多，允许滚动 */
}

25.7水平导航栏
有两种方法创建横向导航栏。使用内联(inline)或浮动(float)的列表项。

这两种方法都很好，但如果你想链接到具有相同的大小，你必须使用浮动的方法。

内联列表项
建立一个横向导航栏的方法之一是指定元素， 下述代码是标准的内联:
li
{
    display:inline;
}
实例解析：

display:inline; - 默认情况下，<li> 元素是块元素。在这里，我们删除换行符之前和之后每个列表项，以显示一行。

25.8浮动列表项
在上面的例子中链接有不同的宽度。

对于所有的链接宽度相等，浮动 <li>元素，并指定为 <a>元素的宽度：
li
{
    float:left;
}
a
{
    display:block;
    width:60px;
}
float:left - 使用浮动块元素的幻灯片彼此相邻
display:block - 显示块元素的链接，让整体变为可点击链接区域（不只是文本），它允许我们指定宽度
width:60px - 块元素默认情况下是最大宽度。我们要指定一个60像素的宽度

25.9水平导航条实例
创建一个水平导航条，在鼠标移动到选项后修改背景颜色。
ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333;
}
 
li {
    float: left;
}
 
li a {
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}
 
/*鼠标移动到选项上修改背景颜色 */
li a:hover {
    background-color: #111;
}

25.10激活/当前导航条实例
在点击了选项后，我们可以添加 "active" 类来标准哪个选项被选中：
.active {
    background-color: #4CAF50;
}

25.11.链接右对齐
将导航条最右边的选项设置右对齐 (float:right;)：
<ul>
  <li><a href="#home">主页</a></li>
  <li><a href="#news">新闻</a></li>
  <li><a href="#contact">联系</a></li>
  <li style="float:right"><a class="active" href="#about">关于</a></li>
</ul>

25.12.添加分割线
<li> 通过 border-right 样式来添加分割线:
/* 除了最后一个选项(last-child) 其他的都添加分割线 */
li {
    border-right: 1px solid #bbb;
}
 
li:last-child {
    border-right: none;
}

25.13.固定导航条
可以设置页面的导航条固定在头部或者底部：
头部
ul {
    position: fixed;
    top: 0;
    width: 100%;
}
底部
ul {
    position: fixed;
    bottom: 0;
    width: 100%;
}

25.14.灰色水平导航条
灰色水平导航条
ul {
    border: 1px solid #e7e7e7;
    background-color: #f3f3f3;
}
 
li a {
    color: #666;
}

26.CSS 下拉菜单
使用 CSS 创建一个鼠标移动上去后显示下拉菜单的效果。

26.1.基本下拉菜单
当鼠标移动到指定元素上时，会出现下拉菜单。
<style>
.dropdown {
  position: relative;
  display: inline-block;
}
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  padding: 12px 16px;
}
.dropdown:hover .dropdown-content {
  display: block;
}
</style>
<div class="dropdown">
  <span>鼠标移动到我这！</span>
  <div class="dropdown-content">
    <p>菜鸟教程</p>
    <p>www.runoob.com</p>
  </div>
</div>

实例解析
HTML 部分：

我们可以使用任何的 HTML 元素来打开下拉菜单，如：<span>, 或 a <button> 元素。

使用容器元素 (如： <div>) 来创建下拉菜单的内容，并放在任何你想放的位置上。

使用 <div> 元素来包裹这些元素，并使用 CSS 来设置下拉内容的样式。

CSS 部分：

.dropdown 类使用 position:relative, 这将设置下拉菜单的内容放置在下拉按钮 (使用 position:absolute) 的右下角位置。

.dropdown-content 类中是实际的下拉菜单。默认是隐藏的，在鼠标移动到指定元素后会显示。 注意 min-width 的值设置为 160px。你可以随意修改它。 注意: 如果你想设置下拉内容与下拉按钮的宽度一致，可设置 width 为 100% ( overflow:auto 设置可以在小尺寸屏幕上滚动)。

我们使用 box-shadow 属性让下拉菜单看起来像一个"卡片"。

:hover 选择器用于在用户将鼠标移动到下拉按钮上时显示下拉菜单。

26.2.下拉菜单
创建下拉菜单，并允许用户选取列表中的某一项：

下拉菜单
这个实例类似前面的实例，当我们在下拉列表中添加了链接，并设置了样式：
<style>/* 下拉按钮样式 */.dropbtn {    
	background-color: #4CAF50;    color: white;    
	padding: 16px;    font-size: 16px;    
	border: none;    cursor: pointer;}/* 
	容器 <div> - 需要定位下拉内容 */.dropdown {    position: relative;    display: 
	inline-block;}/* 下拉内容 (默认隐藏) */
	.dropdown-content {    display: none;    position: 
	absolute;    background-color: #f9f9f9;    
	min-width: 160px;    box-shadow: 
	0px 8px 16px 0px rgba(0,0,0,0.2);}/* 下拉菜单的链接 */
	.dropdown-content a {    color: black;    
	padding: 12px 16px;    text-decoration: none;    
	display: block;}/* 鼠标移上去后修改下拉菜单链接颜色 */
	.dropdown-content a:hover {background-color: #f1f1f1}/* 
	在鼠标移上去后显示下拉菜单 */.dropdown:hover .dropdown-content {    
	display: block;}/* 当下拉内容显示后修改下拉按钮的背景颜色 */.dropdown:hover .dropbtn {    
	background-color: #3e8e41;}</style><div class="dropdown">  <button class="dropbtn">下拉菜单</button>  
	<div class="dropdown-content">    <a href="#">菜鸟教程 
	1</a>    
	<a href="#">菜鸟教程 2</a>    <a href="#">菜鸟教程 3</a>  </div></div>

26.3下拉内容对齐方式
float:left;
左
float:right;

如果你想设置右浮动的下拉菜单内容方向是从右到左，而不是从左到右，可以添加以下代码 right: 0;

.dropdown-content {
    right: 0;
}

27.CSS 提示工具(Tooltip)
本文我们为大家介绍如何使用 HTML 与 CSS 来创建提示工具。

提示工具在鼠标移动到指定元素后触发，先看以下四个实例：

27.1.基础提示框(Tooltip)
提示框在鼠标移动到指定元素上显示：

<style>/* Tooltip 容器 */
.tooltip {
    position: relative;
    display: inline-block;
    border-bottom: 1px dotted black; /* 悬停元素上显示点线 */
}
 
/* Tooltip 文本 */
.tooltip .tooltiptext {
    visibility: hidden;
    width: 120px;
    background-color: black;
    color: #fff;
    text-align: center;
    padding: 5px 0;
    border-radius: 6px;
 
    /* 定位 */
    position: absolute;
    z-index: 1;
}
 
/* 鼠标移动上去后显示提示框 */
.tooltip:hover .tooltiptext {
    visibility: visible;
}</style>
 
<div class="tooltip">鼠标移动到这
  <span class="tooltiptext">提示文本</span>
</div>

实例解析
HTML) 使用容器元素 (like <div>) 并添加 "tooltip" 类。在鼠标移动到 <div> 上时显示提示信息。

提示文本放在内联元素上(如 <span>) 并使用class="tooltiptext"。

CSS)tooltip 类使用 position:relative, 提示文本需要设置定位值 position:absolute。 注意: 接下来的实例会显示更多的定位效果。

tooltiptext 类用于实际的提示文本。模式是隐藏的，在鼠标移动到元素显示 。设置了一些宽度、背景色、字体色等样式。

CSS3 border-radius 属性用于为提示框添加圆角。

:hover 选择器用于在鼠标移动到到指定元素 <div> 上时显示的提示。

27.2定位提示工具
以下实例中，提示工具显示在指定元素的右侧(left:105%) 。

注意 top:-5px 同于定位在容器元素的中间。使用数字 5 因为提示文本的顶部和底部的内边距（padding）是 5px。

如果你修改 padding 的值，top 值也要对应修改，这样才可以确保它是居中对齐的。

在提示框显示在左边的情况也是这个原理。
.tooltip .tooltiptext {
    top: -5px;
    left: 105%; 
}

27.3添加箭头
我们可以用CSS 伪元素 ::after 及 content 属性为提示工具创建一个小箭头标志，箭头是由边框组成的，但组合起来后提示工具像个语音信息框。

以下实例演示了如何为显示在顶部的提示工具添加底部箭头：
.tooltip .tooltiptext::after {
    content: " ";
    position: absolute;
    top: 100%; /* 提示工具底部 */
    left: 50%;
    margin-left: -5px;
    border-width: 5px;
    border-style: solid;
    border-color: black transparent transparent transparent;
}
实例解析
在提示工具内定位箭头: top: 100% , 箭头将显示在提示工具的底部。left: 50% 用于居中对齐箭头。

注意：border-width 属性指定了箭头的大小。如果你修改它，也要修改 margin-left 值。这样箭头才能居中显示。

border-color 用于将内容转换为箭头。设置顶部边框为黑色，其他是透明的。如果设置了其他的也是黑色则会显示为一个黑色的四边形。

以下实例演示了如何在提示工具的头部添加箭头，注意设置边框颜色：

27.4淡入效果
我们可以使用 CSS3 transition 属性及 opacity 属性来实现提示工具的淡入效果:
.tooltip .tooltiptext {
    opacity: 0;
    transition: opacity 1s;
}
 
.tooltip:hover .tooltiptext {
    opacity: 1;
}

28.CSS 媒体类型
媒体类型允许你指定文件将如何在不同媒体呈现。该文件可以以不同的方式显示在屏幕上，在纸张上，或听觉浏览器等等。 

媒体类型
一些 CSS 属性只设计了某些媒体。例如 voice-family 属性是专为听觉用户代理。其他一些属性可用于不同的媒体类型。例如， font-size 属性可用于屏幕和印刷媒体，但有不同的值。屏幕和纸上的文件不同，通常需要一个更大的字体，sans-serif 字体比较适合在屏幕上阅读，而 serif 字体更容易在纸上阅读。

28.1@media 规则
@media 规则允许在相同样式表为不同媒体设置不同的样式。

在下面的例子告诉我们浏览器屏幕上显示一个 14 像素的 Verdana 字体样式。但是如果页面打印，将是 10 个像素的 Times 字体。请注意，font-weight 在屏幕上和纸上设置为粗体：
@media screen
{
    p.test {font-family:verdana,sans-serif;font-size:14px;}
}
@media print
{
    p.test {font-family:times,serif;font-size:10px;}
}
@media screen,print
{
    p.test {font-weight:bold;}
}
其他媒体类型
注意：媒体类型名称不区分大小写。

媒体类型	描述
all	用于所有的媒体设备。
aural	用于语音和音频合成器。
braille	用于盲人用点字法触觉回馈设备。
embossed	用于分页的盲人用点字法打印机。
handheld	用于小的手持的设备。
print	用于打印机。
projection	用于方案展示，比如幻灯片。
screen	用于电脑显示器。
tty	用于使用固定密度字母栅格的媒体，比如电传打字机和终端。
tv	用于电视机类型的设备。

29.CSS 属性 选择器
具有特定属性的HTML元素样式
具有特定属性的HTML元素样式不仅仅是class和id。

注意：IE7和IE8需声明!DOCTYPE才支持属性选择器！IE6和更低的版本不支持属性选择器。

属性选择器
下面的例子是把包含标题（title）的所有元素变为蓝色：
[title]
{
    color:blue;
}

29.1.属性和值选择器
下面的实例改变了标题title='runoob'元素的边框样式:
属性和值的选择器 - 多值
下面是包含指定值的title属性的元素样式的例子，使用（~）分隔属性和值:
[title~=hello] { color:blue; }

下面是包含指定值的lang属性的元素样式的例子，使用（|）分隔属性和值:

[lang|=en] { color:blue; }


29.2表单样式
属性选择器样式无需使用class或id的形式:


30.CSS 表单

30.1输入框(input) 样式(简单的输入)
使用 width 属性来设置输入框的宽度：
    input{
            width:100%;
        }
以上实例中设置了所有 <input> 元素的宽度为 100%，如果你只想设置指定类型的输入框可以使用以下属性选择器：

input[type=text] - 选取文本输入框
input[type=password] - 选择密码的输入框
input[type=number] - 选择数字的输入框

30.2输入框填充
使用 padding 属性可以在输入框中添加内边距。

CSS 实例
input[type=text] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
}
注意我们设置了 box-sizing 属性为 border-box。这样可以确保浏览器呈现出带有指定宽度和高度的输入框是把边框和内边距一起计算进去的。

30.3.输入框(input) 边框
使用 border 属性可以修改 input 边框的大小或颜色，使用 border-radius 属性可以给 input 添加圆角：

CSS 实例
input[type=text] {
  border: 2px solid red;
  border-radius: 4px;
}

30.4.如果你只想添加底部边框可以使用 border-bottom 属性:

CSS 实例
input[type=text] {
  border: none;
  border-bottom: 2px solid red;

30.5.输入框(input) 颜色
可以使用 background-color 属性来设置输入框的背景颜色，color 属性用于修改文本颜色：

CSS 实例
input[type=text] {
  background-color: #3CBC8D;
  color: white;
}

30.6.输入框(input) 聚焦
默认情况下，一些浏览器在输入框获取焦点时（点击输入框）会有一个蓝色轮廓。我们可以设置 input 样式为 outline: none; 来忽略该效果。

使用 :focus 选择器可以设置输入框在获取焦点时的样式：

CSS 实例
input[type=text]:focus {
  background-color: lightblue;

30.7.输入框(input) 图标
如果你想在输入框中添加图标，可以使用 background-image 属性和用于定位的background-position 属性。注意设置图标的左边距，让图标有一定的空间：

CSS 实例
input[type=text] {
  background-color: white;
  background-image: url('searchicon.png');
  background-position: 10px 10px; 
  background-repeat: no-repeat;
  padding-left: 40px;
}

30.9.带动画的搜索框
以下实例使用了 CSS transition 属性，该属性设置了输入框在获取焦点时会向右延展。你可以在 CSS 动画 章节查看更多内容。

CSS 实例
input[type=text] {
  -webkit-transition: width 0.4s ease-in-out;
  transition: width 0.4s ease-in-out;
}
 
input[type=text]:focus {
  width: 100%;
}

30.10.文本框（textarea）样式
注意: 使用 resize 属性来禁用文本框可以重置大小的功能（一般拖动右下角可以重置大小）。

CSS 实例
textarea {
  width: 100%;
  height: 150px;
  padding: 12px 20px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  background-color: #f8f8f8;
  resize: none;
}

30.11.下拉菜单（select）样式
CSS 实例
select {
  width: 100%;
  padding: 16px 20px;
  border: none;
  border-radius: 4px;
  background-color: #f1f1f1;
}
30.12按钮样式
CSS 实例
input[type=button], input[type=submit], input[type=reset] {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 16px 32px;
  text-decoration: none;
  margin: 4px 2px;
  cursor: pointer;
}
 
/* 提示: 使用 width: 100% 设置全宽按钮 */

30.13.响应式表单
响应式表单可以根据浏览器窗口的大小重新布局各个元素，我们可以通过重置浏览器窗口大小来查看效果：

高级: 以下实例使用了CSS3 多媒体查询 来创建一个响应式表单。

* {
  box-sizing: border-box;
}
 
input[type=text], select, textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  resize: vertical;
}
 
label {
  padding: 12px 12px 12px 0;
  display: inline-block;
}
 
input[type=submit] {
  background-color: #4CAF50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  float: right;
}
 
input[type=submit]:hover {
  background-color: #45a049;
}
 
.container {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
 
.col-25 {
  float: left;
  width: 25%;
  margin-top: 6px;
}
 
.col-75 {
  float: left;
  width: 75%;
  margin-top: 6px;
}
 
/* 清除浮动 */
.row:after {
  content: "";
  display: table;
  clear: both;
}
 
/* 响应式布局 layout - 在屏幕宽度小于 600px 时， 设置为上下堆叠元素 */
@media screen and (max-width: 600px) {
  .col-25, .col-75, input[type=submit] {
    width: 100%;
    margin-top: 0;
  }
}

31.CSS 计数器
CSS 计数器通过一个变量来设置，根据规则递增变量。

使用计数器自动编号
CSS 计数器根据规则来递增变量。

CSS 计数器使用到以下几个属性：

counter-reset - 创建或者重置计数器
counter-increment - 递增变量
content - 插入生成的内容
counter() 或 counters() 函数 - 将计数器的值添加到元素
要使用 CSS 计数器，得先用 counter-reset 创建：

以下实例在页面创建一个计数器 (在 body 选择器中)，每个 <h2> 元素的计数值都会递增，并在每个 <h2> 元素前添加 "Section <计数值>:"

body {
  counter-reset: section;
}
 
h2::before {
  counter-increment: section;
  content: "Section " counter(section) ": ";
}

31.1.嵌套计数器
以下实例在页面创建一个计数器，在每一个 <h1> 元素前添加计数值 "Section <主标题计数值>.", 嵌套的计数值则放在 <h2> 元素的前面，内容为 "<主标题计数值>.<副标题计数值>":
body {
  counter-reset: section;
}
 
h1 {
  counter-reset: subsection;
}
 
h1::before {
  counter-increment: section;
  content: "Section " counter(section) ". ";
}
 
h2::before {
  counter-increment: subsection;
  content: counter(section) "." counter(subsection) " ";
}
计数器也可用于列表中，列表的子元素会自动创建。这里我们使用了 counters() 函数在不同的嵌套层级中插入字符串:
ol {
  counter-reset: section;
  list-style-type: none;
}
 
li::before {
  counter-increment: section;
  content: counters(section,".") " ";
}

31.2CSS 计数器属性
属性	描述
content	使用 ::before 和 ::after 伪元素来插入自动生成的内容
counter-increment	递增一个或多个值
counter-reset	创建或重置一个或多个计数器

32.CSS 网页布局
网页布局
网页布局有很多种方式，一般分为以下几个部分：头部区域、菜单导航区域、内容区域、底部区域。
.header {
  background-color: #F1F1F1;
  text-align: center;
  padding: 20px;
}

32.1.菜单导航区域
菜单导航条包含了一些链接，可以引导用户浏览其他页面：
/* 导航条 */
.topnav {
  overflow: hidden;
  background-color: #333;
}
 
/* 导航链接 */
.topnav a {
  float: left;
  display: block;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}
 
/* 链接 - 修改颜色 */
.topnav a:hover {
  background-color: #ddd;
  color: black;
}

32.2.内容区域
内容区域一般有三种形式:

1 列：一般用于移动端
2 列：一般用于平板设备
3 列：一般用于 PC 桌面设备

我们将创建一个 3 列布局，在小的屏幕上将会变成 1 列布局（响应式）：

/* 创建三个相等的列 */
.column {
  float: left;
  width: 33.33%;
}
 
/* 列后清除浮动 */
.row:after {
  content: "";
  display: table;
  clear: both;
}
 
/* 响应式布局 - 小于 600 px 时改为上下布局 */
@media screen and (max-width: 600px) {
  .column {
    width: 100%;
  }
}
提示:要设置两列可以设置 width 为 50%。创建 4 列可以设置为 25%。

提示:如果你想了解更多 @media 的规则可以查看 CSS3 多媒体查询。

提示: 现在更高级的方式是使用 CSS Flexbox 来创建列的布局，但 Internet Explorer 10 及更早的版本不支持该方式， IE6-10 可以使用浮动方式。

32.3.不相等的列
不相等的列一般是在中间部分设置内容区域，这块也是最大最主要的，左右两次侧可以作为一些导航等相关内容，这三列加起来的宽度是 100％。

.column {
  float: left;
}
 
/* 左右侧栏的宽度 */
.column.side {
  width: 25%;
}
 
/* 中间列宽度 */
.column.middle {
  width: 50%;
}
 
/* 响应式布局 - 宽度小于600px时设置上下布局 */
@media screen and (max-width: 600px) {
  .column.side, .column.middle {
    width: 100%;
  }
}

32.4.底部区域
底部区域在网页的最下方，一般包含版权信息和联系方式等。
.footer {
  background-color: #F1F1F1;
  text-align: center;
  padding: 10px;
}

33.CSS !important 规则
什么是 !important
CSS 中的 !important 规则用于增加样式的权重。

!important 与优先级无关，但它与最终的结果直接相关，使用一个 !important 规则时，此声明将覆盖任何其他声明。
#myid {
  background-color: blue;
}
 
.myclass {
  background-color: gray;
}
 
p {
  background-color: red !important;
}

以上实例中，尽管 ID 选择器和类选择器具有更高的优先级，但三个段落背景颜色都显示为红色，因为 !important 规则会覆盖 background-color 属性。

重要说明
使用 !important 是一个坏习惯，应该尽量避免，因为这破坏了样式表中的固有的级联规则 使得调试找 bug 变得更加困难了。

当两条相互冲突的带有 !important 规则的声明被应用到相同的元素上时，拥有更大优先级的声明将会被采用。

以下实例我们在查看 CSS 源码时就不是很清楚哪种颜色最重要：
#myid {
  background-color: blue !important;
}
 
.myclass {
  background-color: gray !important;
}
 
p {
  background-color: red !important;
}

使用建议：

一定要优先考虑使用样式规则的优先级来解决问题而不是 !important
只有在需要覆盖全站或外部 CSS 的特定页面中使用 !important
永远不要在你的插件中使用 !important
永远不要在全站范围的 CSS 代码中使用 !important

33.1.何时使用 !important
如果要在你的网站上设定一个全站样式的 CSS 样式可以使用 !important。

比如我们要让网站上所有按钮的样式都一样：
.button {
  background-color: #8c8c8c;
  color: white;
  padding: 5px;
  border: 1px solid black;
}

如果我们将按钮放在另一个具有更优先级的元素中，按钮的外观就会发生变化，并且属性会发生冲突，如下实例：
.button {
  background-color: #8c8c8c;
  color: white;
  padding: 5px;
  border: 1px solid black;
}
 
#myDiv a {
  color: red;
  background-color: yellow;
}

如果想要设置所有按钮具有相同的外观，我们可以将 !important 规则添加到按钮的样式属性中，如下所示：
.button {
  background-color: #8c8c8c !important;
  color: white !important;
  padding: 5px !important;
  border: 1px solid black !important;
}
 
#myDiv a {
  color: red;
  background-color: yellow;
}
