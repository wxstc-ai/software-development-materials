# 第1章 初识JavaScript

《JavaScript+jQuery交互式Web前端开发（第2版）》

# 学习目标/Target

# 学习目标/Target

# 学习目标/Target

# 章节概述/ Summary

Web前端开发必备的技术包括HTML（Hypertext Markup Language，超文本标记语言）、CSS（Cascading Style Sheets，串联样式表）和JavaScript。HTML和CSS用于创建美观且易于理解的网页布局和页面样式，但对于具有交互性和动态性的网页，JavaScript是必不可少的。因此，学习Web前端开发并实现更为复杂的交互效果和功能不仅需要掌握HTML 和 CSS 的基础知识，还需要掌握JavaScript技术。本章将介绍JavaScript基本概念、JavaScript开发工具、JavaScript基本使用和变量等内容，让读者对JavaScript有初步的认识。

# 目录/Contents

# JavaScript基本概念

1.1

# 了解JavaScript基本概念，能够描述JavaScript的用途

1.1.1	JavaScript概述

先定一个小目标！

# 1.1.1	JavaScript概述

# 在网页中，HTML、CSS和JavaScript分别代表网页的结构、样式和行为。HTML、CSS和JavaScript的说明如下表所示。

1.1.1	JavaScript概述

| 语言 | 说明 |
|---|---|
| HTML | 决定网页的结构，相当于人的身体 |
| CSS | 决定网页呈现给用户的模样，相当于人的衣服、妆容 |
| JavaScript | 实现业务逻辑和页面控制，决定网页的行为，相当于人的各种动作 |

# 利用JavaScript可以实现网页中的许多交互效果，例如轮播图、选项卡、表单验证等。

此外，利用JavaScript还可以实现网页从服务器动态获取数据，例如，用户在百度搜索引擎网站中进行搜索时，在搜索框中输入需要搜索的关键词后，网页会通过服务器智能感知用户将要搜索的内容，服务器接收到用户发出的请求后进行相应处理，并将感知结果显示到网页中。

1.1.1	JavaScript概述

# 了解JavaScript的由来，能够描述JavaScript的由来

1.1.2	JavaScript的由来

先定一个小目标！

# 1.1.2	JavaScript的由来

# 1996年，网景公司在网景导航者2.0浏览器中正式内置了JavaScript语言。其后，微软公司（Microsoft Corporation）开发了一种与JavaScript语言相近的JScript语言，内置于Internet Explorer 3.0浏览器，与网景导航者浏览器竞争。

后来，网景公司面临丧失JavaScript语言的主导权的局面，决定将JavaScript语言提交给Ecma国际（Ecma International，前身为欧洲计算机制造商协会，即European Computer Manufacturers Association，现名称并非为首字母缩略词），希望JavaScript能够成为国际标准。

1.1.2	JavaScript的由来

# Ecma国际是一个国际性会员制的信息和电信标准组织，该组织发布了ECMA-262标准文件，规定了浏览器脚本语言的标准，并将这种语言称为ECMAScript。JavaScript和JScript可以理解为ECMAScript的实现和扩展。

1.1.2	JavaScript的由来

# 1.1.2	JavaScript的由来

需要说明的是，JavaScript语言和Java语言名称比较相似，这是因为网景公司在为JavaScript命名时，考虑到该公司与Java语言的开发商Sun公司（2009年被Oracle公司收购）的合作关系。然而，JavaScript和Java只是名字相似，本质上是两种不同的语言。

# 了解JavaScript的组成，能够描述JavaScript的组成

1.1.3	JavaScript的组成

先定一个小目标！

# 1.1.3	JavaScript的组成

JavaScript是由ECMAScript、DOM、BOM这3部分组成的。JavaScript的组成部分如下图所示。

# 1.1.3	JavaScript的组成

下面对JavaScript的组成部分进行介绍。

