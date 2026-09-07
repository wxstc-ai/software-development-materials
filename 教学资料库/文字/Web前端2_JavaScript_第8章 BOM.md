# 第8章 BOM

《JavaScript+jQuery交互式Web前端开发（第2版）》

# 学习目标/Target

# 章节概述/ Summary

在实际开发中，使用JavaScript开发网页交互效果时，经常需要获取浏览器的一些信息，控制浏览器的刷新和页面跳转。为了使JavaScript控制浏览器，可以使用BOM。本章将详细讲解BOM。

# 目录/Contents

# BOM简介

8.1

# 了解BOM的概念，能够阐述BOM的概念

先定一个小目标！

8.1  BOM简介

# 8.1  BOM简介

BOM（Browser Object Model，浏览器对象模型）是由浏览器提供的一系列对象构成的，它主要用于管理窗口与窗口之间的通信。在BOM中，顶级对象是window，表示浏览器窗口，其他对象都是window对象的属性，当调用window对象下的属性和方法时，可以省略window。常见的BOM对象如下图所示。

# 以下5个BOM对象都是window对象的属性。
document对象表示文档，它既属于BOM又属于DOM。
location对象用于操作浏览器地址。
navigator对象用于获取浏览器的基本信息。
history对象用于操作浏览器的历史记录。
screen对象用于获取屏幕信息。

BOM没有统一标准，每个浏览器都有对BOM的实现方式，因此，BOM的浏览器兼容性较差。

8.1  BOM简介

# BOM对象

8.2

# 掌握window对象的使用，能够灵活应用window对象常用的方法和属性

8.2.1	window对象

先定一个小目标！

# 8.2.1	window对象

# 在JavaScript中，定义在全局作用域中的变量是window对象的属性；定义在全局作用域中的函数是window对象的方法，示例代码如下。

// 全局作用域中的变量是window对象的属性
var num = 10;
console.log(window.num);      // 输出结果为：10
// 全局作用域中的函数是window对象的方法
function fn() {
  return 11;
}
console.log(window.fn());     // 输出结果为：11

8.2.1	window对象

# 下面列举window对象常用的方法和属性，如下表所示。

8.2.1	window对象

| 分类 | 名称 | 说明 |
|---|---|---|
| 方法 | alert() | 弹出带有一段消息和一个“确定”按钮的警告框 |
|  | confirm() | 弹出带有一段消息以及“确定”按钮和“取消”按钮的警告框 |
|  | prompt() | 弹出带有提示信息的输入框 |
|  | open() | 打开一个新的浏览器窗口或查找一个已命名的窗口 |
|  | close() | 关闭浏览器窗口 |
|  | focus() | 使窗口获得焦点 |
|  | scrollBy() | 按照指定的像素值来滚动内容 |
|  | scrollTo() | 把内容滚动到指定的坐标 |

# >>续上一页表

8.2.1	window对象

| 分类 | 名称 | 说明 |
|---|---|---|
| 属性 | name | 设置或获取窗口的名称 |
|  | opener | 获取打开当前窗口的window对象 |
|  | parent | 获取当前窗口的父窗口的window对象 |
|  | self | 获取当前窗口的window对象，等价于window对象 |
|  | window | 获取当前窗口的window对象 |
|  | top | 获取顶层窗口的window对象（页面中有多个框架时） |

# 下面通过代码演示window对象中alert()方法和confirm()方法的使用，示例代码如下。

if (confirm('您确定要运行此操作？')) {
  alert('用户确认');
} else {
  alert('用户取消');
}

8.2.1	window对象

上述示例代码中，confirm()方法用于弹出一个具有提示信息的对话框，返回值为true或false，表示用户单击了对话框中的“确定”按钮或“取消”按钮。

# 掌握location对象的使用，能够灵活应用location对象常用的方法和属性

先定一个小目标！

8.2.2	location对象

# 8.2.2	location对象

# 下面列举location对象常用的方法和属性，如下表所示。

8.2.2	location对象

