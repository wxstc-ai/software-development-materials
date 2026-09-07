# 第9章 jQuery（上）

《JavaScript+jQuery交互式Web前端开发（第2版）》

# 学习目标/Target

# 学习目标/Target

# 章节概述/ Summary

jQuery提供了许多简化DOM操作、事件处理、动画效果等常见任务的方法和函数。通过使用jQuery，可以快速地开发交互性更强的网页和Web应用程序，减少冗余的代码，解决浏览器兼容问题。因此，学习和掌握jQuery具有重要的价值。jQuery的知识内容较多，本章首先对jQuery的上半部分内容进行讲解。

# 目录/Contents

# 初识jQuery

9.1

# 了解什么是jQuery，能够描述jQuery的特点

先定一个小目标！

9.1.1  什么是jQuery

# 9.1.1  什么是jQuery

# jQuery具有以下6个特点。

9.1.1  什么是jQuery

代码可读性强。
语法简洁易懂，文档丰富。
支持CSS 1~CSS 3定义的属性和选择器。
支持事件、样式、动画和Ajax操作。
可跨浏览器，支持的浏览器包括IE、Firefox和Chrome等。
可扩展性强，插件丰富，可以通过插件扩展更多功能。

# 目前jQuery有3个系列的版本，分别是jQuery 1.x、jQuery 2.x和jQuery 3.x系列的版本。

它们的区别在于，jQuery 1.x系列的版本保持了对早期版本的IE浏览器的支持；jQuery 2.x系列的版本不兼容IE 6~ IE 8浏览器，从而更加轻量化；jQuery 3.x系列的版本不兼容IE 6~ IE 8浏览器，此系列的版本增加了一些新方法，并对一些方法进行了优化和改进。

9.1.1  什么是jQuery

# 掌握jQuery的下载和引入，能够独立完成jQuery的下载并且能够使用两种方式引入jQuery

先定一个小目标！

9.1.2  下载和引入jQuery

# 在学习使用jQuery之前，需要下载和引入jQuery，具体操作步骤如下。

9.1.2  下载和引入jQuery

在Chrome浏览器中访问jQuery的下载页面，如下图所示。

# 9.1.2  下载和引入jQuery

在jQuery的下载页面，单击“jQuery 3.6.4”的“minified”链接，弹出“Code Integration”对话框，如下图所示。

# 9.1.2  下载和引入jQuery

引入jQuery。引入方式有两种，第1种方式是将“Code Integration”对话框中的整个<script>标签的代码复制到页面文件中使用。整个<script>标签的具体代码如下。

<script src="https://code.jquery.com/jquery-3.6.4.min.js" integrity="sha256-oP6HI9z1XaZNBrJURtCoUT5SUnxFr8s3BzRl+cbzUq8=" crossorigin="anonymous"></script>

# 9.1.2  下载和引入jQuery

第2种方式是复制“Code Integration”对话框中的地址“https://code.jquery.com/jquery-3.6.4.min.js”，并在浏览器中访问该地址，将“jquery-3.6.4.min.js”文件保存到计算中，然后在程序中手动引入jQuery。引入jQuery的示例代码如下。

<script src="jquery-3.6.4.min.js"></script>

上述示例代码表示引入当前目录下的jQuery-3.6.4.min.js文件。

# 掌握jQuery的简单使用，能够使用jQuery实现简单的页面效果

9.1.3	jQuery的简单使用

先定一个小目标！

# 在使用jQuery时可以分为3个步骤，具体如下。

9.1.3	jQuery的简单使用

在程序中引入jQuery文件。
获取需要操作的元素。
调用操作方法，例如调用hide()方法将元素隐藏。

# 下面通过代码演示jQuery的简单使用，首先定义一个<div>标签，并使用jQuery获取元素，然后将元素在页面中隐藏，示例代码如下。

9.1.3	jQuery的简单使用

<head>
  <script src="jquery-3.6.4.min.js"></script>
</head>
<body>
  <div>Hello jQuery</div>
  <script>
    $('div').hide();    		// 隐藏div元素
  </script>