ECMAScript：规定了JavaScript的编程语法和基础核心内容，是浏览器厂商共同遵守的一套JavaScript语法工业标准。
DOM（Document Object Model）：文档对象模型，是W3C（World Wide Web Consortium，万维网联盟）组织制定的用于处理HTML文档和XML（eXtensible Markup Language，可扩展标记语言）文档的编程接口，它提供了对文档的结构化表述，并定义了一种方式使程序可以对该结构进行访问，从而改变文档的结构、样式和行为。
BOM（Browser Object Model）：浏览器对象模型，是一套编程接口，用于对浏览器进行操作，如刷新页面、弹出警告框、控制页面跳转等。

# 了解JavaScript的特点，能够描述JavaScript的特点

1.1.4	JavaScript的特点

先定一个小目标！

# 01

02

03

1

2

3

JavaScript是脚本语言中的一种，它的语法规则比较松散，使开发人员能够快速编写程序。使用脚本语言编写的代码可以直接由解释器执行，不需要生成独立的可执行文件。由于脚本语言只在被调用时自动进行解释或编译，所以具有简单易用的特点。

简单易用

JavaScript不依赖特定的操作系统，仅需要浏览器的支持。无论用户使用的操作系统是Windows、Linux、macOS还是Android、iOS，只要这些操作系统中安装了支持JavaScript的浏览器，就可以运行JavaScript。

跨平台

面向对象是软件开发中的一种重要的编程思想。JavaScript为面向对象提供了支持，使开发者能够通过面向对象思想进行编程。许多优秀的库和框架的诞生都离不开面向对象思想。面向对象使JavaScript开发变得快捷、高效，还可以降低开发成本。

面向对象

1.1.4	JavaScript的特点

# JavaScript开发工具

1.2

# 了解浏览器，能够描述浏览器的特点以及作用

先定一个小目标！

1.2.1  浏览器

# 1.2.1  浏览器

浏览器是用户访问互联网中各种网站所必备的工具，常见的浏览器及其特点如下表所示。

| 浏览器 | 厂商 | 特点 |
|---|---|---|
| Internet Explorer | 微软公司 | Windows操作系统的内置浏览器 |
| Edge | 微软公司 | Windows 10操作系统新增的浏览器，响应速度更快、功能更多 |
| Chrome | 谷歌公司 | 目前市场占有率较高的浏览器，具有简洁、快速的特点 |
| Firefox | Mozilla公司 | 由Mozilla开发的网页浏览器，安全性高、占用系统资源小 |
| Safari | 苹果公司 | 主要应用在iOS、macOS操作系统中 |

# 1.2.1  浏览器

# 1.2.1  浏览器

在Chrome浏览器控制台中运行代码

多学一招

在Chrome浏览器的控制台中可以直接输入JavaScript代码并运行。下面演示如何在Chrome浏览器的控制台中使用alert()语句实现在页面中弹出一个警告框。其中，alert()语句是在1.3.3小节讲解的内容，此处为了演示操作，提前使用了该语句。

# 1.2.1  浏览器

多学一招

首先在Chrome浏览器中按“F12”键，或在网页的空白区域右击，并在弹出的快捷菜单中选择“检查”，启动开发者工具。然后切换到“Console”（控制台）面板，可以看到一个闪烁的光标，此时可以在控制台中输入代码。如下图所示。

# 1.2.1  浏览器

多学一招

按“Enter”键，即可看到JavaScript代码的运行结果，如下图所示。

# 1.2.1  浏览器

多学一招

另外，在控制台中还可以通过“Ctrl+鼠标滚轮”放大或缩小字体，通过“Shift+Enter”快捷键在输入的代码中换行。

# 掌握下载和安装代码编辑器的方法，能够独立下载和安装代码编辑器

先定一个小目标！

1.2.2  代码编辑器

# 1.2.2  代码编辑器

# Visual Studio Code（简称VS Code）是由微软公司推出的一款免费、开源的代码编辑器。Visual Studio Code代码编辑器具有如下特点。

1.2.2  代码编辑器

