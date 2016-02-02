---
layout: default
title: JavaScript笔记
---

[TOC]
# JavaScript笔记
JavaScript是Web的编程语言。
Web开发必学3门语言:
1.  HTML定义网页内容、结构；
2.  CSS描述了网页的布局、样式；
3.  JavaScript定义网页的行为。
***************************
#####JavaScript 简介
JavaScript是一种轻量级的编程语言；
JavaScript是可插入HTML页面的编程代码；
JavaScript插入HTML页面后，可有所有的现代浏览器执行。

*JavaScript直接写入HTML输出流:*

    document.write("<h1>这是一个标题</h1>");
    document.write("<p>这是一个段落</p>");
**您只能在HTML输出中使用document.write，如果您在文档加载后使用该方法，会覆盖整个文档。**
*JavaScript对事件的反应*

  <button type="button" onclick="alert("欢迎!")">按钮</button>
*JavaScript改变HTML内容*

  <script>
      function myFunction()
        {
          x=document.getElementById("demo");  //找到元素
            x.innerHTML="Hello JavaScript"  //改变内容
        }
    </script>
**document.getElementById()是由HTML DOM中定义的，DOM(Document Object Model)(文档对象模型)是用于访问HTML元素的正式W3C标准**
*JavaScript改变HTML图像*

  <script>
      function changeImage()
        {
          element=document.getElementById("myimage")
            if(element.src.match("bulbon"))
            {
              element.src="/images/pic_bulboff.gif";
            }
            else
            {
              element.src="/images/pic_bulbon.gif";
            }
        }
    </script>
    <img id="myimage" onclick="changeImage()" src="/images/pic_bulboff.gif" width="100" height="180" />
*JavaScript改变HTML样式*
本质上就是改变HTML元素的属性

  x=document.getElementById("demo");
    x.style.color="#ff0000";
*JavaScript:验证输入*

  <script>
    function myFunction()
    {
      var x=document.getElementById("demo").value;
        if(x==""||isNaN(x))
        {
          alert("不是数字");
        }
    }
    </script>
    <button type="button" onclick="myFunction()">点击这里</button>
_____________________________
#####JavaScript 用法
HTML中的脚本必须位于`<script>`与`</script>`标签之间。脚本可被放置在`<body>`和`<head>`部分中。
*`<script>`标签*
**一些老旧的实例可能会在`<script>`标签中使用type="text/javascript"。现在已经不必这样做了。JavaScript是所有现代浏览器以及HTML5中的默认脚本语言**
*`<body>`中的JavaScript*
*JavaScript函数和事件*
通常的做法是把函数放入`<head>`部分或者页面底部，这样就可以把它们安置到同一处位置，不会干扰页面的内容。
*外部的JavaScript*
可以把脚本保存到外部文件中，外部文件通常包含被多个网页使用的代码。
外部JavaScript文件的文件扩展名是.js。
如需使用外部文件，请在`<script>`标签的"src"属性中设置该.js文件，如:

  <!DOCTYPE html>
    <html>
      <body>
          <script src="myScript.js"></script>
        </body>
    </html>
_____________________
#####JavaScript 输出
JavaScript没有任何打印或者输出的函数。
在HTML中，JavaScript通常用于操作HTML元素。
*操作HTML元素*

  document.getElementById(id)方法获取元素，通过innerHTML来获取或插入元素内容。

*写到HTML文档*

  document.write()

*写到控制台*

  console.log()

浏览器中使用F12启用调试模式，在调试窗口中点击"Console"菜单。
#####JavaScript 语法
*JavaScript字面量*
数字(Number)字面量
3.14
1001
123e5
*字符串(String)字面量*
可以使用单引号或双引号
"John Doe"
'John Doe'
*表达式字面量*
5 \+ 6
5 \* 10
*数组(Array)字面量*
[40,100,1,5,25,10]
*对象(Object)字面量*
{firstName:"John",lastName="Doe",age:50,eyeColor:"blue"}
*函数(Function)字面量*

  function myFunction(a,b)
  {
    return a*b;
  }
*JavaScript变量*
使用关键字`var`来定义变量，使用等号来为变量赋值。

    var x, length
  x = 5
  length = 6
*JavaScript操作符*
算术运算符 (5+6)*10
赋值运算符  x = 5
位运算符、条件、比较、逻辑运算符
*JavaScript语句*
语句用分号分隔(可选)

    x = 5 + 6;

*JavaScript关键字*
必须以字母、下划线、美元符开始。
*JavaScript注释*

  //我不会执行

*JavaScript数据类型*
5+"value"="5value"
**JavaScript对大小写敏感**
*JavaScript字符集*
JavaScript使用Unicode字符集。

#####JavaScript 语句
可以用反斜杠对代码行进行换行，如

  document.write("你好 \
    世界!");
不过，不能像这样折行:

  document.write \
    ("你好世界!");

#####JavaScript 注释
单行注释://
多行注释:/\* \*/
#####JavaScript 变量
无值的变量,undefined

  var carname;
carname的值为undefined。

重新声明变量，值不会丢失。

  var carname="Volvo";
    var carname;
carname的值仍然是"Volvo"。
#####JavaScript 数据类型
布尔
true false
对象属性两种寻址方式:

  name=person.lastname;
    name=person["lastname"];

