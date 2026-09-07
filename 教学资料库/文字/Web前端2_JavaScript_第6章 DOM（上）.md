# 第6章 DOM（上）

《JavaScript+jQuery交互式Web前端开发（第2版）》

# 学习目标/Target

# 学习目标/Target

# 章节概述/ Summary

通过第1~5章的学习，相信读者已经掌握了JavaScript的基础知识。在实际开发过程中，若要实现网页交互效果，仅仅掌握JavaScript的基础知识是不够的，还需要进一步学习Web API的相关知识。在本阶段主要学习使用DOM和BOM实现网页交互效果，由于DOM和BOM的知识内容较多，所以本章首先对DOM（上）的基本知识进行讲解，关于DOM（下）和BOM的相关知识将在后续章节中讲解。

# 目录/Contents

# Web API简介

6.1

# 了解Web API的概念，能够阐述Web API的作用

6.1  Web API简介

先定一个小目标！

# 6.1  Web API简介

# 例如，开发一个美颜相机手机应用，该手机应用需要使用手机上的摄像头拍摄画面，手机的操作系统需要将访问摄像头的功能开放给手机应用，为此，手机操作系统提供了摄像头API，手机应用通过摄像头API就可以获得访问摄像头的功能。

6.1  Web API简介

# 在JavaScript中，Web API被封装成对象，用于帮助开发者实现某种功能。开发人员无须访问对象源代码，也无须理解对象内部工作机制和细节，只需要掌握如何使用对象的属性和方法。

例如，在程序中，经常使用console.log()输出一些信息，其中，console就是Web API对象，用于操作控制台，log()方法用于在控制台输出信息。

DOM和BOM都包含一系列对象，这些对象都属于Web API。

6.1  Web API简介

# DOM简介

6.2

# 了解什么是DOM，能够描述DOM中文档、元素和节点的关系

先定一个小目标！

6.2  DOM简介

# 6.2  DOM简介

# DOM将整个文档视为树形结构，这个结构被称为文档树。页面中所有的内容在文档树中都是节点（Node），所有的节点都会被看作是对象，这些对象都拥有属性和方法。

6.2  DOM简介

# 节点有多种类型，常见的类型及解释如下。

元素节点：代表页面中的标签。例如，<div>标签属于元素节点，通常称为div元素或div节点。
文本节点：代表页面中的文本内容。例如，“<div>内容</div>”中的“内容”属于文本节点。
注释节点：代表页面中的注释。例如，“<!-- 注释 -->”属于注释节点。
文档节点：代表整个文档。
文档类型节点：代表文档的类型定义。例如，“<!DOCTYPE html>”属于文档类型节点。

6.2  DOM简介

# 不同节点之间的关系可以用传统的家族关系进行描述，例如，父子关系、兄弟关系，通过这些关系可以将节点划分为不同层级，具体如下。

父节点：是指某一节点的上级节点。
子节点：是指某一节点的下级节点。
兄弟节点：是指同一个父节点的两个子节点。
根节点：document节点是整个文档的根节点。根节点是文档树中唯一没有父节点的节点，所有其他节点都是根节点的后代。

6.2  DOM简介

# 如果一个节点的父节点、子节点或兄弟节点是元素节点，则可以将其称为父元素、子元素或兄弟元素。根元素对应的标签为<html>标签。
下面演示一个简单的文档树示例，如下图所示。

6.2  DOM简介

# 节点对象有3个常用的属性，具体解释如下。

nodeType属性：用于获取数字表示的节点类型。1表示元素节点，3表示文本节点、8表示注释节点、9表示文档节点，10表示文档类型节点。

nodeName属性：用于获取节点名称。

nodeValue属性：用于获取节点值，适用于文本节点、注释节点。

6.2  DOM简介

# 获取元素

6.3

# 掌握根据id属性获取元素的方法，能够根据getElementById()方法获取元素