</body>

# 熟悉jQuery对象，能够区别jQuery对象和DOM对象

9.1.4	jQuery对象

先定一个小目标！

# 在页面中引入jQuery后，全局作用域下会新增两个变量，分别是$和jQuery，这两个变量引用的是同一个对象，该对象称为jQuery顶级对象。为了方便书写，通常使用$变量。
下面通过代码演示$变量和jQuery变量的使用。

// $变量的使用
$('div').hide();
// jQuery变量的使用
jQuery('div').hide();

9.1.4	jQuery对象

# 9.1.4	jQuery对象

# 9.1.4	jQuery对象

jQuery对象以类数组的形式存储，它可以包装一个或多个DOM对象。下面通过代码对比jQuery对象和DOM对象。

<body>
  <div>Hello jQuery</div>
  <script>
    // jQuery对象
    var div1 = $('div');
    console.log(div1);
    // DOM对象
    var div2 = document.getElementsByTagName('div');
    console.log(div2);
  </script>
</body>

# 9.1.4	jQuery对象

前面的示例代码运行后，jQuery对象和DOM对象的输出结果如下图所示。

# 在实际开发中，经常会在jQuery对象和DOM对象之间进行转换，由于DOM对象比jQuery对象更复杂，DOM对象的一些属性和方法在jQuery对象中没有封装，所以使用这些属性和方法时需要把jQuery对象转化为DOM对象。另外，DOM对象也可以转换为jQuery对象。

9.1.4	jQuery对象

# 9.1.4	jQuery对象

1. 将jQuery对象转换为DOM对象

将jQuery对象转换为DOM对象有两种实现方式，第1种实现方式的语法格式如下。

jQuery对象[索引]

第2种实现方式的语法格式如下。

jQuery对象.get(索引)

# 9.1.4	jQuery对象

将jQuery对象转换为DOM对象的示例代码如下。

var div1 = $('div')[0];		// 第1种实现方式
var div2 = $('div').get(0);		// 第2种实现方式

上述示例代码分别使用两种方式将jQuery对象转换为DOM对象，当jQuery对象转换为DOM对象后就可以使用DOM方式操作元素。

# 9.1.4	jQuery对象

2. 将DOM对象转换为jQuery对象

将DOM对象转换为jQuery对象的语法格式如下。

$(DOM对象)

将DOM对象转换为jQuery对象的示例代码如下。

// 获取DOM对象
var div = document.getElementByTagName('div')[0];
// 将DOM对象转换成jQuery对象
div = $(div);

# jQuery选择器

9.2

# 掌握基本选择器的使用，能够灵活应用基本选择器获取元素

9.2.1	基本选择器

先定一个小目标！

# jQuery提供了类似CSS选择器的机制，使用选择器可以很方便地获取元素，使用jQuery选择器获取元素的语法格式如下。

$(selector)

9.2.1	基本选择器

上述语法格式中，selector表示选择器。

# 下面列举jQuery中常用的基本选择器，具体如下表所示。

9.2.1	基本选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| #id | 获取指定id的元素 | $('#btn')获取id为btn的元素 |
| * | 匹配所有元素 | $('*')获取页面中的所有元素 |
| .class | 获取同一class的元素 | $('.tab')获取所有class为tab的元素 |
| element | 获取相同标签名的所有元素 | $('div')获取所有div元素 |
| selector1, selector2,… | 同时获取多个元素 | $('div,p,li')同时获取div元素、p元素和li元素 |

# 下面通过代码进行演示。

<div class="fruit">苹果</div>
<script>
  console.log($('.fruit'));
</script>

9.2.1	基本选择器

# 先定一个小目标！

9.2.2	层次选择器

掌握层次选择器的使用，能够灵活应用层次选择器获取元素

# 9.2.2	层次选择器

# 下面列举jQuery中常用的层次选择器，具体如下表所示。