轻巧快速，占用系统资源较少。
具备代码智能补全、语法高亮显示、自定义快捷键和代码匹配等功能。
跨平台，可用于Windows、Linux和macOS操作系统。
主题界面设计人性化。例如，可以快速查找文件、分屏显示代码、自定义主题颜色、快速查看最近打开的项目文件，以及查看项目文件结构等。
提供丰富的扩展，用户可以根据需要自行下载和安装扩展，以增强代码编辑器的功能。

# 打开浏览器并访问Visual Studio Code官方网站，如下图所示。

1. 下载和安装Visual Studio Code代码编辑器

1.2.2  代码编辑器

# 在Visual Studio Code官方网站页面中，单击“Download for Windows”按钮可以下载Windows操作系统的Visual Studio Code安装包。如需下载其他操作系统的Visual Studio Code安装包，单击“    ”按钮，即可看到其他操作系统版本的下载选项，如下图所示。

1.2.2  代码编辑器

# Visual Studio Code安装包下载成功后，在下载目录中找到该安装包，双击启动安装程序，按照程序的安装向导提示操作，直到安装完成。

1.2.2  代码编辑器

# Visual Studio Code安装成功后，启动该编辑器，即可进入Visual Studio Code初始界面，如下图所示。

1.2.2  代码编辑器

# 为了提高Visual Studio Code代码编辑器的易用性，使其界面和提示信息显示为中文，需要安装中文语言扩展。单击Visual Studio Code初始界面左侧的第5个按钮“    ”，进入扩展界面，在该界面的搜索框中输入关键词“Chinese”找到中文语言扩展，单击“Install”按钮进行安装即可。

2. 安装中文语言插件

1.2.2  代码编辑器

# 安装中文语言扩展界面如下图所示。

2. 安装中文语言插件

1.2.2  代码编辑器

# 1.2.2  代码编辑器

需要说明的是，中文语言扩展安装成功后，需要重新启动Visual Studio Code代码编辑器，该扩展才会生效。

# Live Server扩展用于搭建具有实时重新加载功能的本地服务器，可以实现保存代码后浏览器自动同步刷新，即时查看网页效果。单击Visual Studio Code初始界面左侧的第5个图标按钮“    ”进入扩展界面，在该界面的搜索框中输入关键词“Live Server”找到Live Server扩展，单击“安装”按钮进行安装即可。

3. 安装Live Server扩展

1.2.2  代码编辑器

# 安装Live Server扩展界面如下图所示。

3. 安装Live Server扩展

1.2.2  代码编辑器

# 安装Live Server扩展后，可在编写好的网页文件中右击，在弹出的快捷菜单中选择“Open with Live Server”调用浏览器打开网页文件。

1.2.2  代码编辑器

# 在开发项目时，需要创建项目文件夹，以保存项目所需的文件。下面在本地创建一个文件夹Chapter01，创建好文件夹后，首先在Visual Studio Code代码编辑器的菜单栏中单击“文件”，然后单击“打开文件夹...”并选择Chapter01文件夹。打开文件夹后的界面如下图所示。

4. 创建项目文件夹

1.2.2  代码编辑器

# JavaScript基本使用

1.3

# 掌握JavaScript初体验，能够在Visual Studio Code代码编辑器中编写一段简单的JavaScript代码

先定一个小目标！

1.3.1  JavaScript初体验

# 1.3.1  JavaScript初体验

下面将通过一个案例演示如何在Visual Studio Code代码编辑器中编写一段简单的JavaScript代码。本案例的需求是打开网页时自动弹出一个警告框，警告框中的提示内容为“锲而不舍，金石可镂”。

# 编写完JavaScript代码后，按“Ctrl+S”快捷键保存代码，然后右击Visual Studio Code代码编辑器中的Example1.html文件，选择“Open with Live Server”，就会自动通过浏览器打开Example1.html文件。

1.3.1  JavaScript初体验

# 掌握JavaScript代码引入方式，能够灵活运用行内式、内部式、外部式的方式引入JavaScript代码