6.3.1	根据id属性获取元素

先定一个小目标！

# 在HTML中，为元素设置id属性可以作为元素设置唯一标识。document对象提供了getElementById()方法，用于根据id属性获取元素，该方法的语法格式如下。

document.getElementById(id)

上述语法格式中，参数id表示id属性值。在调用getElementById()方法后会返回一个元素对象，这个元素对象就是根据id属性获取的目标元素。若没有找到指定id属性的元素，则返回null。

6.3.1	根据id属性获取元素

# 6.3.1	根据id属性获取元素

下面通过代码演示getElementById()方法的使用。

<body>
  <ul>
    <li id="menu">家居</li>
    <li>美妆</li>
    <li>食品</li>
  </ul>
  <script>
    // 根据id属性获取元素
    var Obox = document.getElementById('menu');
    console.log(Obox);
  </script>
</body>

# 先定一个小目标！

6.3.2	根据标签名获取元素

掌握根据标签名获取元素的方法，能够根据getElementsByTagName()方法获取元素

# 在实际开发中，有时需要获取多个元素，而getElementById()方法一次只能获取一个元素，当要获取多个元素时，操作比较烦琐。为此，document对象还提供了一种通过标签名获取元素的方法，即getElementsByTagName()方法，该方法的语法格式如下。

document.getElementsByTagName(name)

上述语法格式中，参数name表示标签名。在使用getElementsByTagName()方法时，只需将标签名作为参数传入即可。由于具有相同标签名的元素可能有多个，所以该方法的返回结果不是单个元素对象，而是一个集合。

6.3.2	根据标签名获取元素

# 下面通过代码演示getElementsByTagName()方法的使用。

<body>
  <ul>
    <li>家居</li>
    <li>美妆</li>
    <li>食品</li>
  </ul>
  <script>
    // 根据标签名获取元素
    var list = document.getElementsByTagName('li');
    console.log(list);
  </script>
</body>

6.3.2	根据标签名获取元素

# 需要注意的是，getElementsByTagName()方法返回的集合与数组的使用方法类似，但是它本质上并不是数组。为了证明这一点，可以通过在前面示例代码的第10行代码下方添加如下代码进行验证。

console.log(Array.isArray(list));	// 输出结果为：false

6.3.2	根据标签名获取元素

上述运行代码后，控制台输出的结果为false，说明调用getElementsByTagName()方法后返回的结果不是数组。这种类似数组但不是数组的数据称为类数组（array-like）对象，类数组对象可以像数组一样通过索引访问元素，但不能使用数组的方法。

# 6.3.2	根据标签名获取元素

需要注意的是，即使页面中只有一个li元素，getElementsByTagName()方法返回的结果仍然是一个集合，如果页面中没有该元素，那么将返回一个空集合。通过getElementsByTagName()方法获取到的集合是动态集合，当页面增加标签时，在该集合中也会自动增加元素。

# 先定一个小目标！

6.3.3	根据name属性获取元素

掌握根据name属性获取元素的方法，能够根据getElementsByName()方法获取元素

# 在实际开发中，经常需要编写表单页面的交互逻辑代码，此时就需要获取表单元素。表单元素通过name属性设置元素名称，为了通过name属性获取表单元素，document对象提供了getElementsByName()方法，该方法的语法格式如下。

document.getElementsByName(name)

上述语法格式中，参数name表示name属性值。在使用getElementsByName()方法时，只需将name属性值作为参数传入即可，由于name属性的值不要求必须唯一，多个元素可以有相同的名称，如表单中的单选框和复选框等，所以该方法的返回结果不是单个元素对象，而是一个集合。

6.3.3	根据name属性获取元素

# 下面通过代码演示getElementsByName()方法的使用。

6.3.3	根据name属性获取元素