9.2.2	层次选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| parent > child | 获取所有子元素 | $('ul > li')获取ul元素下的所有li子元素 |
| selector selector1 | 获取所有后代元素 | $('ul li')获取ul元素下的所有li后代元素 |
| prev + next | 获取后面紧邻的兄弟元素 | $('div + .title')获取div元素后面紧邻的class为title的兄弟元素 |
| prev ~ siblings | 获取后面的所有兄弟元素 | $('.bar ~ li')获取class为bar的元素后的所有li兄弟元素 |

# 下面通过代码进行演示。

<ul>
  <li>第1个li元素</li>
  <li>第2个li元素</li>
</ul>
<script>
   console.log($('ul li'));		// 获取ul中的li
</script>

9.2.2	层次选择器

# 先定一个小目标！

9.2.3	筛选选择器

掌握筛选选择器的使用，能够灵活应用筛选选择器获取元素

# 9.2.3	筛选选择器

# 下面列举jQuery中常用的筛选选择器，具体如下表所示。

9.2.3	筛选选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :first | 获取指定选择器中的第一个元素 | $('li:first')获取第一个li元素 |
| :last | 获取指定选择器中的最后一个元素 | $('li:last')获取最后一个li元素 |
| :eq(index) | 获取索引等于index的元素（索引从0开始） | $('li:eq(2)')获取索引为2的li元素 |
| :gt(index) | 获取索引大于index的元素 | $('li:gt(3)')获取索引大于3的所有li元素 |
| :lt(index) | 获取索引小于index的元素 | $('li:lt(3)')获取索引小于3的所有li元素 |
| :even | 获取索引为偶数的元素 | $('li:even')获取索引为偶数的li元素 |

# >>续上一页表

9.2.3	筛选选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :odd | 获取索引为奇数的元素 | $('li:odd')获取索引为奇数的li元素 |
| :not(seletor) | 获取除指定的选择器之外的其他元素 | $('li:not(li:eq(3))')获取除索引为3的li元素之外的所有li元素 |
| :focus | 获取当前获得焦点的元素 | $('input:focus')获取当前获得焦点的input元素 |
| :animated | 获取所有正在运行动画效果的元素 | $('div:animated')获取当前正在运行动画效果的div元素 |
| :target | 选择由文档URL的格式化识别码表示的目标元素 | 若URL为http://localhost/#foo，则$('div:target')将获取id为foo的div元素 |
| :contains(text) | 获取内容包含text的元素 | $('li:contains(js)')获取内容中包含js的li元素 |

# 9.2.3	筛选选择器

>>续上一页表

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :empty | 获取内容为空的元素 | $('li:empty')获取内容为空的li元素 |
| :has(selector) | 获取内容包含指定选择器的元素 | $("li:has('a')")获取内容中包含a元素的所有li元素 |
| :parent | 获取带有子元素或包含文本的元素 | $('li:parent')获取带有子元素或包含文本的li元素 |
| :hidden | 获取所有隐藏元素 | $('li:hidden')获取所有隐藏的li元素 |
| :visible | 获取所有可见元素 | $('li:visible')获取所有可见的li元素 |

# 下面通过代码进行演示。

<ul>
  <li>第1个li元素，索引为0</li>
  <li>第2个li元素，索引为1</li>
  <li>第3个li元素，索引为2</li>
</ul>
<script>
  $('ul li:first').css('color', 'red');
  $('ul li:eq(2)').css('color', 'blue');
</script>

9.2.3	筛选选择器

# 前面的示例代码运行后，使用了筛选选择器的输出结果如下图所示。

9.2.3	筛选选择器

# 先定一个小目标！

9.2.4	其他选择器

掌握其他选择器的使用，能够灵活应用其他选择器获取元素

# 9.2.4	其他选择器

# 1. 属性选择器

jQuery中提供了根据元素的属性获取指定元素的选择器，即属性选择器。
常用的属性选择器如下表所示。