1.3.2  JavaScript代码引入方式

先定一个小目标！

# 1.3.2  JavaScript代码引入方式

# 行内式是将JavaScript代码作为HTML标签的属性值使用。例如，在打开网页时自动弹出一个警告框，警告框中的提示内容为“通过行内式引入JavaScript代码”，示例代码如下。

1. 行内式

1.3.2  JavaScript代码引入方式

<body onload="alert('通过行内式引入JavaScript代码');">
</body>

在上述示例代码中，<body>标签的onload属性表示页面加载事件，用于在网页打开时自动执行JavaScript代码，该属性的值为行内式JavaScript代码。

# 需要说明的是，使用行内式不适合在HTML标签中书写大量的JavaScript代码，这是因为行内式代码与HTML标签混合在一起，不利于代码维护。

1.3.2  JavaScript代码引入方式

# 内部式将JavaScript代码写在<script>标签中。<script>标签可以写在<head>标签或<body>标签中。例如，在打开网页时自动弹出一个警告框，警告框中的提示内容为“通过内部式引入JavaScript代码”，示例代码如下。

2. 内部式

1.3.2  JavaScript代码引入方式

<body>
  <script>
    alert('通过内部式引入JavaScript代码');
  </script>
</body>

# 由于通过内部式可以将多行JavaScript代码写在<script>标签中，相比于行内式，使用内部式更方便阅读代码，所以内部式是引入JavaScript代码的常用方式之一。

1.3.2  JavaScript代码引入方式

# 另外，<script>标签有一个type属性，该属性表示脚本类型。由于在HTML5中type属性的默认值为text/javascript（表示JavaScript），所以在使用HTML5时可以省略type属性。

1.3.2  JavaScript代码引入方式

# 外部式将JavaScript代码单独写在一个文件中（一般使用“.js”作为该文件的扩展名），然后在HTML中通过<script>标签引入该文件。外部式适合在JavaScript代码量较多的情况下使用。例如，创建一个test.js文件，在该文件中编写如下代码。

3. 外部式

1.3.2  JavaScript代码引入方式

alert('通过外部式引入JavaScript代码');

在HTML文件中使用外部式引入JavaScript代码，示例代码如下。

<body>
  <script src="test.js"></script>
</body>

需要注意的是，在使用外部式时，<script>标签内不可以编写JavaScript代码。

# 以上分别介绍了引入JavaScript代码的3种方式。在实际开发中，提倡结构、样式、行为的分离，即分离HTML、CSS、JavaScript这3部分代码，这样可以提高代码的可读性和可维护性。当需要编写大量的、逻辑复杂的、具有特定功能的JavaScript代码时，推荐使用外部式。

1.3.2  JavaScript代码引入方式

# 01

02

03

1

2

3

使用外部式JavaScript代码存在于独立文件中，有利于修改和维护，而使用内部式会导致HTML代码与JavaScript代码混合在一起。

使用外部式可以通过浏览器缓存提高响应速度。例如，在多个页面中引入相同的JavaScript文件时，打开第1个页面后，浏览器会将JavaScript文件缓存下来，下次打开其他页面时就不用重新下载该文件。

使用外部式有利于HTML页面代码结构化，可以把大量的JavaScript代码分离到HTML页面外，这样既美观，又方便文件级别的代码复用。

1.3.2  JavaScript代码引入方式

外部式相比内部式，具有以下3点优势。

# 另外，浏览器运行 JavaScript 代码时，无论使用的是内部式还是外部式，页面的加载和渲染都会暂停，等待脚本执行完成后才会继续。为了尽可能减少对整个页面的影响，推荐将不需要提前运行的JavaScript代码所在的<script>标签放在HTML文档的底部。

1.3.2  JavaScript代码引入方式

# JavaScript异步加载

多学一招

使用外部式时，为了减少JavaScript加载过程对页面造成的影响，可以使用HTML5为<script>标签新增的两个可选属性async和defer，实现异步加载。实现异步加载后，即使JavaScript文件下载失败，也不会阻塞后面的JavaScript代码运行。async属性用于异步加载，即先下载文件，不阻塞其他代码运行，下载完成后再运行，示例代码如下。