| 分类 | 名称 | 说明 |
|---|---|---|
| 方法 | assign(url) | 触发窗口加载并显示指定URL的内容 |
|  | replace(url) | 使用给定的URL替换当前的资源 |
|  | reload([forcedReload]) | 刷新当前页面 |
| 属性 | search | 获取或设置当前URL的查询字符串（又称为URL参数），即URL中“?”之后的内容 |
|  | hash | 获取当前URL的锚点部分（从“#”开始的部分） |

# >>续上一页表

8.2.2	location对象

| 分类 | 名称 | 说明 |
|---|---|---|
| 属性 | host | 获取当前URL的主机名和端口 |
|  | hostname | 获取当前URL的主机名 |
|  | href | 获取当前URL |
|  | pathname | 获取当前URL中的路径名 |
|  | port | 获取当前URL中的端口号 |
|  | protocol | 获取当前URL中的协议 |

# reload()方法的可选参数forcedReload是一个布尔值，当值为true时，表示强制浏览器从服务器加载页面资源，当值为false或未传参时，浏览器则可能从缓存中读取页面。

search属性通常用于在向服务器查询信息时传入查询条件，如页码、搜索的关键字、排序方式等。

assign()方法在打开指定URL时，会生成一条新的历史记录，而replace()方法不会在浏览器历史记录中生成新的记录，并且在调用replace()方法后，用户不能返回到前一个页面。

8.2.2	location对象

# 下面以如下URL为例，演示location对象常用的属性的使用。

8.2.2	location对象

http://127.0.0.1:5500/test.html?name=a#data

在浏览器打开上述URL时，使用location对象常用的属性的示例代码如下。

console.log(location.search);          	// 输出结果为：?name=a
console.log(location.hash);            	// 输出结果为：#data
console.log(location.host);               	// 输出结果为：127.0.0.1:5500
console.log(location.hostname);	// 输出结果为：127.0.0.1
console.log(location.href);               	// 输出结果为: http://127.0.0.1:5500/test.html
console.log(location.pathname);      	// 输出结果为：/test.html
console.log(location.port);                	// 输出结果为：5500
console.log(location.protocol);         	// 输出结果为：http:

# 掌握navigator对象的使用，能够灵活应用navigator对象常用的方法和属性

先定一个小目标！

8.2.3	navigator对象

# navigator对象用于获取浏览器的相关信息，下面列举navigator对象常用的方法和属性，如下表所示。

8.2.3	navigator对象

| 分类 | 名称 | 说明 |
|---|---|---|
| 方法 | javaEnable() | 是否在浏览器中启动Java |
| 属性 | appCodeName | 获取浏览器的内部名称 |
|  | appName | 获取浏览器的完整名称 |
|  | appVersion | 获取浏览器的平台和版本信息 |
|  | cookieEnable | 浏览器中是否启用Cookie |
|  | platform | 获取运行浏览器的操作系统平台 |
|  | userAgent | 获取由浏览器发送到服务器的User-Agent的值 |

# 下面以userAgent属性为例，演示如何获取由浏览器发送到服务器的User-Agent的值。

8.2.3	navigator对象

var msg = navigator.userAgent;
console.log(msg);

在上述示例代码中，使用navigator对象的userAgent属性获取由浏览器发送到服务器的User-Agent的值，其内容主要包含浏览器版本、操作系统等信息，每种浏览器获取的信息都不相同。

# 下面以Chrome浏览器、Firefox浏览器、IE浏览器为例演示浏览器获取的信息。

8.2.3	navigator对象

Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36

Chrome浏览器的输出结果示例如下。

Firefox浏览器的输出结果示例如下。

Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/111.0

IE浏览器的输出结果示例如下。

Mozilla/5.0 (Windows NT 10.0; WOW64; Trident/7.0; .NET4.0C; .NET4.0E; rv:11.0) like Gecko

# 掌握history对象的使用，能够灵活应用navigator对象常用的方法和属性

先定一个小目标！

8.2.4	history对象

# 8.2.4	history对象

# 8.2.4	history对象