Undefined和Null
Undefined表示变量不含有值。
可以通过将变量的值设置为null来清空变量。
声明变量类型:
当声明新变量时，可以使用关键字`new`来声明其类型:

  var carname=new String;
    var x = new Number;
    var y = new Boolean;
    var cars = new Array;
    var person = new Object;
#####JavaScript 对象
如果访问person对象的fullName属性，它将作为一个定义函数的字符串返回。
函数属性作为一个属性\方法访问。
#####JavaScript 函数
如果你把值赋给一个尚未声明的变量，该变量将被自动作为全局变量声明，即使它在函数内执行。
如

  carname="Volvo";
#####JavaScript 作用域
*JavaScript局部作用域:*
变量在函数内声明
*JavaScript全局变量*
* 在函数外部声明；
* 如果你的变量没有声明，它将自动成为全局变量.

HTML中的全局变量
在HTML中，全局变量是window对象，所有数据变量都属于window对象。
eg:

  <script>
    myFunction();
        document.getElementById("demo").innerHTML="I can display" + window.carName;
        function myFunction()
        {
          carName="Volvo";
        }
    </script>

#####JavaScript 事件
HTML事件是发生在HTML元素上的事情。
可以是浏览器行为，也可以是用户行为。
如:
* HTML页面完成加载
* HTML input字段改变时
* HTML按钮被点击
在事件触发时，JavaScript可以执行一些代码。
HTML元素中可以添加事件属性:


  <some-HTML-element some-event="some JavaScript">
    如:
    <button onclick='getElementById("demo").innerHTML=Date()'>The time is ?</button>
代码修改自身元素的内容:
使用this关键字

  <button onclick="this.innerHTML=Date()">The time is ?</button>

JavaScript代码通常几行，常通过事件属性来调用。

**常见的HTML事件**
onchange  HTML元素改变
onclick   HTML元素被点击
onmouseover 用户在一个HTML元素上移动鼠标
onmouseout  用户从一个HTML元素上移开鼠标
onkeydown 用户按下键盘按键
onload    浏览器已完成页面的加载

#####JavaScript 字符串
可以通过索引位置来访问字符串中的每个字符

  var character = carname[7];
引号转义
*字符串长度*
内置属性length
eg:

  var text = "ABCDEFG";
    var sln = text.length;
字符串可以是对象

  var x = "John";
    var y = new String("John");
  typeof x // 返回String
    typeof y // 返回Object
    x===y //false
尽量不要创建string对象，它会拖慢执行速度，并可能产生其他副作用。
\=\=\=为绝对相等，即数据类型和值都必须相等。
属性:
construtor  返回创建字符串属性的函数
length    返回字符串的长度
prototype 允许您向对象添加属性和方法
方法:
charAt()  返回指定索引位置的字符
charCodeAt()  返回指定索引位置字符的Unicode值
concat()  连接两个或多个字符串，返回连接的字符串
fromCharCode()  将字符转换为Unicode值
indexOf() 返回字符串中检索指定字符第一次出现的位置
lastIndexOf() 返回字符串中检索指定字符最后一次出现的位置
localeCompare() 用本地特定的顺序来比较两个字符串
match() 找到一个或多个正则表达式的匹配
replace() 替换与正则表达式匹配的字串
search()  检索与正则表达式相匹配的值
slice()   提取字符串的片段，并在新的字符串中返回被提取的部分
split()   把字符串分割为子字符串数组
substr()  从起始索引号提取字符串中指定数目的字符
substring() 提取字符串中两个指定的索引号之间的字符
toLocaleLowerCase() 根据主机的语言环境把字符串转换为小写，只有几种语言(如土耳其语)具有地方特有的大小写映射
toLocaleUpperCase() 转换为大写
toLowerCase() 把字符串转换为小写
toString()  返回字符串对象值
toUpperCase() 把字符串转换为大写
trim()    移除字符串首尾空白
valueOf() 返回某个字符串对象的原始值
#####JavaScript 运算符
字符串连接符: +
== 等于
#####JavaScript If..Else语句

  var time = new Date().getHours();
  var r = Math.random();
#####JavaScript switch语句
与C语言类似
#####JavaScript for循环
for/in循环
循环遍历对象的属性

  var person={fname:"John",lname:"Doe",age:25};

    for(x in person)  //迭代的是key
    {
      txt = txt + person[x];
    }
#####JavaScript while循环
undefined也属于false
#####JavaScript break和continue语句
*JavaScript标签*

  label:
    statements;

    break labelname;
    continue labelname;
#####JavaScript typeof,null和undefined
*typeof*
检测变量的数据类型

  typeof "John" //返回string
    typeof 3.14   //返回number
    typeof false  //返回boolean
    typeof [1,2,3,4]//返回object
    typeof {name:'John',age:34}
            //返回object

**注意:数组是一种特殊的对象类型,因此typeof array返回object.**

*Null*
只有一个值的特殊类型,表示一个空对象引用.

  typeof null //返回object
设置为null值来清空对象

    typeof undefined  //返回undefined
可以设置undefined来清空对象

*Undefined*
表示没有设置值

*Undefined和Null的区别*

    typeof undefined // undefined
    typeof null //object
    null === undefined //false
    null == undefined  //true

#####JavaScript 类型转换
Number()转换为数字
String()转换为字符串
Boolean()转换为布尔值
*JavaScript中数据类型*
1.  string
2.  number
3.  boolean
4.  object
5.  function

对象类型:
1.  Object
2.  Date
3.  Array