1.3.2  JavaScript代码引入方式

<script src="file.js" async></script>

defer属性用于延后执行，即先下载文件，不阻塞其他代码运行，直到网页加载完成后再运行，示例代码如下。

<script src="file.js" defer></script>

# 掌握JavaScript常用的输入输出语句，能够灵活运用prompt()、alert()、document.write()、console.log()语句

1.3.3	JavaScript常用的输入输出语句

先定一个小目标！

# 在实际开发中，为了方便数据的输入和输出，JavaScript提供了输入输出语句。
常用的输入输出语句如下表所示。

1.3.3	JavaScript常用的输入输出语句

| 类型 | 语句 | 作用 |
|---|---|---|
| 输入 | prompt() | 在网页中弹出输入框 |
| 输出 | alert() | 在网页中弹出警告框 |
|  | document.write() | 在网页中输出内容 |
|  | console.log() | 在控制台中输出内容 |

# 使用prompt()语句实现在网页中弹出一个带有提示信息的输入框，示例代码如下。

1.3.3	JavaScript常用的输入输出语句

1. prompt()语句

prompt('请输入手机号：');

# 使用alert()语句实现在网页中弹出一个警告框，示例代码如下。

1.3.3	JavaScript常用的输入输出语句

2. alert()语句

alert('这是一个警告框');

# 使用document.write()语句时，如果输出内容中含有HTML标签，则输出内容会被浏览器解析。下面使用document.write()语句在页面中输出“谁知盘中餐，粒粒皆辛苦。”，示例代码如下。

1.3.3	JavaScript常用的输入输出语句

3. document.write()语句

document.write('谁知盘中餐，粒粒皆辛苦。');

# 使用console.log()语句在控制台中输出“一年之计在于春，一日之计在于晨。”，示例代码如下。

1.3.3	JavaScript常用的输入输出语句

4. console.log()语句

console.log('一年之计在于春，一日之计在于晨。');

# 如果输出的内容中包含JavaScript结束标签，则会导致代码提前结束。若要解决这个问题，需要使用“\”对结束标签的“/”进行转义，即使用“<\/script>”，示例代码如下。

1.3.3	JavaScript常用的输入输出语句

输出内容包含JavaScript结束标签的情况

脚下留心

document.write('<script>alert(1);<\/script>');

运行上述示例代码后，页面中会弹出一个警告框。如果没有使用“\”对结束标签进行转义，则</script>会被当成结束标签，使得页面不会弹出警告框，程序会报错。

# 掌握JavaScript注释的使用，能够合理运用单行注释、多行注释增强代码的可读性

先定一个小目标！

1.3.4	JavaScript注释

# 1.3.4	JavaScript注释

# 单行注释以“//”开始，到该行结束之前的内容都是注释。
下面通过代码演示单行注释的使用。

1. 单行注释

prompt('请输入用户名：');	      //  提示用户输入用户名

上述示例代码中，“//”和后面的“提示用户输入用户名”是一条单行注释，运行代码后这部分内容不会在页面中显示。

1.3.4	JavaScript注释

# 多行注释以“/*”开始，以“*/”结束。在多行注释中可以嵌套单行注释，但不可以嵌套多行注释。下面通过代码演示多行注释的使用。

2. 多行注释

/*
  prompt('请输入用户名：'); 
*/

1.3.4	JavaScript注释

上述示例代码中，从“/*”开始到“*/”结束的内容就是多行注释。

# 在Visual Studio Code代码编辑器中，可以使用快捷键对当前选中的行添加注释或取消注释，单行注释使用快捷键“Ctrl+/”，多行注释使用快捷键“Shift+Alt+A”。

1.3.4	JavaScript注释

# 变量

1.4

# 了解什么是变量，能够描述变量的概念

1.4.1	什么是变量

先定一个小目标！