<body>
  <p>请选择你最喜欢的水果（多选）</p>
  <input type="checkbox" name="fruit" value="草莓">草莓
  <input type="checkbox" name="fruit" value="雪梨">雪梨
  <input type="checkbox" name="fruit" value="芒果">芒果
  <script>
    var favoriteFruit = document.getElementsByName('fruit');
    console.log(favoriteFruit);
    console.log(favoriteFruit[2]); 
  </script>
</body>

# 先定一个小目标！

6.3.4	根据类名获取元素

掌握根据类名获取元素的方法，能够根据getElementsByClassName()方法获取元素

# 如果需要根据类名获取元素，可以在页面中为元素设置类名，然后使用document对象提供的getElementsByClassName()方法获取元素，该方法的语法格式如下。

document.getElementsByClassName(names)

上述语法格式中，参数names表示要匹配的类名列表，多个类名之间使用空格分隔。

需要说明的是，一些旧版本的浏览器（如IE 6~IE 8）不支持getElementsByClassName()方法。

6.3.4	根据类名获取元素

# 下面通过代码演示getElementsByClassName()方法的使用。

<body>
  <ul>
    <li class="girl">小花</li>
    <li class="girl">小红</li>
    <li class="boy">小智</li>
    <li class="boy">小强</li>
  </ul>
  <script>
    var girlStudent = document.getElementsByClassName('girl');
    var boyStudent = document.getElementsByClassName('boy');
    console.log(girlStudent[0]);
    console.log(boyStudent[0]);
  </script>
</body>

6.3.4	根据类名获取元素

# 先定一个小目标！

6.3.5	根据CSS选择器获取元素

掌握根据CSS选择器获取元素的方法，能够根据querySelector()方法和querySelectorAll()方法获取元素

# 在DOM中，还可以根据CSS选择器获取元素。document对象提供了querySelector()方法和querySelectorAll()方法获取目标元素，这两个方法的语法格式如下。

document.querySelector(selectors)
document.querySelectorAll(selectors)

上述语法格式中，参数selectors表示CSS选择器。querySelector()方法的使用方式和querySelectorAll()方法的使用方式相似，只需将CSS选择器作为参数传入即可。这两个方法的区别是，querySelector()方法返回指定CSS选择器的第一个元素对象，querySelectorAll()方法返回指定CSS选择器的所有元素对象集合。

6.3.5	根据CSS选择器获取元素

# 在使用querySelector()方法和querySelectorAll()方法时，要注意IE浏览器的兼容问题，这两个方法从IE 9才开始被完整支持。

6.3.5	根据CSS选择器获取元素

# 下面通过代码演示querySelector()方法和querySelectorAll()方法的使用。

<body>
  <div class="book">西游记</div>
  <div class="book">红楼梦</div>
  <div class="book">三国演义</div>
  <div class="book">水浒传</div>
  <script>
    // 获取类名为book的第1个div元素
    var firstBook = document.querySelector('.book'); 
    console.log(firstBook);
    // 获取类名为book的所有div元素
    var allBook = document.querySelectorAll('.book');
    console.log(allBook); 
  </script>
</body>

6.3.5	根据CSS选择器获取元素

# 掌握获取基本结构元素的属性，能够灵活应用获取基本结构元素的属性

先定一个小目标！

6.3.6	获取基本结构元素

# 6.3.6	获取基本结构元素

在实际开发中，若需要获取HTML中的基本结构元素（如html、body等），可以通过document对象的属性获取。获取基本结构元素的document对象的属性如下表所示。

| 属性 | 作用 |
|---|---|
| document.documentElement | 获取文档的html元素 |
| document.body | 获取文档的body元素 |
| document.forms | 获取文档中包含所有form元素的集合 |
| document.images | 获取文档中包含所有image元素的集合 |

# 6.3.6	获取基本结构元素

下面通过代码演示如何获取文档中body元素和html元素。

<script>
  // 获取body元素
  var bodyEle = document.body;
  console.log(bodyEle);
  // 获取html元素
  var htmlEle = document.documentElement;
  console.log(htmlEle);