下面列举history对象常用的方法和属性，如下表所示。

| 分类 | 名称 | 说明 |
|---|---|---|
| 方法 | back() | 加载history列表中的上一个URL，即后退一页 |
|  | forward() | 加载history列表中的下一个URL，即前进一页 |
|  | go([delta]) | 加载history列表中的某个具体页面，可选参数delta的值是负整数时，表示后退指定的页数；是正整数时，表示前进指定的页数；是0或省略时，表示刷新页面 |
| 属性 | length | 返回history列表中的URL数 |

# 8.2.4	history对象

下面通过代码演示history对象的back()方法和forward()方法，示例代码如下。

<body>
  <button id="btn1">后退</button>
  <button id="btn2">前进</button>
  <script>
    var btn1 = document.getElementById('btn1');
    var btn2 = document.getElementById('btn2');
    btn1.onclick = function () {
      history.back();		// 控制浏览器后退一页
    };
   btn2.onclick = function () {
      history.forward();	// 控制浏览器前进一页
    };
  </script>
</body>

# 掌握screen对象的使用，能够灵活应用screen对象常用的方法和属性

先定一个小目标！

8.2.5	screen对象

# screen对象用于获取屏幕相关的信息，例如，屏幕的宽度、屏幕的高度等。下面列举screen对象常用的属性，如下表所示。

8.2.5	screen对象

上述表中的属性的获取结果都是数字型像素值。

| 属性 | 作用 |
|---|---|
| width | 获取整个屏幕的宽度 |
| height | 获取整个屏幕的高度 |
| availWidth | 获取浏览器窗口在屏幕上可占用的水平空间 |
| availHeight | 获取浏览器窗口在屏幕上可占用的垂直空间 |

# 下面通过代码进行演示。

8.2.5	screen对象

console.log(screen.width);          	// 输出结果为：1920
console.log(screen.height);         	// 输出结果为：1080
console.log(screen.availWidth);      	// 输出结果为：1920
console.log(screen.availHeight);     	// 输出结果为：1040

# 窗口事件

8.3

# 掌握窗口加载与卸载事件，能够在窗口加载、窗口卸载时运行特定的代码

先定一个小目标！

8.3.1	窗口加载与卸载事件

# 当需要在窗口加载完成后运行某些代码，或在窗口关闭时运行某些代码，可以使用window对象提供的窗口加载与卸载事件。
下面列举window对象提供的窗口加载与卸载事件，如下表所示。

8.3.1	窗口加载与卸载事件

窗口加载事件在网页文档以及外链的文件（包括图像文件、JavaScript文件、CSS文件等）全部加载完成后才会触发；窗口卸载事件会在用户关闭网页时触发。

| 属性 | 作用 |
|---|---|
| load | 窗口加载事件，当页面加载完毕后触发 |
| unload | 窗口卸载事件，当页面关闭时触发 |

# 窗口加载与卸载事件有两种注册方式，第1种注册方式的示例代码如下。

8.3.1	窗口加载与卸载事件

window.onload = function () {};	// 窗口加载事件
window.onunload = function () {};	// 窗口卸载事件

在上述示例代码中，只能注册一个事件处理函数。

# 窗口加载与卸载事件的第2种注册方式的示例代码如下。

8.3.1	窗口加载与卸载事件

window.addEventListener('load', function () {});     // 窗口加载事件
window.addEventListener('unload', function () {}); // 窗口卸载事件

在上述示例代码中，当多次调用window.addEventListener()时，可以注册多个事件处理函数。

# 下面通过代码进行演示。首先演示不使用窗口加载事件时代码运行出错的情况。由于程序中的代码是从上往下运行的，当JavaScript代码写在需要操作的HTML标签前面时，获取元素的操作会失败，示例代码如下。

8.3.1	窗口加载与卸载事件

<body>
  <script>
    document.getElementById('demo').onclick = function () {
      console.log('被单击了');
    };
  </script>
  <div id="demo">持之以恒</div>
</body>

# 保存代码，在浏览器中进行测试，运行结果如下图所示。