9.2.4	其他选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| [attr] | 获取具有指定属性的元素 | $('div[class]')获取含有class属性的所有div元素 |
| [attr=value] | 获取属性值等于value的元素 | $('div[class=current]')获取class属性值等于current的所有div元素 |
| [attr!=value] | 获取属性值不等于value的元素 | $('div[class!=current]')获取class属性值不等于current的所有div元素 |
| [attr^=value] | 获取属性值以value开始的元素 | $('div[class^=box]')获取class属性值以box开始的所有div元素 |

# >>续上一页表

9.2.4	其他选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| [attr$=value] | 获取属性值以value结尾的元素 | $('div[class$=er]') 获取class属性值以er结尾的所有div元素 |
| [attr*=value] | 获取属性值包含value的元素 | $("div[class*='-']")获取class属性值中含有“-”符号的所有div元素 |
| [attr~=value] | 获取属性值包含value或以空格分隔并包含value的元素 | $("div[class~='box']")获取class属性值等于“box”或通过空格分隔并含有box的div元素，如“a box” |
| [attr1] [attr2]… | 获取同时拥有多个属性的元素 | $("input[id][name$='usr']")获取同时含有id属性和属性值以usr结尾的name属性的input元素 |

# 2. 子元素选择器

在开发过程中，若需要通过子元素获取元素，可以使用jQuery提供的子元素选择器。常用的子元素选择器如下表所示。

9.2.4	其他选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :nth-child(数字/even/odd/公式) | 按数字、奇数、偶数或公式获取元素 | $('ul li:nth-child(3)')获取所有ul中的第3个li元素 |
| :first-child | 获取第一个子元素 | $('ul li:first-child')获取所有ul中的第一个li元素 |
| :last-child | 获取最后一子元素 | $('ul li:last-child')获取所有ul中的最后一个li元素 |
| :only-child | 如果当前元素是父元素唯一的子元素，则获取 | $('ul li:only-child')如果当前li元素是ul唯一的子元素，则获取 |
| :nth-last-child(数字/even/odd/公式) | 按指定条件获取相同父元素中的子元素，计数从最后一个元素开始到第一个 | $('ul li:nth-last-child(2)') 获取所有ul中的最后2个li元素 |

# 9.2.4	其他选择器

>>续上一页表

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :nth-of-type(数字/even/odd/公式) | 按指定条件获取相同父元素中的同类子元素 | $('span:nth-of-type(2)')获取span类型元素中的第2个子元素 |
| :first-of-type | 获取同类元素中的第一个子元素 | $('span:first-of-type')获取span类型元素中的第一个子元素 |
| :last-of-type | 获取同类元素中的最后一个子元素 | $('span:last-of-type')获取span类型元素中的最后一个子元素 |
| :only-of-type | 获取没有兄弟元素的同类子元素 | $('span:only-of-type')获取没有兄弟元素的span类型子元素 |
| :nth-last-of-type(数字/even/odd/公式) | 按指定条件获取相同父元素下的同类子元素，计数从最后一个元素开始到第一个 | $('span:nth-last-of-type(2)')获取span类型的最后2个子元素 |

# 3. 表单选择器

在开发过程中，若需要对表单进行操作，可以使用jQuery提供的表单选择器获取表单元素。常用的表单选择器如下表所示。

9.2.4	其他选择器

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :input | 获取页面中的所有表单元素，包括select元素以及textarea元素 | $('input:input')获取页面中的所有表单元素 |
| :text | 获取所有的文本框 | $('input:text')获取所有的文本框 |
| :password | 获取所有的密码框 | $('input:password')获取所有的密码框 |
| :radio | 获取所有的单选按钮 | $('input:radio')获取所有的单选按钮 |
| :checkbox | 获取所有的复选框 | $('input:checkbox')获取所有的复选框 |

# 9.2.4	其他选择器

>>续上一页表

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :submit | 获取提交按钮 | $('input:submit')获取提交按钮 |
| :reset | 获取重置按钮 | $('input:reset')获取重置按钮 |
| :image | 获取图像域，即<input type="image"> | $('input:image')获取图像域 |
| :button | 获取所有按钮，包括<button>和<input type="button"> | $('input:button')获取所有按钮 |
| :file | 获取文件域，即<input type="file"> | $('input:file')获取文件域 |