</script>

# 6.3.6	获取基本结构元素

# 获取或设置当前文档的标题

多学一招

在实际开发中，当需要获取或设置当前文档的标题时，可以使用document对象提供的title属性，示例代码如下。

console.log(document.title);	 // 获取标题
document.title = '新标题'; 	 // 设置标题

6.3.6	获取基本结构元素

# 多学一招

下面通过代码演示如何获取当前文档的标题。

<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>这是文档标题</title>
</head>
<body>
  <script>
    console.log(document.title);
  </script>
</body>
</html>

6.3.6	获取基本结构元素

# 事件基础

6.4

# 了解事件的概念，能够描述事件的3个要素

先定一个小目标！

6.4.1	事件概述

# 6.4.1	事件概述

# 事件是一种“触发-响应”机制，行为产生后，对应的事件就会被触发，事件驱动程序就会被调用，从而使网页响应并产生交互效果。

6.4.1	事件概述

# 6.4.1	事件概述

事件有3个要素，分别是事件源、事件类型和事件驱动程序，具体解释如下。

事件源：承受事件的元素对象。例如，在单击按钮的过程中，按钮就是事件源。
事件类型：使网页产生交互效果的行为对应的事件种类。例如，单击事件的事件类型为click。
事件驱动程序：事件触发后为了实现相应的网页交互效果而运行的代码。

# 若要实现网页交互效果，首先需要确定事件源，事件源确定后就可以获取这个元素；然后需要确定事件类型，为获取的元素注册该类型的事件；最后分析事件触发后，实现相应网页交互效果的逻辑，编写实现该逻辑的事件驱动程序。

6.4.1	事件概述

# 掌握事件的注册，能够为页面中的元素注册事件

先定一个小目标！

6.4.2	事件注册

# 6.4.2	事件注册

# 注册事件有两种方式，一种是在标签中注册，另一种是在JavaScript中注册。在标签中注册事件的示例代码如下。

<div onclick="">按钮</div>

6.4.2	事件注册

上述示例代码中，在onclick属性的值中可以编写事件驱动程序。

在JavaScript中注册事件的示例代码如下。

// 元素对象.事件属性 = 事件处理函数;
element.onclick = function () {};

# 下面通过代码演示如何进行事件注册。定义一个按钮元素，通过注册事件，实现单击按钮元素后弹出内容为“事件注册”的警告框，示例代码如下。

<body>
  <button id="btn">单击</button>
  <script>
    // 获取事件源
    var button = document.getElementById('btn');
    // 为获取的元素注册单击事件
    button.onclick = function () {
      alert('事件注册');
    };
  </script>
</body>

6.4.2	事件注册

# 操作元素

6.5

# 掌握操作元素内容的方法，能够根据不同场景选择合适的方法操作元素内容

6.5.1	操作元素内容

先定一个小目标！

# 在实际开发中，当需要修改页面中的内容时，就需要操作元素内容，例如，修改页面元素的文本内容，或动态生成页面内容等。下面列举DOM提供的操作元素内容的常用属性，具体如下表所示。

6.5.1	操作元素内容

| 属性 | 作用 |
|---|---|
| innerHTML | 设置或获取元素开始标签和结束标签之间的HTML内容，返回结果包含HTML标签，并保留空格和换行 |
| innerText | 设置或获取元素的文本内容，返回结果会去除HTML标签和多余的空格、换行，在设置文本内容的时候会进行特殊字符转义 |
| textContent | 设置或获取元素的文本内容，返回结果保留空格和换行 |

# innerHTML属性获取的元素内容包含HTML标签；innerText属性获取的元素内容不包含HTML标签；textContent属性和innerText属性相似，都可以用来设置或获取元素的文本内容，并且返回结果会去除HTML标签，但是textContent属性还可以用于设置和获取占位隐藏元素的文本内容。

