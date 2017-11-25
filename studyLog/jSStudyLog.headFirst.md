# JavaScript 

## INDEX

####[Chapter 1-2](#Chapter1-2)

- [HTML标记和JS的关系](#HTML标记和JS的关系)
- [加载顺序](#加载顺序)
- [数组](#数组)
- [字符串加法](字符串加法)
- [DOM](#DOM(Document Object Model))


####[Chapter 3](#Chapter3)

####[Chapter4：函数、变量和对象](#Chapter4：函数、变量和对象)

- 




#Chapter1-2

##HTML标记和JS的关系

**建立元素（HTML标记）和变量（JavaScript对象）的映射。**

JS通过*DOM*来访问HTML标记

具体方式有

```javascript
var Name = document.getElementById("idName")

```

****





## DOM(Document Object Model)

文档对象模型

## 加载顺序

在页面加载之前就执行CODE的话会导致无法读取标签对象



## 数组



#### 新建数组 

```javascript
var arrayName = new Array();

```



#### 数组属性

```javascript
var arr1 = new Array();
var ran1 = Math.floor(Math.random() * arr1.length);//数组的长度

```



## 字符串加法

```javascript
"String" + Integer = "StringInerger"

```



## Math库

```javascript
Math.random() //生成0-1之间的随机数
Math.floor//去掉小数部分

```



--------

# Chapter3

## 创建元素和插入位置

```javascript
var li = document.createElement("li");//创建元素。
li.innerHTML = songName;//向元素内添加内容。
var ul = document.getElementById("ul");//得到父元素。
ul.appendChild(li);//添加子元素
```



## playlist事件触发

```javascript
function init(){
    var button = document.getElementById("addSong");//获得按钮元素->对象
    button.onclick = handleButtonClick;//设置button的onclick属性为函数名，点击button时触发handleButtonClick函数。
}window.onload = init;//先加载页面再加载init。

function handleButtonClick(){
    var textInput = document.getElementById("songTextInput");//得到用户输入元素->对象
    var songName = textInput.value;//7-8行需要理解<form>。得到用户输入对象的value(即内容)属性(property)；
    var li = document.createElement("li");//创建元素。
    li.innerHTML = songName;//向元素内添加内容。
    var ul = document.getElementById("ul");//得到父元素。
    ul.appendChild(li);//添加子元素。
}
```



## Form

```Html
<form>
<input type="text" id="songTextInput" size="40" placeholder="Song name">//用户输入
<input type="button" id="addButton" value="Add Song">//按钮
</form>
```



---

#Chapter4：函数、变量和对象

## 函数和属性

```javascript
var textInput = document.getElementById("songTextInput");//.getElementById("songTextInput") 函数传参
button.onclick = handleButtonClick；//属性赋值
```





##函数

###定义函数

```javascript
function checkGuess(guess){//函数名和参数都是optional.
  ---code
  ---
  return whatever;//返回值可选
}
```



###函数也是值

```javascript
var f = function(){
  alert(where is my name?);
}//将函数整体赋给了f
botton.onclick = function(){
    alert(botton clicked);
}//将函数整体赋给了one of botton's propertis, which is onclick.
window.onload = checkGuess;//函数整体赋给 one of window's propertis, which is onload.
```





##参数和变量

###实参和形参

**定义**函数时指定`形参`，**调用**函数时传递`实参`。



###变量传递

向函数传递参数时，传递的是实参，但在函数体内还是形参，也就是说传递的变量值不会改变。

*不过传递数组时情况不一样。*



###局部和全局变量

- 页面存在全局变量就存在（刷新相当于重载页面），函数结束局部变量消失。
- 局部变量会“遮蔽”全局变量





## 对象

###单个对象创建

```javascript
var objectName = {                      //赋值的是引用
     property1 :"string",
     property2 : integer,
     property3 : [Array1,Array2],
     method1 : function(){
         alert(this.property1); //在对象内定义函数要用*this*指定对象名
     }
};
```

###工厂函数

 ```javascript
      function ObjectName(property1,property2,property3){			//创建工厂
          this.property1 = ;
          this.property2 = ;								    //工厂函数实际上是一个函数（废话。。）所                                                                以内部要用分号，区分于单个对象创建的逗号
          this.property3 =  {                                  //属性可以是对象
           property1 :"string",
           property2 : integer,
           property3 : [Array1,Array2],
           method1 : function(){
               alert(this.property1); 
           }
      };
          this.method = function(){
              alert(this.property);
          
          };
      }

      var instance = new ObjectName(property1,property2,property3)  //创建实例并赋引用给变量
       //所有的property都是必须的吗？
      var time = new getDate().getTime //创建实例访问属性并赋值给变量
 ```



####关于`this`

```javascript
this的存在得以实现 objectName.method() 处理objectName的属性时无需传递参数在()中。
创建实例后，实际上所有实例都共享着工厂函数里：1、属性名和key值的关系。2、方法的代码实现。//这样做增加了代码重用。
```



### 调用属性或者方法

```javascript
var property1 = name.property1;
var property2 = name.property2;
var property3 = name.property3;
name.method1();                 //
```



### 对象作为参数传递

在创建对象时候对象将<u>引用</u>赋给了`变量`，所以传递实参实质上传递了引用，即在函数内部形参也等于引用，并且和`实参`指向了同一`对象`，所以`形参`的任何改变都会反映到原本传入的`变量`引用的`对象`上。



## 函数、变量和对象的关系

- 变量储存1、数据类型的值比如：数，串和数组。2、对象的引用

- 函数1、传入、加工、传出（optional）参数（变量的值）2、传入对象的引用，加工对象。

- 对象封装变量和函数作为对象的属性和方法，属性是变量，方法是函数。

  ​






---









