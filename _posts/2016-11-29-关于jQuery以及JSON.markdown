---
layout:     post
title:      "关于jQuery以及JSON"
subtitle:   ""
date:       2016-11-29
author:     "MaggicQ"
tags:
    - 其他

---



## jQuery



### 了解jQuery



**jQuery** 是一个快速的，轻量的，特性丰富的开源JavaScript库，它的宗旨是“写的少，做的多*（write less,do more）*”，使用jQuery的目的是为了更好的利用JavaScript，减轻网页开发者的工作。

**jQuery**的强大之处体现在哪呢？**jQuery** 能够很好的遍历以及操纵*HTML*元素，处理网页上的触发事件 ，动画以及让AJAX技术的应用变得更加简单，此外，**jQuery** 能在几乎所有主流的浏览器下正常工作。它具有强大的通用性和可拓展性。



### 简单的例子



#### 操纵HTML元素：

```javascript
$( "button.continue" ).html( "Next Step..." )
```

jQuery使用`$`符号表示选择元素，上面这个语句选择了网页中的含有 `continue` 属性的 `<button>`元素，并且它的HTML改变为 *“Next Step....”*。是不是感觉一切都变得很容易！



#### 控制事件触发

```javascript
var hiddenBox = $( "#banner-message" );
$( "#button-container button" ).on( "click", function( event ) {
  hiddenBox.show();
});
```

上面这段代码的作用是：

​	绑定一个事件到`id=button-container`的`<button>`元素，当`click`事件被触发时，`hiddenBox`就会被显示出来。这里的`hiddenBox`是一个`id=banner-message`的元素(在第一行被定义)，我们假设它在默认情况下被CSS隐藏。



#### 与Ajax交互

```javascript
$.ajax({
  url: "/api/getWeather",
  data: {
    zipcode: 97201
  },
  success: function( result ) {
    $( "#weather-temp" ).html( "<strong>" + result + "</strong> degrees" );
  }
});
```

上面这段代码的作用是：

​	调用服务器上的`/api/getWeather`脚本，查询参数为`zipcode: 97201`，并且将网页中指定的元素的html替换成换回的结果。



## JSON以及XML

### 基本概念

**JSON**(JavaScript Object Notation) 是一种轻量级的数据交换格式。 易于人阅读和编写。同时也易于机器解析和生成。 它基于*JavaScript*， JSON采用完全独立于语言的文本格式，但是也使用了类似于C语言家族的习惯（包括C, C++, C#, Java, JavaScript, Perl, Python等）。 这些特性使JSON成为理想的数据交换语言。



**XML** 也就是可扩展标记语言，（英语：Extensible Markup Language，简称：**XML**），是一种标记语言，通过此种标记，计算机之间可以处理包含各种信息的文章等。如何定义这些标记，既可以选择国际通用的标记语言，比如HTML，也可以使用像XML这样由相关人士自由决定的标记语言，这就是语言的可扩展性。XML是被设计用来传送以及携带数据信息的。



### 比较

下面是一段JSON格式的数据：

```json
{"employees":[
    {"firstName":"John", "lastName":"Doe"},
    {"firstName":"Anna", "lastName":"Smith"},
    {"firstName":"Peter", "lastName":"Jones"}
]}
```

接下来是一段XML呈现的数据：

```xml
<employees>
    <employee>
        <firstName>John</firstName> <lastName>Doe</lastName>
    </employee>
    <employee>
        <firstName>Anna</firstName> <lastName>Smith</lastName>
    </employee>
    <employee>
        <firstName>Peter</firstName> <lastName>Jones</lastName>
    </employee>
</employees>
```

从上面可以看出二者的一些特性。



**共同点**：

* 容易理解，对于人来说是可读的，而不仅仅是对机器。
* 分层。
* 都可以被许多编程语言解析。
* 都可以用**XMLHttpRequest**对象获取。（关于这个对象，在AJAX那篇博客中有涉及到）

**不同点**：

* JSON不使用标签，而XML可以使用自定义的标签。
* JSON更为简短，容易阅读。
* JSON可以使用数组。



同时，因为JSON与JavaScript结合更为紧密，使用javascript语句可以很简单的对数据进行转化解析，同时速度还比较快，对于AJAX应用，JSON的响应速度也是要优于XML的，所以现在JSON格式的数据传输正在逐渐取代XML。





## 参考资料

[jquery官方网站](http://jquery.com/)

[W3C](http://www.w3schools.com/js/js_json_intro.asp)