需要注意的是，IE 8及更早版本的浏览器不支持textContent属性，在使用时需要注意浏览器兼容问题。

小提示：通过给元素的visibility样式属性设置hidden值即可实现占位隐藏。

6.5.1	操作元素内容

# 首先搭建一个用于展示商品种类和商品状态的表格，商品种类分别是过季旧款、当前热销、春季新品，对应的商品状态分别是已下架、热卖中、待上架。

然后通过innerHTML属性获取过季旧款对应的商品状态，并将过季旧款对应的商品状态修改为已上架；通过innerText属性获取当前热销的商品状态，通过textContent属性获取春季新品的商品状态。

6.5.1	操作元素内容

# 6.5.1	操作元素内容

# 掌握操作元素属性的方法，能够根据不同场景选择合适的方法操作元素属性

先定一个小目标！

6.5.2	操作元素属性

# 6.5.2	操作元素属性

# 6.5.2	操作元素属性

1. 操作property属性

property是一个统称，它并不是一个具体的属性名，而是指元素在DOM中作为对象拥有的属性。

对于页面中property属性的操作，可以通过“元素对象.属性名”实现。

# 6.5.2	操作元素属性

img元素用于显示图片。下面列举img元素中的常用属性及其作用，具体如下表所示。

（1）操作img元素的属性

| 属性 | 作用 |
|---|---|
| src | 设置图片的路径 |
| alt | 设置图片加载失败时显示在网页上的替代文字 |
| title | 设置鼠标移到图片上时显示的提示文字 |
| width | 设置图片的宽度 |
| height | 设置图片的高度 |
| sizes | 设置图片的尺寸 |

# 下面以单击按钮操作img元素属性为例，演示img元素中src、title属性的使用方法，实现单击按钮时显示图片和图片对应的提示文字，示例代码如下。

6.5.2	操作元素属性

<body>
  <button id="vegetable">蔬菜</button>
  <button id="fruit">水果</button><br>
  <img src="images/fruit.png" alt="" title="水果">
  <script>
    // 通过id属性获取元素
    var vegetable = document.getElementById('vegetable');
    var fruit = document.getElementById('fruit');
     // 通过CSS选择器获取元素
    var img = document.querySelector('img');

# >>  续上一页代码

6.5.2	操作元素属性

// 注册事件处理程序
    vegetable.onclick = function () {
      img.src = 'images/vegetable.png';
      img.title = '蔬菜';
    };
    fruit.onclick = function () {
      img.src = 'images/fruit.png';
      img.title = '水果';
    };
  </script>
</body>

# 6.5.2	操作元素属性

input元素用于使用户在表单中输入内容。下面列举input元素中的常用属性及其作用，具体如下表所示。

（2）操作input元素的属性

| 属性 | 作用 |
|---|---|
| type | 设置文本框的类型，例如text、checkbox、radio、submit等 |
| name | 设置表单的名称 |
| value | 设置文本框的值，默认值为空字符串 |
| checked | 设置是否选中该元素，该属性仅在type为checkbox或radio时有效 |
| disabled | 设置表单元素是否被禁用 |

# 下面演示input元素中type、value和disabled属性的使用，实现单击按钮时，通过获取文本框的值并将其修改为“被单击了！”来改变文本框的值，并在单击按钮时设置禁用按钮，示例代码如下。

6.5.2	操作元素属性

<body>
  <button>搜索</button>
  <input type="text" value="输入内容">
  <script>
    // 通过CSS选择器获取元素
    var btn = document.querySelector('button');
    var input = document.querySelector('input');

# >>  续上一页代码

6.5.2	操作元素属性

// 注册事件处理程序
    btn.onclick = function () {
      input.value = '被单击了！';  // 通过value修改表单中值
      this.disabled = true;           // this指向事件函数的调用者btn
    };
  </script>
</body>

# 6.5.2	操作元素属性

2. 操作attribute属性