# 9.2.4	其他选择器

>>续上一页表

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| :hidden | 获取表单隐藏项 | $('input:hidden')获取表单隐藏项 |
| :enabled | 获取所有可用表单元素 | $('input:enabled')获取所有可用表单元素 |
| :disabled | 获取所有不可用表单元素 | $('input:disabled')获取所有不可用表单元素 |
| :checked | 获取所有选中的表单元素，主要针对radio元素和checkbox元素 | $(':checked')获取所有被选中的表单元素 |
| :selected | 获取所有选中的表单元素，主要针对select元素 | $('selected')获取所有选中的表单元素 |

# jQuery内容操作

9.3

# 掌握jQuery内容操作，能够灵活应用jQuery中操作元素内容的方法

先定一个小目标！

9.3  jQuery内容操作

# 9.3  jQuery内容操作

# 下面列举jQuery中元素内容操作的方法，具体如下表所示。

9.3  jQuery内容操作

| 选择器 | 功能描述 | 示例 |
|---|---|---|
| html() | 获取第1个匹配元素的HTML内容 | html() |
| html(htmlString) | 设置所有匹配元素的HTML内容为htmlString | html(htmlString) |
| text() | 获取所有匹配元素包含的文本内容组合起来的文本 | text() |
| text(text) | 设置所有匹配元素的文本内容为text | text(text) |
| val() | 获取表单元素的value值 | val() |
| val(value) | 设置表单元素的value值 | val(value) |

# 当需要获取内容的元素是select时，val()方法的返回结果是一个包含所选值的数组；当需要为表单元素设置选中情况时，可以为val()方法传递数组参数。

9.3  jQuery内容操作

# jQuery样式操作

9.4

# 掌握css()方法的使用，能够灵活应用css()方法操作元素的样式

先定一个小目标！

9.4.1	css()方法操作元素的样式

# 9.4.1	css()方法操作元素的样式

使用jQuery提供的css()方法可以获取元素的样式和设置元素的样式。
css()方法的具体用法和说明如下表所示。

| 方法 | 说明 |
|---|---|
| css(propertyName) | 获取第一个匹配元素的样式 |
| css(propertyName,value) | 为所有匹配的元素设置样式 |
| css(properties) | 将一个键值对形式的对象properties设置为所有匹配元素的样式 |

# 9.4.1	css()方法操作元素的样式

在css()方法的参数中：
propertyName是一个字符串，表示样式属性名。
value表示样式属性值。
properties表示样式对象，如{ color: 'red' }。

需要注意的是，当css()方法接收对象作为参数时，如果属性名由两个单词组成，需要将CSS属性名中的“-”去掉，并将第2个单词首字母大写，例如，设置元素的backgroud-color样式属性时，需要将属性名修改为backgroudColor。

# 下面通过代码演示如何使用css()方法操作元素的样式。

首先定义一个<div>标签，并设置其宽度为100px，高度为100px，背景颜色为blue，然后使用css()方法将<div>标签的宽度设置为200px，高度为200px，背景颜色为pink。

9.4.1	css()方法操作元素的样式

# 先定一个小目标！

9.4.2	操作元素样式类

掌握操作元素样式类，能够灵活应用操作元素样式类的方法

# 9.4.2	操作元素样式类

在网页开发中不仅可以使用类操作元素的样式，即定义class，还可以通过jQuery操作元素样式类。下面列举操作元素样式类的方法，具体如下表所示。

| 用法 | 说明 |
|---|---|
| addClass(className) | 为每个匹配的元素追加指定类名的样式 |
| removeClass(className) | 从所有匹配的元素中删除全部或者指定的类 |
| toggleClass(className) | 判断指定类是否存在，存在则删除，不存在则添加 |

# 下面通过代码进行演示。