2个不包含任何值的数据类型:
1.  null
2.  undefined


  tyoeof NaN; //返回number
*constructor属性*
返回所有JavaScript变量的构造函数

  "John".constructor  //返回function String() {[native code]}

通过constructor属性来查看变量是否为数组(包含字符串"Array")

  function isArray(myArray)
    {
      return myArray.constructor.toString().indexOf("Array")>-1;
    }
    function isDate(myDate)
    {
      return myDate.constructor.toString().indexOf("Date")>-1;
    }
*JavaScript类型转换*
将数字/布尔值/日期转换为字符串
String(123)
(123).toString()
_______________________
String(false)
false.toString()
_______________________
String(Date())
Date().toString()
_______________________
均可
Number方法
toExponential() 把对象的值转换为指数计数法
toFixed()   把数字转换为字符串,结果的小数点后有指定位数的数字
toPrecision() 把数字格式化为指定的长度

Date方法
getDate() 从Date对象返回一个月中的某一天(1~31)
getDay()  从Date对象返回一周中的某一天(0~6)
getFullYear() 从Date对象以四位数字返回年份
getHours()  返回Date对象的小时(0~23)
getMilliseconds() 返回Date对象的毫秒(0~999)
getMinutes()  返回Date对象的分钟(0~59)
getMonth()    从Date对象返回月份(0~11)
getSeconds()  返回Date对象的秒数(0~59)
getTime() 返回1970年1月1日至今的毫秒数

将字符串转换为数字
Number()
字符串包含数字会被转换为数字
空字符串转换为0
其他字符串会转换为NaN
parseFloat()  解析一个字符串,并返回一个浮点数
parseInt()  解析一个字符串,并返回一个整数
一元运算符 +
可以将变量转换为数字

  var y="5";
    var x=+y; //x是一个数字
如果变量不能转换,仍然是数字,但值为NaN.

布尔值转换为数字

  Number(true)  //返回1
    Number(false) //返回0

日期转换为数字

  d = new Date();
    Number(d);
    d.getTime()
二者等价.

自动类型转换
自动转换为字符串
当尝试输出一个对象或变量时,JavaScript会自动调用变量的`toString()`方法.

#####JavaScript正则表达式
Regular Expression(regex|regexp|RE)
*语法:*

  /pattern/modifiers
*字符串方法:*
search() 检索与正则表达式匹配的子字符串,并返回字串的起始位置
replace() 用于在字符串中用一些字符替换另一些字符,或替换一个与正则表达式匹配的子串

  //search()方法使用正则表达式
  var str="Visit W3cschool";
    var n = str.search(/w3cschool/i);
  //search()方法使用字符串
    var m = str.search("w3cschool");

  //replace()方法使用正则表达式
    var str = "Visit Microsoft";
    var res = str.replace(/microsoft/i,"w3cschool");
  //replace()方法使用字符串
    var ret = str.replace("Microsoft","w3cschool");

*正则表达式修饰符*
i 执行对大小写不敏感的匹配
g 执行全局匹配(查找所有匹配而非在找到第一个匹配后停止)
m 执行多行匹配
*正则表达式模式*
[abc] 查找方括号之间的任何字符
[0-9] 查找任何从0至9的数字
(x|y) 查找任何以|分隔的选项
*元字符*
\d 查找数字
\s 查找空白字符
\b 匹配单词边界
\uxxxx 查找以16进制数xxxx规定的Unicode字符
*量词*
n+  匹配任何包含至少一个n的字符串
n*  匹配任何包含0个或多个n的字符串
n?  匹配任何包含0个或1个n的字符串

*使用RegExp对象*
RegExp是一个预定义了属性和方法的正则表达式对象.
**使用test()**
正则表达式方法,检测一个字符串是否包含某个模式,如果有子串匹配返回true,否则false.

  var patt = /e/;
    patt.test("The best thing in life is free");
    因为包含'e',所以返回true.
    可以合并为一行:
    /e/.test("The best....");

*使用exec()*
检索字符串中的正则表达式的匹配
返回一个数组,其中存放匹配的结果,否则返回null.

  /e/.exec("The best thing in life is free");
    返回[e]

#####JavaScript错误

  try
    {
      //在这里运行代码
    }
    catch(err)
    {
      //在这里处理错误
    }

throw语句

  throw exception
异常可以是JavaScript字符串 数字 逻辑值或对象.

  <script>
      function myFunction()
        {
          try
            {
              var x = document.getElementById("demo").value;
                if(x=="") throw "empty";
                if(isNaN(x)) throw "not a number";
                if(x>10) throw "too high";
                if(x<5) throw "too low";
            }
            catch(err)
            {
              var y = document.getElementById("mess");
                y.innerHTML="Error:"+err+".";
            }

        }
    </script>
    <h1>My First JavaScript</h1>
    <p>Please input a number between 5 and 10;</p>
    <input id="demo" type="text">
    <button type="button" onclick="myFunction()">Test Input</button>
    <p id="mess"></p>

#####JavaScript调试
浏览器启用调试工具一般是按下F12键,并在调试菜单中选择"Console".
*console.log()方法*
*设置断点*
 debugger关键字
 这个关键字与在调试工具中设置断点的效果是一样的.

  var x = 15 * 5;
    debugger; //将在这里停止执行
    document.getElementById("demo").innerHTML=x;