8.3.1	窗口加载与卸载事件

# 下面通过窗口加载事件解决示例代码中出现的问题。

8.3.1	窗口加载与卸载事件

<script>
  window.onload = function () {
    document.getElementById('demo').onclick = function () {
     console.log('被单击了');
    };
  };
</script>

# document.DOMContentLoaded事件

多学一招

当网页中的图片较多时，如果图片加载速度慢，窗口加载事件的触发可能需要较长的时间，这样会影响到用户的体验，此时，可以使用document.DOMContentLoaded事件，该事件会在文档加载完成时触发，与图片文件、JavaScript文件、CSS文件等外部文件是否加载完成无关，适用于页面中有很多外部文件的情况。

8.3.1	窗口加载与卸载事件

注意

document.DOMContentLoaded事件不兼容IE 9之前的浏览器。

# 先定一个小目标！

8.3.2	窗口大小改变事件

掌握窗口大小改变事件，能够灵活应用两种方式注册窗口大小改变事件

# 在实际开发中，为了能够响应用户调整浏览器窗口大小的操作，可以使用窗口大小改变事件resize，该事件有两种注册方式，第1种注册方式的示例代码如下。

8.3.2	窗口大小改变事件

window.onresize = function () {};

第2种注册方式的示例代码如下。

window.addEventListener ('resize', function () {});

# 下面通过代码进行演示。要求当用户调整窗口大小时，在控制台输出当前页面的宽度。

8.3.2	窗口大小改变事件

<script>
  window.addEventListener ('resize', function () {
    console.log(document.body.clientWidth);
  });
</script>

# 定时器

8.4

# 掌握定时器方法的使用，能够应用定时器延迟一段时间运行代码或间歇运行代码

先定一个小目标！

8.4.1	设置定时器方法

# window对象提供了两种用于设置定时器的方法，分别是setTimeout()方法和setInterval()方法，此外，还提供了两种用于清除定时器的方法，分别是clearTimeout()方法和clearInterval()方法。关于设置和清除定时器的方法说明如下。

8.4.1	设置定时器方法

| 方法 | 说明 |
|---|---|
| setTimeout(fn, delay) | 在达到指定时间（以毫秒计）后调用函数或运行一段代码 |
| setInterval(fn, delay) | 按照指定的周期（以毫秒计）来调用函数或运行一段代码 |
| clearTimeout(定时器ID) | 清除由setTimeout()方法设置的定时器 |
| clearInterval(定时器ID) | 清除由setInterval()方法设置的定时器 |

# 8.4.1	设置定时器方法

# 8.4.1	设置定时器方法

setTimeout()方法和setInterval()方法都有两个参数，第1个参数fn表示到达延迟时间后运行的代码，可以传入普通函数、匿名函数或字符串代码，第2个参数delay表示延迟时间的毫秒值。

# 8.4.1	设置定时器方法

setTimeout()方法和setInterval()方法的返回值为定时器ID（定时器的唯一标识），将定时器ID作为参数传给clearTimeout()方法或clearInterval()方法可以清除定时器。

# 8.4.1	设置定时器方法

下面以setTimeout()方法为例，演示使用3种传参方式实现定时器的设置。

（1）传入普通函数的方式

setTimeout(fn, 2000);
function fn() {
  alert('争分夺秒');
}

# 8.4.1	设置定时器方法

（2）传入匿名函数的方式

setTimeout(function () {
  alert('争分夺秒');
}, 2000);

（3）传入字符串代码的方式

setTimeout('alert("争分夺秒");', 2000);

# 8.4.1	设置定时器方法

// 设置定时器时保存定时器ID
var timer = setTimeout(function () {
  alert('争分夺秒');
}, 2000);
// 清除定时器时传入需要清除的定时器ID
clearTimeout(timer);

下面以clearTimeout()方法为例，演示定时器的清除，示例代码如下。

# 掌握3秒后自动关闭广告的案例，能够编写代码实现案例

先定一个小目标！