# 1.4.1	什么是变量

# 1.4.1	什么是变量

假设把内存想象成一列火车，变量相当于火车的车厢，变量名相当于火车座车厢的座位号，变量值相当于乘客。乘务员通过火车车厢的座位号就可以找到对应的乘客。例如，程序在内存中保存名为seat01、seat02和seat03的3个变量，变量值分别为小明、小智和小华，如下图所示。

# 掌握变量的命名规则，能够根据变量的命名规则为变量命名

1.4.2	变量的命名规则

先定一个小目标！

# 1.4.2	变量的命名规则

# 1.4.2	变量的命名规则

JavaScript中变量的命名规则如下。

不能以数字开头，且不能包含+、-等运算符，如01user、02-user是非法的变量名。
严格区分大小写，如apple和Apple是两个不相同的变量名。
不能使用JavaScript中的关键字命名。关键字是指在JavaScript中被事先定义并赋予特殊含义的单词，如if、this就是JavaScript中的关键字。

# 1.4.2	变量的命名规则

为了提高代码的可读性，在对变量命名时应遵循以下建议。

使用字母、下画线或美元符号（$）命名，如score、set_name、$a、user01。
尽量做到“见其名知其义”，如age表示年龄、sex表示性别、num表示数字等。
用下画线分隔多个单词，如show_message；或采用驼峰命名法，变量的第1个单词首字母小写，后面的单词首字母大写，如leftHand、myFirstName等。

# 需要说明的是，只要程序不报错，其他字符（如中文字符）也能作为变量名使用，但是不推荐这种命名方式。

1.4.2	变量的命名规则

# JavaScript中常见的关键字

多学一招

在JavaScript中，关键字分为保留关键字和未来保留关键字。保留关键字是指目前已经生效的关键字。常见的保留关键字如下表所示。

1.4.2	变量的命名规则

| break | case | catch | class | const | continue |
|---|---|---|---|---|---|
| debugger | default | delete | do | else | export |
| extends | finally | for | function | if | import |
| in | instanceof | new | return | super | switch |
| this | throw | try | typeof | var | void |
| while | with | yield | enum | let | — |

# 多学一招

未来保留关键字是指ECMAScript规范中预留的关键字，目前它们没有特殊的作用，但是在未来的某个时间可能会具有一定的作用。未来保留关键字如下表所示。

1.4.2	变量的命名规则

在命名变量时，不建议使用上表中列举的未来保留关键字，以免未来它们转换为保留关键字时程序出错。

| implements | package | public |
|---|---|---|
| interface | private | static |
| protected | — | — |

# 掌握变量的声明与赋值，能够声明变量并为其赋值

1.4.3	变量的声明与赋值

先定一个小目标！

# 1.4.3	变量的声明与赋值

# JavaScript中通常使用var关键字声明变量，声明变量后，变量值默认会被设定为undefined，表示未定义。如果需要使用变量保存具体的值就需要在声明变量后为其赋值。先声明变量后赋值的示例代码如下。

1. 先声明变量后赋值

// 声明变量
var username;             	// 声明一个名称为username的变量
var age, sex, height;    	// 同时声明3个变量
// 为变量赋值
username = '小智';        	// 为变量赋值'小智'
age = 20;                 	// 为变量赋值20
sex = '男';               	// 为变量赋值'男'
height = 180;                       // 为变量赋值180

1.4.3	变量的声明与赋值

# 当变量的值是数字型数据时，不需要将其写在单引号中，如果将数字型数据写到单引号中，则表示该数据为字符串型数据，而不是数字型数据。

如果想要查看变量的值，则可以使用console.log()语句将变量的值输出到控制台。

console.log(username);	   	// 输出变量username的值
console.log(age);		// 输出变量age的值
console.log(sex);		// 输出变量sex的值
console.log(height); 	   	// 输出变量height的值

1.4.3	变量的声明与赋值

# 1.4.3	变量的声明与赋值

# 1.4.3	变量的声明与赋值