首先定义1个<div>标签和3个类，这3个类分别为first、second和third，再使用addClass()方法为<div>标签添加first类和second类，然后使用removeClass()方法删除<div>标签中的first类，最后使用toggleClass()方法判断<div>标签中是否存在third类，若存在则删除该类，否则添加该类。

9.4.2	操作元素样式类

# 9.4.2	操作元素样式类

操作元素样式的运行结果如下图所示。

# jQuery属性操作

9.5

# 掌握prop()方法的使用，能够应用prop()方法操作元素的属性

先定一个小目标！

9.5.1	prop()方法

# 9.5.1	prop()方法

prop()方法用于获取或设置元素的属性值，该方法的语法格式如下。

$(selector).prop(propertyName, value)

上述语法格式中，selector表示选择器，propertyName表示属性名，value表示属性值。如果只传递propertyName参数，则表示获取对应元素的属性值；如果传递了value参数，表示设置对应元素的属性值。

# 9.5.1	prop()方法

下面通过代码进行演示。

<body>
  <a href="http://localhost" title="与时俱进"></a>
  <script>
    console.log($('a').prop('href'));    // 输出结果为：http://localhost/
    $('a').prop('title', '实事求是');
  </script>
</body>

# 9.5.1	prop()方法

下面演示如何使用prop()方法获取表单元素的checked值。

<body>
  <label for="myCheckbox">选择：
    <input type="checkbox" id="myCheckbox" checked>
  </label>
  <script>
    var isChecked = $('#myCheckbox').prop('checked');
    console.log(isChecked);
  </script>
</body>

# 掌握attr()方法的使用，能够应用attr()方法获取或设置标签的属性值

先定一个小目标！

9.5.2	attr()方法

# attr()方法用于获取或设置标签的属性值，例如，给div元素添加index属性，保存元素的索引。attr()方法的语法格式如下。

$(selector).attr(propertyName, value)

上述语法格式中，selector表示选择器，propertyName表示属性名，value表示属性值。如果只传递propertyName参数，则表示获取对应标签的属性值；如果传递了value参数，表示设置对应标签的属性值。

9.5.2	attr()方法

如果只传递propertyName参数，则表示获取对应元素的属性值。

# 下面通过代码进行演示。

<body>
  <div index="1" data-index="2">div元素</div>
  <script>
    console.log($('div').attr('index'));          // 输出结果为：1
    console.log($('div').attr('data-index'));  // 输出结果为：2
    $('div').attr('index', 3);	            	         // 设置index的属性值为3
    $('div').attr('data-index', 4);     	         // 设置data-index的属性值为4
  </script>
</body>

9.5.2	attr()方法

# 掌握data()方法的使用，能够应用data()方法获取或设置数据

先定一个小目标！

9.5.3	data()方法

# data()方法用于在指定的元素上获取或设置数据，该方法的语法格式如下。

$(selector).data(name, value)

上述语法格式中，selector表示选择器，name表示数据名，value表示数据值。
如果只传递name参数，则表示获取对应元素上的数据；如果传递了value参数，表示设置对应元素上的数据。

9.5.3	data()方法

# 下面通过代码进行演示。

<body>
  <div>div元素</div>
  <script>
    $('div').data('userName', '小智');       	// 设置数据
    console.log($('div').data('userName'));	// 获取数据，输出结果为：小智
  </script>
</body>

9.5.3	data()方法

# data()方法不仅可以在指定的元素上获取或设置数据，而且可以读取HTML5自定义属性data-index，示例代码如下。

<body>
  <div index="1" data-index="2">div元素</div>
  <script>
    console.log($('div').data('index'));       // 输出结果为：2
  </script>
</body>

9.5.3	data()方法

# 本章小结

本章主要对jQuery的上半部分内容进行讲解，首先讲解了什么是jQuery、下载和引入jQuery、jQuery的简单使用和jQuery对象，然后讲解了jQuery选择器，包括基本选择器、层次选择器、筛选选择器和其他选择器，最后讲解了jQuery内容操作、样式操作和属性操作。通过本章的学习，读者能够运用jQuery开发常见的网页交互功能。

本

章

小

结