attribute属性也是一个统称，它是指HTML标签的属性。下面详细讲解attribute属性的操作。

（1）设置属性

通过元素对象的setAttribute()方法可以设置属性，其语法格式如下。

element.setAttribute('属性', '值');

# 6.5.2	操作元素属性

下面通过代码演示如何设置属性。

<body>
  <div></div>
  <script>
    var div = document.querySelector('div');
    div.setAttribute('flag', 3);
    div.setAttribute('id', 'book');
  </script>
</body>

# 6.5.2	操作元素属性

（2）获取属性值

通过元素对象的getAttribute()方法可以获取属性值，其语法格式如下。

element.getAttribute('属性');

下面通过代码演示如何获取属性值。

<body>
  <div id="demo1" index="1"></div>
  <script>
    var div = document.querySelector('div'); 
    console.log(div.getAttribute('id'));	         // 输出结果为：demo1
    console.log(div.getAttribute('index'));         // 输出结果为：1
  </script>
</body>

# 6.5.2	操作元素属性

（3）移除属性

通过元素对象的removeAttribute()方法可以移除属性，其语法格式如下。

element.removeAttribute('属性');

下面通过代码演示如何移除属性。

<body>
  <div id="demo2" index="2"></div>
  <script>
    var div = document.querySelector('div'); 
    console.log(div.removeAttribute('id'));
    console.log(div.removeAttribute('index'));
  </script>
</body>

# 6.5.2	操作元素属性

3. 操作data-*属性

data-*属性是HTML5提供的一种新的自定义属性，（通过“data-”前缀来设置开发所需要的自定义属性，“*”可以自行命名）。

（1）设置data-*属性

在HTML的标签中可以直接为元素设置data-*属性，示例代码如下。

<div data-index="3"></div>

在上述示例代码中，“data-”是属性前缀，index是自定义的属性名。

# 在DOM中设置data-*属性值的方式有两种，第1种方式是通过“元素对象.dataset.属性名 = 值”设置，也可以写为“元素对象.dataset['属性名'] = 值”，如果属性名包含连字符“-”，则需要采用驼峰命名法；第2种方式是通过setAttribute()方法设置。

6.5.2	操作元素属性

# 下面通过两种方式演示如何设置data-*属性，示例代码如下。

6.5.2	操作元素属性

<body>
  <div></div>
  <script>
    var div = document.querySelector('div');
    div.dataset.index = '3';                	         // 演示第1种方式
    div.setAttribute('data-name', '小智');     // 演示第2种方式
  </script>
</body>

# 6.5.2	操作元素属性

（2）获取data-*属性值

获取data-*属性值的方式有两种，第1种方式是通过“元素对象.dataset.属性名”获取，也可以写为“元素对象.dataset['属性名']”，如果属性名包含连字符“-”，则需要采用驼峰命名法；第2种方式是通过getAttribute()方法获取。

# 下面通过两种方式演示如何获取data-*属性值，示例代码如下。

6.5.2	操作元素属性

<body>
  <div getTime="20" data-index="3" data-list-name="小智"></div>
  <script>
    var div = document.querySelector('div');
    // 通过第1种方式获取
    console.log(div.dataset.index);	   // 输出结果为：3
    console.log(div.dataset['index']);     // 输出结果为：3
    console.log(div.dataset.listName);   // 输出结果为：小智
    console.log(div.dataset['listName']); // 输出结果为：小智

# >>  续上一页代码

6.5.2	操作元素属性

// 通过第2种方式获取
    console.log(div.getAttribute('data-index'));	       // 输出结果为：3
    console.log(div.getAttribute('data-list-name'));  // 输出结果为：小智
  </script>
</body>

# 掌握操作元素样式的方法，能够根据不同场景选择合适的方法操作元素样式

先定一个小目标！

6.5.3	操作元素样式

# 6.5.3	操作元素样式

