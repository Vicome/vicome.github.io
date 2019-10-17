---
layout:		post
title:		"JavaScript"
subtitle:	"JavaScript-javaScript内置对象"
date:		2019-10-15
author:		"vicome"
header-img:	"img/post-bg-js.jpg"
catalog:    true
tags:
    - JavaScript
---

> 匆匆错过的，何止是窗外的世界。



## JavaScript 内置对象

### 1. Array 对象

Array 对象用于在变量中存储多个值：

```js
var cars = ["Saab","Volvo","BMW"];
```

数组下标从0开始。

#### 数组属性

| 属性         | 描述 |
| ------------| ---- |
| constructor | 返回创建数组对象的原型函数 |
| length      | 设置或返回数组元素的个数 |
| prototype   | 允许你想数组对象添加属性或方法 |

- ##### constructor

  **定义和用法**

  在 JavaScript 中, constructor 属性返回对象的构造函数。

  返回值是函数的引用，不是函数名：

  JavaScript 数组 constructor 属性返回 function Array() { [native code] }

  JavaScript 数字 constructor 属性返回 function Number() { [native code] }

  JavaScript 字符串 constructor 属性返回 function String() { [native code] }

  如果一个变量是数组你可以使用 constructor 属性来定义。

  **代码：**

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  	<meta charset="utf-8">
  </head>
  <body>
  <p id="demo">点击按钮创建一个数组，并显示它的构造函数。</p>
  <button onclick="myFunction()">点我</button>
  <script>
  function myFunction()
  {
  	var fruits = ["Banana", "Orange", "Apple", "Mango"];
  	var x=document.getElementById("demo");
  	x.innerHTML=fruits.constructor;
  }
  </script>
  </body>
  </html>
  ```

  本例运行结果是：`function Array() { [native code] }`

- ##### length

  设置数组的长度：

  ```js
  array.length = number;
  ```

  返回数组的长度：

  ```javascript
  array.length;
  ```

  代码：

  ```html
  ...
  (同上)
  ...
  <body>
  <p id="demo"></p>
  <button onclick="myFunction()">点我</button>
  <script>
  var fruits = ["Banana", "Orange", "Apple", "Mango"];
  document.getElementById("demo").innerHTML=fruits;
  function myFunction()
  {
  document.getElementById("demo").innerHTML=fruits.length;
  }
  </script>
  </body>
  ...
  ```

- ##### prototype

  **定义和用法：**

  prototype 属性使您有能力向对象添加属性和方法。

  当构建一个属性，所有的数组将被设置属性，它是默认值。

  在构建一个方法时，所有的数组都可以使用该方法。

  > **注意：** Array.prototype 单独不能引用数组, Array() 对象可以。
  >
  > **注意：** 在JavaScript对象中，Prototype是一个全局属性。

  **代码：**

  ```html
  ...
  <body>
  <p>点击按钮填充 “Runoob” 到数组的最后两个元素。</p>
  <button onclick="myFunction()">点我</button>
  <p id="demo"></p>
  
  <script>
      Array.prototype.myUcase = function () {
          for (i = 0; i < this.length; i++) {
              this[i] = this[i].toUpperCase();
          }
      }
  
      var fruits = ["Banana", "Orange", "Apple", "Mango"];
      document.getElementById("demo").innerHTML = fruits;
  
      function myFunction() {
          fruits.myUcase();
          document.getElementById("demo").innerHTML = fruits;
      }
  </script>
  </body>
  ...
  ```

  