火狐浏览器 Firebug插件可用于调试.
#####JavaScript表单验证
必填项目

  function validateForm()
    {
      var x = document.forms["myForm"]["fname"].value;
        if(x==null||x=="")
        {
          alert("First name must be filled out!");
        }
        return false;
    }
    <form name="myForm" action="demo_form.asp" onsubmit="return validateForm()" method="post">
      First name:
        <input type="text" name="fname">
        <input type="submit" value="Submit">
    </form>
#####JavaScript JSON
JSON是用于存储和传输数据的格式.
JSON通常用于服务端向网页传递数据.
JSON
* JSON(JavaScript Object Notation)
* JSON是一种轻量级的数据交换格式
* JSON是独立的语言
* JSON易于理解


  {
      "employees":
        [
        {"firstName":"John","lastName":"Doe"},
    {"firstName":"Anna","lastName":"Smith"},
    {"firstName":"Peter","lastName":"Jones"}
        ]
    }
*JSON格式化后转为JavaScript对象*
JSON格式在语法上与创建JavaScript对象代码是相同的
*JSON语法规则*
* 数据为键/值对
* 数据由逗号分隔
* 大括号保存对象
* 方括号保存数组

*JSON字符串转换为JavaScript对象*
使用JavaScript内置函数JSON.parse()将JSON字符串转换为JavaScript对象

JSON.parse()  用于将一个JSON字符串转换为JavaScript对象
JSON.stringify()  用于将JavaScript值转换为JSON字符串

#####JavaScript void
*javascript:void(0)含义*
void关键字指定要计算一个表达式但是不返回值

  <head>
    <script type="text/javascript">
    <!--
    void func()
    javascript:void func()

    或者

  void(func())
    javascript:void(func())
    //-->
    </script>
  </head>

href="#"与href="javascript:void(0)"的区别:
\#包含了一个位置信息,默认的锚是#top,也就是网页的上端.
而javascript:void(0),仅仅表示一个死链接.


#####JavaScript 函数定义
函数声明

  function functionName(parameters)
    {
      //执行的代码
    }
函数表达式

  var x = function(a,b){return a*b};
  //匿名函数
Function()构造函数

  var myFunction = new Function("a","b","return a*b");
函数提升(Hoisting)
提升是JavaScript默认将当前作用域提升到前面的行为,应用在变量的声明与函数的声明.
因此,函数可以在声明之前调用.
使用表达式定义函数时无法提升.
自调用函数

  (function()
    {
      var x = "hello!!";
    })();
    //匿名自我调用的函数
函数是对象
typeof 函数 是 "function"
但是JavaScript函数描述为一个对象更加准确.
JavaScript函数有**属性**和**方法**.
如arguments.length 属性返回函数调用过程中接收到的实际参数个数.
toString()方法将函数作为一个字符串返回.
该字符串的值就是函数在源代码中的声明字符串.
#####JavaScript函数参数
JavaScript函数对参数的值不进行任何检查.
对参数类型 数目都没有检测
默认参数,如果缺少参数,会默认设置为undefined

  function myFunction(x,y)
    {
      if(y === undefined)
          y = 0;
    }
    或者
    function myFunction(x,y)
    {
      y = y || 0;
    }
如果传入了过多的参数,将无法引用,只能通过arguments对象来调用.
Arguments对象
实际参数数组
#####JavaScript函数调用
this关键字
一般而言,this指向函数执行时的当前对象,不能修改其值.
全局函数属于window对象.
this指向浏览器窗口(window对象)
函数作为对象方法调用,会使得this的值成为对象本身.
*使用构造函数调用函数*

  //构造函数
  function myFunction(arg1,arg2)
    {
      this.firstName = arg1;
        this.lastName = arg2;
    }

    //This creates a new object
  var x = new myFunction("John","Doe");
    x.firstName;  //返回"John"
构造函数的调用会创建一个新的对象,新对象会继承构造函数的属性和方法.
构造函数中this关键字没有任何的值
this的值在函数调用时实例化对象(new object)时创建
*作为函数方法调用函数*
在JS中,函数是对象,函数也有自己的属性和方法.
call() apply() 可用于调用函数
两个方法的第一个参数是对象本身

    function myFunction(a,b)
    {
      return a*b;
    }
    myFunction.call(myObject,10,2);

  function myFunction(a,b)
    {
      return a*b;
    }
    myArray = [10,2];
    myFunction.apply(myObject,myArray); //返回20
区别在于第二个参数,apply传入的是一个参数数组,而call则作为call的参数传入(从第二个参数开始).
在JS严格模式(strict mode)下,在调用函数时第一个参数会成为this的值,即使该参数不是一个对象.
在非严格模式(non-strict mode)下,如果第一个参数的值为null或undefined,它将使用全局对象替代.
通过call()或apply()方法你可以设置this的值,且作为已存在对象的新方法调用.
#####JavaScript闭包
JavaScript变量可以是局部变量或者全局变量.
私有变量可以用到闭包.
全局变量和局部变量可以重名,类似C语言.
**变量声明是如果不使用 var 关键字，那么它就是一个全局变量，即便它在函数内定义.**
*JavaScript内嵌函数*
在JS中,所有函数都能访问它们上一层的作用域.

  function add()
    {
      var counter = 0;
        function plus( counter += 1;)
        plus();
        return counter;
    }
*JavaScript闭包*

  var add = (function(){
      var counter = 0;
        return function()
        {
         return counter+=1;
        }
    })();
    add();
    add();
    add();