# 1. 通过style属性操作元素样式

6.5.3	操作元素样式

在实际开发中，页面中样式的交互效果，可以通过操作元素对象的style属性实现，示例代码如下。

element.style.样式属性名 = '样式属性值';	// 设置样式
console.log(element.style.样式属性名);	// 获取样式

# 6.5.3	操作元素样式

下面列举style属性中常用的样式属性名，具体如下表所示。

| 样式属性名 | 作用 |
|---|---|
| background | 设置或获取元素的背景属性 |
| backgroundColor | 设置或获取元素的背景颜色 |
| display | 设置或获取元素的显示类型 |
| fontSize | 设置或获取元素的字体大小 |
| width | 设置或获取元素的宽度 |
| height | 设置或获取元素的高度 |
| left | 设置或获取定位元素的左部位置 |

# 6.5.3	操作元素样式

>>  续上一页表

| 样式属性名 | 作用 |
|---|---|
| listStyleType | 设置或获取列表项标记的类型 |
| overflow | 设置或获取如何处理呈现在元素框外面的内容 |
| textAlign | 设置或获取文本的水平对齐方式 |
| textDecoration | 设置或获取文本的修饰 |
| textIndent | 设置或获取文本第一行的缩进 |
| transform | 向元素应用2D或3D转换 |

# 6.5.3	操作元素样式

下面通过代码演示如何对元素对象添加样式。

<body>
  <div id="box"></div>
  <script>
    var ele = document.querySelector('#box');
    ele.style.width = '100px';
    ele.style.height = '100px';
    ele.style.transform = 'rotate(7deg)';
  </script>
</body>

其效果相当于在CSS中添加如下样式。

#box {width: 100px; height: 100px; transform: rotate(7deg);}

# 2. 通过className属性操作元素样式

6.5.3	操作元素样式

在实际开发中，当需要为元素对象设置多种样式时，若通过style属性实现，就需要编写多行“element.style.样式属性名 = '样式属性值';”形式的代码，此种方式非常烦琐。

为了能够方便快捷地实现为元素对象设置多种样式，可以通过className属性操作元素样式，设置该属性相当于设置元素对应标签的class属性。

# 6.5.3	操作元素样式

操作className属性时，首先将元素对象的样式写在CSS中，并使用CSS中的类选择器为元素设置样式，然后通过JavaScript操作className属性更改元素的类名，实现元素样式的更改。操作className属性的示例代码如下。

element.className = '类名';	// 设置类名
console.log(element.className);	// 获取类名

# 6.5.3	操作元素样式

下面通过代码演示如何通过className属性更改元素的样式。

<style>
  .target {
    width: 200px;
    height: 200px;
    border: 1px solid black;
    font-size: 10px;
    text-align: center;
    line-height: 200px;
  }
</style>

# 6.5.3	操作元素样式

通过JavaScript操作className属性更改元素类名的示例代码如下。

<body>
  <div class="box">使用className更改元素的样式</div>
  <script>
    // 获取div元素
    var box = document.querySelector('.box');
    // 为获取到的div元素设置className
    box.className = 'target';
  </script>
</body>

# 3. 通过classList属性操作元素样式

6.5.3	操作元素样式

在实际开发中，对于元素中类的操作还可以使用元素对象的classList属性，在使用该属性时，需要注意IE浏览器的兼容问题。

classList属性从IE 10开始才被支持，且IE 10中classList属性不能对SVG（Scalable Vector Graphics，可缩放矢量图形）元素进行操作。

# 6.5.3	操作元素样式

通过classList属性可以对元素中的类名进行获取、添加、移除、判断等操作。通过classList属性获取类名的示例代码如下。

element.classList

classList属性返回一个对象，该对象称为classList对象，是一个类数组对象，对象中的每一项对应一个类名，通过数组索引即可访问类名。

# 6.5.3	操作元素样式