# 在声明变量的同时为变量赋值，这个过程又称为定义变量或初始化变量，示例代码如下。

2. 声明变量的同时并赋值

var username = '小智';	// 声明username变量并赋值为'小智'
var age = 20;		// 声明age变量并赋值为20
var sex = '男';		// 声明sex变量并赋值为'男'
var height = 180;             // 声明height变量并赋值为180

1.4.3	变量的声明与赋值

# 使用变量的语法细节

多学一招

在JavaScript中使用变量时，还有一些语法细节，具体介绍如下。

1.4.3	变量的声明与赋值

（1）更新变量的值
当声明一个变量并赋值后，如果重新为该变量赋值，则原来的值会被覆盖，示例代码如下。

var age = 20;
console.log(age);	// 输出结果为：20
age = 22;		// 更新变量的值
console.log(age);	// 输出结果为：22

# 多学一招

1.4.3	变量的声明与赋值

（2）同时声明多个变量
在 var 关键字后面可以同时声明多个变量，多个变量名之间使用英文逗号隔开，示例代码如下。

// 同时声明多个变量，没有赋值
var username, password, phone;
// 同时声明多个变量，并赋值
var username = '小智', password = '123456', phone = '13012345678';

如果只声明变量没有赋值，则输出结果为undefined。如果不声明变量，直接输出变量的值，则程序会报错。

# 掌握使用变量保存商品信息的案例，能够编写代码实现案例

1.4.4	【案例】使用变量保存商品信息

先定一个小目标！

# 下面将通过一个案例演示如何使用变量保存商品信息。其中，商品名称为衬衫，商品颜色为白色，商品价格为50，商品尺寸为均码。

1.4.4	【案例】使用变量保存商品信息

# 掌握使用变量保存用户输入的值的案例，能够编写代码实现案例

1.4.5	【案例】使用变量保存用户输入的值

先定一个小目标！

# 在前面的小节中讲解了使用prompt()语句可以在页面中弹出一个输入框，提示用户输入内容。当用户输入内容后，使用变量就可以保存用户输入的内容。

下面演示如何使用变量保存用户输入的值。声明一个email变量，当用户打开页面时提示用户输入邮箱，用户输入邮箱并单击“确定”按钮后，页面将显示用户的邮箱。

1.4.5	【案例】使用变量保存用户输入的值

# 如果在页面中输入“123456@qq.com”并单击“确定”按钮后，
页面的显示信息如下图所示。

1.4.5	【案例】使用变量保存用户输入的值

# 掌握交换两个变量的值的案例，能够编写代码实现案例

1.4.6	【案例】交换两个变量的值

先定一个小目标！

# 学习了JavaScript的变量后，下面通过一个案例来练习变量的使用。本案例将实现交换两个变量的值。

首先定义两个变量apple1和apple2，其中，变量apple1的值为红苹果，变量apple2的值为青苹果，然后定义第3个变量temp来保存临时数据，用于实现红苹果和青苹果的交换。

1.4.6	【案例】交换两个变量的值

# 在实现红苹果和青苹果交换的过程中，我们可以想象成左手拿着红苹果（apple1），右手拿着青苹果（apple2），前面有一张桌子（temp）。为了将左手的红苹果和右手的青苹果交换，首先需要将左手的红苹果放到桌子上，然后将右手的青苹果给左手，最后右手再从桌子上拿起红苹果，这样就完成了交换。

下面编写代码实现红苹果和青苹果的交换。

1.4.6	【案例】交换两个变量的值

# 1.4.6	【案例】交换两个变量的值

# 本章小结

本章首先介绍了JavaScript基本概念，包括JavaScript概述，JavaScript的由来、组成和特点，其次介绍了JavaScript开发工具的相关内容，然后讲解了JavaScript基本使用，包括JavaScript代码引入方式、常用的输入输出语句及注释，最后讲解了变量，包括变量的概念、命名规则、声明与赋值，并通过案例演示变量的基本使用。

本

章

小

结