**闭包**使得函数拥有私有变量变成可能.
计数器受匿名函数的作用域保护,只能通过add方法修改.
**闭包是可访问上一层函数作用域里变量的函数,即使上一层函数已经关闭.**
#####JavaScript HTML DOM
DOM(Document Object Model)文档对象模型
当网页被加载时,浏览器会创建页面的文档对象模型.
**HTML DOM树**
![DOM](http://www.runoob.com/images/pic_htmltree.gif)
* JavaScript能够改变页面中所有的HTML元素
* JavaScript能够改变页面中所有的HTML属性
* JavaScript能够改变网页中所有的CSS样式
* JavaScript能够对页面中所有事件做出反应
*查找HTML元素*
1.  通过id查找
document.getElementById("intro");
如果未找到该元素,返回null.
2.  通过标签名查找
document.getElementsByTagName("p")
3.  通过类名查找
document.getElementsByClassName("intro");
(IE8及更早IE版本不支持该函数)

#####JavaScript 改变HTML
*改变HTML输出流*
绝对不要在文档加载完成之后使用document.write(),这将覆盖该文档.
*改变HTML内容*
innerHTML
*改变HTML属性*
attribute:

  document.getElementById("image").src="newpic.jpg";
#####JavaScript 改变CSS

  document.getElementById(id).style.property = new style;

设置文本可见性:

  document.getElementById("p1").style.visibility="hidden";
    document.getElementById("p1").style.visibility="visible";
#####JavaScript HTML DOM 事件
*对事件做出反应*
如需在某个事件发生时执行JS代码,我们需要向一个HTML事件属性添加JS代码.
`onclick=javaScript`
*HTML事件属性*
onload:进入页面时,可用于检测访问者的浏览器类型和浏览器版本,并基于这些信息来加载网页的正确版本.
onunload:离开页面时,和onload事件用于处理cookie.
onchange:改变输入字段内容时
onmouseover和onmouseout:
鼠标移至HTML元素上方或者移出元素时触发函数.
onmousedown onmouseup onclick:
点击鼠标    释放鼠标   完成点击
onfocus: 获得焦点
#####JavaScript EventListener
*addEventListener()方法*

  document.getElementById("myBtn").addEventListener("click",displayDate);
addEventListener()方法用于向指定元素添加事件句柄,不会覆盖已有的事件句柄.
可以向一个元素添加多个事件句柄
可以向同个元素添加多个同类型的事件句柄,如两个"click"事件.
可以向任何DOM对象添加事件监听,不仅仅是HTML元素,如window对象.
addEventListener()方法可以更简单的控制事件(冒泡与捕获).
可以将JavaScript从HTML标记中分离出来,可读性更强.
移除事件监听:removeEventListener()
*语法:*
element.addEventListener(event,function,useCapture);
* 第一个参数是事件的类型(click,mousedown)
* 第二个参数是事件触发后调用的函数
* 第三个参数是个布尔值,用于描述事件是冒泡还是捕获,该参数可选.

**事件名称去掉"on"前缀即可.**

addEventListener()方法允许你在HTML DOM对象添加事件监听,HTML DOM对象如:HTML元素 HTML文档 window对象 或者 其他支出的事件对象如 xmlHttpRequest对象.

  window.addEventListener("resize",function()
    {
      document.getElementById("demo").innerHTML = Math.random();
    })
*传递参数*
当传递参数值时,使用匿名函数调用带参数的函数.

    element.addEvventListener("click",function(){myFunction(p1,p2);});
*事件冒泡或事件捕获*
事件传递有两种方式: 冒泡和捕获
事件传递定义了元素事件触发的顺序,如果把`<p>`放到`<div>`元素中,点击`<p>`元素,哪个元素的"click"事件先被触发呢?
冒泡:内部元素的事件先被触发 false
捕获:外部元素的事件先被触发 true
扩浏览器解决方案:

  var x = document.getElementById("myBtn");
    //所有主流浏览器,除了IE8及更早版本
    if(x.addEventListener)
    {
      x.addEventListener("click",myFunction);
    }
    else if(x.attachEvent)//IE8及更早版本
    {
      x.attachEvent("onlick",myFunction);
    }
#####JavaScript HTML DOM元素(节点)
*创建新的HTML元素*
首先创建该元素,然后向一个已存在的元素追加该元素.

  <div id="div1">
      <p id="p1">This is a paragraph.</p>
        <p id="p2">This is another paragraph.</p>
    </div>

    <script>
      var para = document.createElement("p");
        var node=document.createTextNode("This is new");
        para.appendChild(node);

        var element = document.getElementById("div1");
        element.appendChild(para);
    </script>
*删除已有的HTML元素*

  <div id="div1">
      <p id="p1">This is a paragraph.</p>
        <p id="p2">This is another paragraph.</p>
    </div>

    <script>
      var parent = document.getElementById("div1");
        var child = document.getElementById("p1");
        parent.removeChild(child);
    </script>
常见的解决方案,找到希望删除的子元素,然后使用其parentNode属性来找到父元素:

  var child = document.getElementById("p1");
    child.parentNode.removeChild(child);
***************************
#####JavaScript对象
访问对象的属性:
objectName.propertyName
访问对象的方法:
objectName.methodName()
创建JavaScript对象:
* 定义并创建对象的实例
* 使用函数来定义对象,然后创建新的对象实例

eg:

  function person(firstName,lastName,age,eyeColor)
    {
      this.firstName = firstName;
        this.lastName = lastName;
        this.age = age;
        this.eyeColor = eyeColor;
    }
    var myFather = new person("John","Doe",50,"blue");

在JavaScript中,this通常指向我们正在执行的函数本身,或者是指向该函数所属的对象(运行时).
*JavaScript类:*
JavaScript是面向对象的语言,但JavaScript不使用类.
JavaScript基于prototype,而不是基于class.
*for...in循环*
循环遍历对象的属性

  for(variable in object)
    {
      //code to be executed here
    }
#####JavaScript Number对象
所有JS数字均为64位
不分整型还是浮点型,所有数字都是浮点型.
精度:整数最多为15位 小数的最大位数是17.

八进制: 前缀0
十六进制:前缀0x
使用toString()方法输出16进制 8进制 2进制
eg:

  var myNumber = 128;
    myNumber.toString(16);//returns 80
    myNumber.toString(8)://returns 200
    myNumber.toString(2);//returns 10000000
无穷大(Infinity)
Infinity -Infinity
非数字值(NaN)
使用全局函数`isNaN()`来判断是否为NaN值.
*数字可以是数字或者对象*

  var x = 123;
    var y = new Number(123);
    typeof(x);  //returns Number
    typeof(y);  //returns Object

数字属性:
* MAX_VALUE
* MIN_VALUE
* NEGATIVE_INFINITY
* POSITIVE_INFINITY
* NaN
* prototype
* construtor
数字方法:
* toExponential()
* toFixed()
* toPrecision()
* toString()
* valueOf()

#####JavaScript 字符串(String)对象
`indexOf()`定位字符串中某一个指定的字符串首次出现的位置

  var str="Hello world!";
    var n = str.indexOf("world");
如果没找到返回-1,lastIndexOf()方法在字符串末尾开始查找字符串首次出现的位置.
`match()`函数用于定位字符串中特定的子串,如果找到的话,返回该子串.

  var str = "Hello world!";
    document.write(str.match("world")+"<br/>");
    document.write(str.match("World")+"<br/>"); //返回null
    document.write(str.match("world!"));
`replace()`函数用于在字符串中用某些字符替换另一些字符.

  str = "Please visit Microsoft!";
    var n = str.replace("Microsoft","W3cschool");

大小写转换:
`toUpperCase()`和`toLowerCase()`
字符串转为数组:
`split()`

    txt = "a,b,c,d,e";
    txt.split(",");
#####JavaScript 日期(Date)对象

  var d = new Date();
    document.write(d);
`getFullYear()`获得年份
`getTime()` 返回从1970年1月1日至今的毫秒数
`setFullYear()`设置具体的日期

  function myFunction()
    {
      var d = new Date();
        d.setFullYear(2020,10,3);//10 is Nov
        var x = document.getElementById("demo");
        x.innerHTML = d;
    }
`toUTCString()` 将当前时间转换为UTC时间字符串.

`getDay()` 返回星期几 0-6
在网页上显示一个时钟:

  function startTime()
    {
      var today = new Date();
        var h = today.getHours();
        var m = today.getMinutes();
        var s = today.getSeconds();
        //add a zero in front of numbers < 10
        m = checkTime(m);
        s=checkTime(s);
        document.getElementById("txt").innerHTML=h+":"+"m"+":"+s;
        t = setTimeout(function(){startTime(),500});
    }
    function checkTime(i)
    {
      if(i<10)
          i="0"+i;
        return i;
    }
**setTimeout()方法用于在指定的毫秒数后调用函数或计算表达式.**
setTimeout(code,millisec)
四种方式初始化日期:
new Date()  //当前日期和时间
new Date(millisec) //返回从1970年1月1日至今的毫秒数
new Date(dateString)
new Date(year,month,day,hours,minutes,seconds,milliseconds)
参数大多可选,不指定的情况下,默认参数是0.
eg:

  var today = new Date();
    var d1 = new Date("October 13, 1975 11:13:00");
    var d2 = new Date(79,5,24);
    var d3 = new Date(79,5,24,11,33,0)
将日期对象设置为5天后的日期:

  var myDate = new Date();
    myDate.setDate(myDate.getDate()+5);
两个日期比较
\> <
#####JavaScript 数组(Array)对象
在一个数组中可以有不同的对象
concat()合并两个数组
join() 用数组的元素组成字符串
pop() 删除数组的最后一个元素
push()  数组的末尾添加新的元素
reverse() 将数组的元素反转排序
shift() 删除数组的第一个元素 返回被删元素
unshift() 在数组的开头添加新元素 返回数组个数
slice() 从一个数组中选择元素
sort() 数组排序

    var points = [40,100,1,5,25,10];
    points.sort(function(a,b){return a-b};)
splice() 在数组的第2位置添加一个元素
直接对数组进行修改

  var fruits = ["Banana","Orange","Apple","Mango"];
    fruits.splice(2,0,"Lemon","Kiwi");
toString() 转换数组到字符串

#####JavaScript 布尔(Boolean)对象
0 is boolean false
1 is boolean true
An empty string is boolean false
null is boolean false
NaN is boolean false
The string "false" is boolean true
如果布尔对象无初始值或者其值为:
* 0
* -0
* null
* ""
* false
* undefined
* NaN

那么该对象的值为false,否则为true.
#####JavaScript 算数(Math)对象
Math.round() 四舍五入
Math.random() 返回0到1之间的随机数
max() min() floor()
无需在使用Math对象之前对它进行定义.
Math.PI
Math.sqrt()
常量:
Math.E
Math.PI
Math.SQRT2
Math.SQRT1_2
Math.Ln2
Math.Ln10
Math.LOG2E
Math.LOG10E
#####JavaScript RegExp对象

  var patt = new RegExp(pattern,modifiers);
    或者
    var patt = /pattern/modifiers;
注意,当使用构造函数构造RegExp对象时,需要常规的字符转义规则,如以下等价:

  var re = new RegExp("\\w+");
    var re = /\w+/;
RegExp修饰符:
i 不区分大小写
g 全局搜索
test()方法搜索字符串指定的值,根据结果返回真或假.
exec()方法检索字符串中的指定值,返回值是被找到的值,如果没有发现匹配,则返回null.
*************************************
#####JavaScript Window-浏览器对象模型
BOM(Browser Object Model)浏览器对象模型尚无正式标准.
*window对象*
表示浏览器窗口,所有JavaScript全局对象 函数 以及变量均自动成为window对象的成员.
全局变量是window对象的属性.
全局函数是window对象的方法.
document也是window对象的属性之一.
eg:

    window.document.getElementById("header");
    与
    document.getElementById("header");
    相同
*Window尺寸*
有三种方法确定浏览器窗口的尺寸(浏览器的视口,不包括工具栏和滚动条)
window.innerHeight -浏览器窗口的内部高度
window.innerWidth  -浏览器窗口的内部宽度
对于IE8 7 6 5:
document.documentElement.clientHeight
document.documentElement.clientWidth
或者
document.body.clientHeight
document.body.clientWidth
eg:

  var w = window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth;
    var h = window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight;
其他window方法:
* window.open() 打开新窗口
* window.close()  关闭当前窗口
* window.moveTo() 移动当前窗口
* window.resizeTo() 调整当前窗口的尺寸

#####JavaScript Window Screen
window.screen对象包含有关用户屏幕的信息.
window.screen对象在编写时可以不使用window这个前缀.

  screen.availWidth -可用的屏幕宽度
    screen.availHeight-可用的屏幕高度

#####JavaScript Window Location
window.location对象用于获得当前页面的URL,并把浏览器重定向到新的页面.

  location.hostname //返回web主机的域名
    location.pathname //返回当前页面的路径和文件名
    location.port //返回web主机的端口(80或443)
    location.protocol //返回所使用的web协议(http://或https://)

*Window Location Href*
location.href属性返回当前页面的URL
*Window Location Pathname*
location.pathname属性返回URL的路径名
*Window Location Assign*
location.assign()方法加载新的文档

  function newDoc()
    {
      window.location.assign("http://www.w3cschool.cc");
    }
#####JavaScript Window History
window.history对象包含浏览器的历史
为了保护用户隐私,对JavaScript访问该对象的方法做出了限制.
history.back()  与在浏览器中点击后退按钮相同
history.forward() 与在浏览器中点击前进按钮相同
#####JavaScript Window Navigator
window.navigator对象包含有关访问者浏览器的信息.

  <div id="example"></div>
    <script>
      txt = "<p>Browser CodeName: "+navigator.appCodeName+"</p>";
        txt += "<p>Browser Name: "+navigator.appName+"</p>";
        txt += "<p>Browser Version: "+navigator.appVersion+"</p>";
        txt += "<p>Cookies Enabled: "+navigator.cookieEnabled+"</p>";
        txt += "<p>Platform: "+navigator.platform+"</p>";
        txt += "<p>User-agent header:"+navigator.userAgent+"</p>";
        txt += "<p>User-agent language: "+navigator.systemLanguage+"</p>";
    document.getElementById("example").innerHTML=txt;
    </script>
**注意:来自navigator的信息具有误导性,不应该被用于检测浏览器版本,因为**
**1.navigator数据可被浏览器使用者更改**
**2.一些浏览器对测试站点会识别错误**
**3.浏览器无法报告晚于浏览器发布的新操作系统**

*浏览器检测*
由于不同的浏览器支持不同的对象,您可以使用对象来检测浏览器,例如,由于只有Opera支持属性`window.opera`,您可以据此识别出Opera.
eg:

  if(window.opera)
    {
      //some code...
    }
#####JavaScript 弹窗
三种消息框:警告框、确认框、提示框。
*警告框*
"确认"

  window.alert("warning...");
*确认框*
"确认"或者"取消"，分别返回true和false

  window.confirm("some text");
*提示框*
用户需要输入某个指，然后点击"确定"或者"取消"
如果"确认"，返回输入的值
如果"取消"，返回null

  window.prompt("sometext","defaultValue");
*换行*
弹窗使用\n来换行
#####JavaScript 计时事件
在一个设定的时间间隔之后来执行代码
两个关键方法:
* setInterval() 间隔指定的毫秒数不停地执行指定的代码
* setTimeout()  暂停指定的毫秒数后执行指定的代码

属于window对象。
*setInterval()*

  window.setInterval("javascript function",milliseconds);
eg:
每3秒弹出"hello":

  setInterval(function(){alert("Hello!")},3000);
clearInterval()方法用于停止setInterval()方法执行的函数代码。

  window.clearInterval(intervalVaribale)
为了使用clearInterval()方法，在创建计时方法时必须使用全局变量。
eg:

  var myVar = setInterval(......);
    clearInterval(myVar);

*setTimeout()方法*

  window.setTimeout("javascript function",milliseconds);
会返回某个值，如果希望取消它，通过使用这个变量来指定它。
第二个参数指示从当前起多少毫秒后执行第一个参数。

clearTimeout()方法用于停止执行setTimeout()方法的函数代码。

  window.clearTimeout(timeoutVariable);
#####JavaScript Cookies
Cookies用于存储web页面的用户信息。
*什么是Cookies?*
Cookies是一些数据，存储于电脑上的文本文件中。
当Web服务器向浏览器发送Web页面时，在连接关闭后，服务端不会记录用户的信息。
Cookies的作用就是用于解决"如果记录客户端的用户信息"。
* 当用户访问web页面时，他的名字可以记录在cookie中
* 当用户下一次访问该页面时，可以在cookie中读取用户访问记录
Cookies以名/值对的形式存储，如下所示:


  username=John Doe
当浏览器从服务端上请求web页面时，属于该页面的cookies会被添加到该请求中，服务端通过这种方式来获取用户的信息。

*使用JavaScript创建Cookie*
JS可以使用**document.cookie**属性来创建、读取、删除cookies。

  document.cookie="username=John Doe";
还可以为cookie添加一个过期时间(以UTC或GMT时间)。默认情况下，cookie在浏览器关闭时删除。

    document.cookie="username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 GMT";
还可以使用path参数告诉浏览器cookie的路径，默认情况下，cookie属于当前页面

  document.cookie="username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 GMT;path=/";

*使用JavaScript读取Cookie*

  var x = document.cookie;
**document.cookie将以字符串的形式返回所有的Cookies.类型格式:
cookie1=value;
cookie2=value;
cookie3=value;**

*使用JavaScript修改Cookie*
即覆盖旧的cookie

*使用JavaScript删除Cookie*
只需设置expires参数为以前的时间即可

    document.cookie = "username=;expires=Thu, 01 Jan 1970 00:00:00 GMT";
注意，当删除时不必指定cookie的值。

*Cookie字符串*
document.cookie看起来像一个普通的文本字符串，其实不是。
如果需要查找一个指定的cookie值，必须创建一个JS函数在cookie字符串中查找cookie值。
*实例*
设置cookie值的函数:

  function setCookie(cname,cvalue,exdays)
    {
      var d = new Date();
        d.setTime(d.getTime()+(exdays*24*60*60*1000));
        var expires = "expires="+d.toGMTString();
        document.cookie=cname+"="+cvalue+";"+expires;
    }
获取cookie值的函数:

  function getCookie(cname)
    {
      var name = cname + "=";
        var ca = document.cookie.split(";");
        for(var i=0;i<ca.length;i++)
        {
          var c = ca[i].trim();
            if(c.indexOf(name)==0)
              return c.substring(name.length,c.length);
        }
        return "";
    }

检测cookie值的函数:

  function checkCookie()
    {
      var username = getCookie("username");
        if(username!="")
        {
          alert("Welcome again "+username);
        }
        else
        {
          username=prompt("Please enter your name:","");
            if(username!=""&&username!=null)
            {
              setCookie("username",username,365);
            }
        }
    }

在页面载入时执行checkCookie()函数

  <body onload="checkCookie()">
    </body>
#####JavaScript 库
jQuery、Prototype、MooTools

*JavaScript框架(库)*
JavaScript高级程序设计(特别是对浏览器差异的复杂处理)，通常很困难也很耗时。

*jQuery*
jQuery是目前最受欢迎的JavaScript框架。
它使用CSS选择器来访问和操作页面上的HTML元素(DOM对象)
同时提供companion UI(用户界面)和插件。

*Prototype*
提供用于执行常见web任务的简单API
Prototype 通过提供类和继承，实现了对 JavaScript 的增强。

*MooTools*
也含有一些轻量级的效果和动画函数。

*其他框架*
* YUI(Yahoo!User Interface Framework),涵盖大量函数的大型库，从简单的JS功能到完整的internet widget。
* Ext JS:可定制的widget，用于构建富因特网应用程序(rich Internet applications)
* Dojo:用于DOM操作、事件、widget等的工具包
* script.aculo.us:开源的JavaScript框架，针对可视效果和界面行为
* UIZE:Widget、AJAX、DOM、模板等等。

*CDN 内容分发网络*
如果许多不同的网站使用相同的JavaScript框架，那么把框架库存放在一个通用的位置供每个网页分享就变得很有意义。
CDN(Content Delivery Network)解决了这个问题，CDN是包含可分享代码库的服务器网络。
Google为一系列JavaScript库提供了免费的CDN，包括jQuery、Prototype、MooTools、Dojo、Yahoo!YUI，但是由于GFW(防火长城，Great Firewall of China)屏蔽，所以访问不稳定，建议使用百度静态资源公共库:
[http://cdn.code.baidu.com]
如果需要使用JavaScript框架，只需要在`<script>`标签中引用该库即可:

  <script src="http://apps.bdimg.com/libs/jquery/2.1.1/jquery.min.js">
    </script>

#####JavaScript 测试jQuery
jQuery允许链接(链式语法)
链接(Chaining)是一种在同一对象上执行多个任务的便捷方法
#####JavaScript 测试Prototype
与jQuery相同，Prototype允许链式语法。

#####javaScript 实例