classList对象还可以通过一系列属性和方法对元素的类名进行设置和移除。classList对象常用的属性和方法如下表所示。

| 属性和方法 | 作用 |
|---|---|
| length | 获取类名的数量 |
| add(class1,class2…) | 为元素添加一个或多个类名 |
| remove(class1,class2…) | 移除元素的一个或多个类名 |
| toggle(class,true|false) | 为元素切换类名，第2个参数是可选参数，设为true表示添加，设为false表示移除，若不设置表示有则移除，没有则添加 |
| contains(class) | 判断元素中指定的类名是否存在，返回布尔值 |
| item(index) | 获取元素中索引对应的类名，索引从0开始 |

# 掌握操作元素的综合应用的案例，能够编写代码实现案例

先定一个小目标！

6.5.4	【案例】操作元素的综合应用

# 在一些网站输入登录密码时，会发现用户输入的密码是隐藏的（显示为小黑点），通过单击文本框右侧的“眼睛”图片就可以使密码显示。

为了提升用户体验，可以使用两张不同状态的“眼睛”图片充当按钮，图片中的“眼睛”睁开时显示密码，闭合时隐藏密码。默认情况下，输入的密码是隐藏的，图片中的“眼睛”是闭合状态。

6.5.4	【案例】操作元素的综合应用

1. 显示隐藏密码明文

要想实现密码显示和隐藏的页面，首先通过<img>和<input>等标签搭建密码框结构，然后通过JavaScript实现密码框和文本框的切换，并切换对应的“眼睛”图片。

# 6.5.4	【案例】操作元素的综合应用

# 本案例要求单击文本框时，隐藏文本框默认的提示文字，单击文本框之外的区域时，显示文本框默认的提示文字。

首先为元素注册获取文本框焦点事件onfocus和失去焦点事件onblur，在获取焦点时，需要判断表单中的内容是否为默认文字，如果是默认文字，就清空表单内容，如果失去焦点，需要判断表单内容是否为空，如果为空，则表单里边的内容改为默认文字。

6.5.4	【案例】操作元素的综合应用

2. 显示隐藏文本框内容

# 6.5.4	【案例】操作元素的综合应用

# 在实际开发中，为了提高网页的界面设计和用户的使用体验，可以实现在多个选项之间进行切换时，保持只有一个选项处于选中状态，其他选项处于未选中状态的交互效果。例如，在页面中设置5个按钮，当用户单击某个按钮时，则改变按钮背景颜色，而其他按钮保持默认样式。

6.5.4	【案例】操作元素的综合应用

3. 高亮显示被单击的按钮

本案例要求在页面中设置5个按钮，当用户单击某个按钮时，高亮显示被单击的按钮，其他按钮保持默认样式。

# 6.5.4	【案例】操作元素的综合应用

# 在实际开发中，当表格中有多个单元格时，可以在鼠标指针经过时为当前行添加背景颜色，使表格内容一目了然。

下面使用鼠标指针经过事件onmouseover和鼠标指针离开事件onmouseout实现鼠标指针经过时背景变色的案例效果。

6.5.4	【案例】操作元素的综合应用

4. 鼠标指针经过时背景变色

# 6.5.4	【案例】操作元素的综合应用

# 6.5.4	【案例】操作元素的综合应用

前面运行结果的页面展示了编号01~03的商品信息，并且这3行商品信息均没有背景颜色，鼠标指针经过编号02的商品信息时的运行结果如下图所示。

# 本章小结

本章主要对DOM（上）进行讲解，首先讲解了Web API和DOM的概念，然后讲解了获取元素和事件基础，最后讲解了元素内容、属性和样式的操作。其中，获取元素主要讲解了根据id属性、标签名、name属性、类名、CSS选择器获取元素以及获取基本结构元素，事件基础主要讲解了事件的概念和事件的注册。通过本章的学习，读者应能够运用DOM完成一些基本的页面交互效果。

本

章

小

结