8.4.2	【案例】3秒后自动关闭广告

# 在浏览网站的过程中，经常会在页面中看到广告，并显示自动关闭广告的倒计时。自动关闭广告的倒计时效果可以使用定时器实现。

下面将通过一个案例演示如何实现3秒后自动关闭广告。

8.4.2	【案例】3秒后自动关闭广告

# 掌握60秒内只能发送一次验证码的案例，能够编写代码实现案例

先定一个小目标！

8.4.3	【案例】60秒内只能发送一次验证码

# 本案例要求在页面中设置一个文本框和一个“发送验证码”按钮，在单击“发送验证码”按钮后，该按钮中的文字会变为“60秒后重新发送”，并且“60”会每秒减1。在60秒后，才能再次单击“发送验证码”按钮，并且按钮恢复为初始状态。

8.4.3	【案例】60秒内只能发送一次验证码

# 同步和异步

8.5

# 熟悉同步和异步的概念，能够区分同步和异步

先定一个小目标！

8.5  同步和异步

# 8.5  同步和异步

# 异步是指在处理一个任务的同时，可以去处理其他的任务。例如，在煮饭的同时去炒菜。异步代码通常写在回调函数中，例如，注册事件时传入的事件处理函数，以及设置定时器时传入的函数，都是回调函数。

8.5  同步和异步

# JavaScript的运行机制是单线程，即同一个时间只能做一件事。假设JavaScript被设计为多线程，一个线程在某个DOM节点上添加内容，另一个线程要删除这个节点，此种情况下浏览器将无法确定以哪个线程为准。多线程会让JavaScript变得复杂，而采用单线程可以避免出现这样的问题。

8.5  同步和异步

# 采用单线程意味着所有任务需要排队，前一个任务结束，才会运行后一个任务，如果其中一个任务运行的时间过长，就会阻塞后面的任务。

例如，有3个任务正在排队，第1个任务是在控制台输出1，第2个任务是3秒后在控制台输出2，第3个任务是在控制台输出3。当程序运行到第2个任务时，程序就会被阻塞3秒，3秒后才能运行第3个任务。

8.5  同步和异步

# 若想要解决程序中的阻塞问题，可以使用定时器，例如，使用setTimeout()方法设置一个3秒的定时器，将第2个任务放到定时器函数中即可，示例代码如下。

8.5  同步和异步

console.log(1);       		// 第1个任务
setTimeout(function () {
  console.log(2);     		// 第2个任务
}, 3000);
console.log(3);       		// 第3个任务

# JavaScript运行机制

多学一招

首先思考一个问题：当定时器的时间设为0时，程序是优先运行定时器传入的回调函数还是优先运行setTimeout()方法后面的代码呢？示例代码如下。

8.5  同步和异步

console.log(1);
setTimeout(function () {
  console.log(2);
}, 0);
for (var i = 0, str = ''; i < 900000; i++) {
  str += i;       		// 使用字符串拼接运算延迟运行时间
}
console.log(3);		// 输出结果为：1 3 2

# 多学一招

由于JavaScript中同步任务都是放在主线程的运行栈中优先运行的，而异步任务（回调函数中代码）则被放在任务队列中等待运行，所以出现前面示例代码运行后的结果。
下面演示运行栈和任务队列的区别，如下图所示。

8.5  同步和异步

# 多学一招

一旦运行栈中的所有同步任务运行完毕，系统就会按次序读取任务队列中的异步任务，被读取的异步任务就会进入运行栈开始运行。JavaScript的主线程会不断地从任务队列里重复获取任务、运行任务，这种机制被称为事件循环。

8.5  同步和异步

# 本章小结

本章主要讲解了BOM的相关知识，首先讲解了BOM的基本概念，其次讲解了BOM对象，包括window对象、location对象、navigator对象、history对象和screen对象，然后讲解了窗口事件，包括窗口加载与卸载事件、窗口大小改变事件，最后讲解了定时器、同步和异步。通过本章的学习，读者能够使用BOM完成一些常见的页面交互效果。

本

章

小

结