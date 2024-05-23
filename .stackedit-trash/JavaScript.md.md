# JavaScript 基础

## JavaScript介绍

### JavaScript是什么

 1. JavaScript

    是一种运行在客户端（浏览器）的 **编程语言**，实现 **人机交互** 效果

	2. 作用

    - 网页特效（监听用户的一些行为让网页做出对应的反馈）
    - 表单验证（针对表单数据的合法性进行判断）
    - 数据交互（获取后台的数据，渲染到全端）
    - 服务器编程（node.js）

	3. JavaScript的组成

    - ECMAScript：

      规定了js基础语法核心知识。

      - 比如：变量、分支语句、循环语句、对象等等

    - Web APIs：

      - DOM	操作 **文档**，比如对 **页面元素** 进行 **移动、大小、添加删除** 等操作
      - BOM	操作 **浏览器**，比如 **页面弹窗，检测窗口宽度、存储数据到浏览器** 等等

JavaScript权威网站：[[MDN Web Docs (mozilla.org)](https://developer.mozilla.org/zh-CN/)]

### JavaScript 书写位置

- 行内样式

  代码写在标签 **内部**

  语法：

  ```html
  <body>
  	<button onclick="alert('你好，js')">点击</button>
  </body>
  ```

  

- 内部样式

  直接写在 html 文件里面，用 **script** 标签包住

  **规范**：script 标签卸载`</body>`上面

  拓展：`alert('你好，js')` 页面弹出警告对话框

  ```html
  <html>
      <header>
          <!-- 头部代码 -->
      </header>
      <body>
          <!-- 页面代码 -->
          <script>
              alert('你好，js')
          </script>
      </body>
  </html>
  ```

  **script 标签放在 header 里和放在 body 底部里有什么区别？**

  - **放在 header 中**

    你能看到 html 第一时间被加载进来，但页面 body 内容迟迟没有渲染出来。因为在等待 header 标签中 script 脚本的加载，3 秒后，整个页面渲染完成。

  - **放在 body 底部**

    这次 html 内容第一时间渲染完成，随后等待 js 的加载。

  - **总结**

    脚本会 **阻塞** 页面的 **渲染**，所以推荐将其放在 body 底部，因为当解析到 script 标签时，通常页面的大部分内容都已经渲染完成，让用户马上能看到一个非空白页面。

- 外部样式

  代码写在以 `.js`结尾的文件里

  **语法**：通过 **script** 标签，引入到 html 页面中。

  ```html
  <body>
  	<!-- 页面代码 -->
  	<script src="./xx/xx.js"></script>
  </body>
  ```

  `script`标签中间不要写内容，会被 **忽略**

### JavaScript怎么写

了解 JavaScript 注释 写法以及 结束符 通俗写法

- 注释

  - 单行注释

    - 符号：`//`
    - 作用：`//`右边这一行代码会被忽略
    - 快捷键：`CTRL + /`

    ```html
    <script>
        // 这是单行注释的写法
        // 一次只能注释一行
        // 可以重复注释
    </script>
    ```

  - 块注释

    - 符号：`/* */`
    - 作用：在`/*` 和 `*/` 之间的所有内容都会被忽略
    - 快捷键：`shift + alt + a`

    ```html
    <script>
        /* 这是块注释的写法 */
        /*
        	更常见的多行注释写法
        	在里面可以任意换行
            多少行都可以
        */
    </script>
    ```

    

- 结束符

  - **作用**：使用英文的 `;` 代表语句结束
  - **实际情况**：实际开发中，可写 **可不写** ，浏览器（JavaScript引擎）可以自动推断语句的结束位置
  - **现状**：在实际开发中，越来越多的人主张，书写 JavaScript 代码时 **省略** 结束符
  - <font color="red" style="font-weight: 900;">约定</font><font color="red">：为了风格统一，结束符要么每句都写，要么每句都不写（按照团队要求）。</font>

  ```html
  <script>
      alert("1");
      alert("2");
  </script>
  // or
  <script>
      alert("1")
      alert("2")
  </script>
  ```

### JavaScript输入输出

什么是语法：

- 人和计算机打交道的规则约定
- 要按照这个规则去写

输入和输出也可以理解为人和计算机的交互，用户通过键盘、鼠标等向计算机输入信息，计算机处理后再展示结果给用户，这便是一次输入和输出的过程。

- 输出：

  - 语法1：

    ```javascript
    document.write('要输出的内容') // 向网页输出
    ```

    **作用**：向 body 内输出内容

    **注意**：如果输出的内容写的是标签，，也会被解析成网页元素

  - 语法2：

    ```javascript
    alert('要输出的内容') // 向网页输出
    ```

    **作用**：页面弹出警示框

  - 语法3：

    ```js
    console.log('控制台打印')
    ```

    **作用**：控制台输出语法，程序员调试使用

- 输入：

  - 语法：

    ```js
    prompt('请输入内容：')
    ```

    **作用**：显示一个对话框，对话框中包含一条文字信息，用来提示用户输入文字

    效果：![prompt('请输入内容：')](D:\learning notes\Getting started\学习笔记\images\prompt('请输入内容：').png)



JavaScript 代码执行顺序：

- 按 HTML 文档流顺序执行 JavaScript 代码
- **`alert( )`** 和 `**prompt( )`** 它们会 **跳过页面渲染先被执行**



### 字面量

在计算机科学中，字面量（literal）是在计算机中描述 事/物

比如：

- 我年龄是：23。	此时 23 就是 数字字面量
- 'hello world' 字符串字面量
- 还有 `[] `数组字面量、`{} `对象字面量 等等



## 变量

### 变量是什么

变量是计算机中用来 **存储数据** 的“<font color=red>容器</font>”，它可以让计算机变得有记忆。

**注意**：变量不是数据本身，它仅仅是一个容器。可以理解为一个盒子。



### 变量的使用

变量的使用：

1. 声明变量

   要想使用变量，先要 **创建** 变量（也称为声明变量或定义变量）

   **语法**：

   ```js
   let 变量名
   ```

   - 声明变量由两部分构成：声明关键词、变量名（标识）
   - `let` 即关键词（let：允许、许可、让、要），所谓关键词是系统提供的专门用来声明（定义）变量的词语

2. 变量赋值

   定义了一个变量后，你就能够初始化它（赋值）。在变量名之后跟上一个”=”，然后是数值。

3. 更新变量

   变量赋值后，还可以通过简单的给它一个 **不同的值** 来更新它。

   **注意**：`let` 不允许多次声明一个变量

4. 声明多个变量：

   变量赋值后，可以通过简单的给一个不同的值来更新它。

   语法：

   ```js
   let age = 18, name = 'pop'
   ```

### 变量的本质

**变量的本质** 是程序在内存中申请的一块用来存放数据的小空间



### 变量的命名规则与规范

1. 规则：

   **必须遵守**，不遵守则报错

   - 不能用关键字
   - 只能用下划线、字母、数字、$组成，且数字不能开头（符号只有 "_" 和 "$"）
   - 字母严格 **区分大小写**，如 Age 和 age 是不同的变量

2. 规范：

   建议遵守，不强制要求，不遵守也不会报错

   - 起名要有意义
   - 遵守小驼峰命名法
     - **第一个** 单词首字母 **小写**，**后面** 每个单词首字母 **大写**。例如：userName

### 变量拓展

#### `let` 和 `var` 的区别

在较旧的 JavaScript ，使用关键字 `var` 来声明变量，而不是 `let`。
`var` 现在开发中一般不再使用它，只是可能再老版程序中看到它。
`let` 为了解决 `var` 的一些问题.

`var` 声明：

- 可以先使用 再声明（不合理）
- `var` 声明过的变量可以重复声明（不合理）
- 比如变量提升、全局变量、没有块级作用域等等

#### 数组（`Array`）

作用：将 **多个数据** 存储再 **单个变量名** 下

语法：

```js
let arr = []
let 数组名 = [数据1, 数据2, ……, 数据n]
```

**长度**：数组中数据的个数，通过 **`length`** 属性获取



## 常量

概念：在程序运行 **过程中** 其值 **不会改变** 的量

命名规范：与变量一致

使用方法：

```js
// 声明并赋值常量
const G = 9.8
// 输出常量
console.log(G)
```

**注意**：<font color=red>常量不允许重新赋值，声明的时候必须赋值（初始化）</font>

## 数据类型

JavaScript 是一个 **弱数据类型** 的语言

数据类型有：

1. 基本数据类型
   - [number：数字型](# 数字型-Number)
   - [string：字符型](# 字符串-string)
   - [Boolean：布尔型](# 布尔类型-Boolean)
   - [undefined：未定义型](#未定义类型-undefined)
   - [null：空类型](# 空类型-null)
2. 引用数据类型
   - [object：对象](# Object-对象)

### 数字型-`Number`

即数学中的数字，可以是整数、小数、正数、负数。

```js
let age = 18	//整数
let PI = 3.14	//小数
```

数字可以做很对操作，比如：加+、减-、乘*、除/ 等等，所以经常和 **算术运算符** 一起

数学运算符也叫  **算术运算符** ，主要有：

- `+`：求和
- `-`：求差
- `*`：求积
- `/`：求商
- `%`：取模（取余数），常用于判断某数字是否被整除

**运算优先级**：优先级相同时以书从左向右执行。

- 乘、除、取余优先级相同
- 加、减优先级相同
- 乘、除、取余优先级大于加、减
- 使用`()`可以提升优先级
- 总结：先**乘除**后**加减**，有括号**先算括号里面**的

<font color=red>`NaN`（not   a  number）：代表一个计算错误。他是一个不正确的或者未定义的数学操作所得到的结果</font>

### 字符串-`string`

通过 **单引号`"`**、**双引号`"`** 或 **反引号<code>`</code>**包裹的数据都叫字符串，单引号和双引号 **没有** 本质上的 **区别**，推荐使用
单引号。

```js
let str1 = 'hello'
let str2 = "world"
let str3 = `你好，世界！`
let str4 = '123456'
let str5 = ''	// 空字符
```

**注意事项**：

1. 无论单引号或是双引号必须 **成对** 使用
2. 单引号 / 双引号可以 **互相嵌套**，但是**不可以自已嵌套自已**（口诀：外双内单，或者外单内双）
3. 必要时可以使用转义符\，输出单引号或双引号

<font color=red style="font-weight: 700;">字符串拼接：</font>

-  <font color=red>使用 `+` 运算符，可以实现字符串的拼接</font>
- 只要有一个字符串，`+` 运算符就是拼接。

#### 模板字符串

- 使用场景：

  - 拼接 **字符串** 和 **变量**

- 语法：

  - <code>``</code> （反引号）
  - 内容拼接变量时，用 `${}` 包住变量

  ```javascript
  let name = "小明"
  let age = 20
  let introduce = `大家好，我是${name}，今年${age}岁了。`	// 大家好，我是小明，今年20岁了。
  ```

  

### 布尔类型-`Boolean`

​	表示 **肯定** 或 **否定** 时在计算机中对应的是布尔类型数据。
​	它有两个固定的值 **`true`** 和 **`false`**，表示肯定的数据用 `true(真)`，表示否定的数据用 `false(假)`。

```js
let isCool = true
isCool = false
console.log(3 > 4)	// 控制台输出：false
```



### 未定义类型-`undefined`

未定义是比较特殊的类型，只有一个值`undefined`。
只 **声明** 变量，**不赋值** 的情况下，变量的 **默认值** 为`undefined`，一般很少【直接】为某个变量赋值为`undefined`。

```js
let name
console.log(name)	// 控制台输出：undefined
```



### 空类型-`null`

JavaScript 中的 **`null`** 仅仅是一个代表"无”、"空”或“值未知”的特殊值

```js
let name = null
console.log(name)	// 控制台输出：null
```

**`null`** 和 **`undefined`** 区别：

- **`undefined`** 表示没有赋值
- **`nul`** 表示赋值了，但是内容为空

```js
let num
console.log(num + 1)	// 控制台输出：NaN
num = null
console.log(num + 1)	// 控制台输出：1
```

### 日期对象

**日期对象**：**用来表示时间的对象**

**作用**：可以得到当前系统时间

#### 实例化

在代码中发现了 ==**`new`**==关键字时，一般将这个操作称为 ==**实例化**==

- 创建一个时间对象并获取时间

  - 获取当前时间

    ```js
    const date = new Date()
    ```

  - 获得指定时间

    ```js
    const date = new Date('2020-2-20')
    console.log(date)
    ```

#### 日期对象方法

因为日期对象返回的数据不能直接使用，所以需要转换为实际开发中常用的格式

| 方法           | 作用               | 说明                 |
| -------------- | ------------------ | -------------------- |
| getFullYear( ) | 获得年份           | 获取四位年份         |
| getMonth( )    | 获得月份           | 取值为 0 ~ 11        |
| getDate( )     | 获取月份中的每一天 | 不同月份取值也不相同 |
| getDay()       | 获取星期           | 取值为 0 ~ 6         |
| getHours()     | 获取小时           | 取值为 0 ~ 23        |
| getMinutes()   | 获取分钟           | 取值为 0 ~ 59        |
| getSeconds()   | 获取秒             | 取值为 0 ~ 59        |

```js
date.toLocaleString('zh-CN', {month: '2-digit', day: '2-digit', year: 'numeric', hour: '2-digit', minute: '2-digit', second: '2-digit'}).replace(/\//g, '-') //
```



#### 时间戳

如果计算倒计时效果，前面方法无法直接计算，需要借助于时间戳完成

- 什么是时间戳：
  - 是指1970年01月01日00时00分00秒起至现在的 ==**毫秒数**==，它是一种特殊的计量时间的方式

- **算法**：

  - 将来的时间戳 - 现在的时间戳 = 剩余时间毫秒数

  - 剩余时间毫秒数 转换为 剩余时间的 年月日时分秒 就是倒计时时间

  - 比如将来时间戳2000ms-现在时间戳1000ms=1000ms

  - 1000ms转换为就是0小时0分1秒



- 获取时间戳

  - 使用 `getTime( )` 方法：

    ```js
    date.getTime()
    ```

  - **<font color=red>简写 `+new Date( )`</font>**

    ```js
    +new Date()
    ```

  - 使用 `Date.now( )`

    - 无需实例化
    - 但是只能得到当前的时间戳，不能再括号里添加时间

    ```js
    Date.now()
    ```

    

### **数组**（`Array`）：

是一种可以按顺序保存数据的数据类型

1. 声明数组

   ```js
   let 数组名 = [数据1, 数据2, ……, 数据n]
   
   let arr = new Array(数据1, 数据2, ……, 数据n)	// 构造函数
   ```

   数组是按顺序保存的，每个数据都有自己的编号

2. 取值

   ```js
   数组名[下标]
   
   let names = ['小明'，'小刚'，'小红'，'小丽'，'小米]
   names[0]	//小明
   names[1]	//小刚
   ```

   通过下标获取数据

3. 增加

   ```javascript
   let arr = [1, 2, 3, 4];
   
   // 向数组末尾添加新元素
   arr.push(5);
   console.log(arr.push(5))	// 打印添加元素后，数组长度 5
   
   // 向数组开头添加一个或多个新元素
   arr.unshift(0);
   ```

4. 删除

   ```javascript
   let arr = [1, 2, 3, 4, 5];
   
   // 从数组末尾删除元素
   arr.pop();
   
   // 从数组开头删除元素
   arr.shift();
   
   // 删除特定位置的元素
   arr.splice(1, 2); // 从索引1开始删除2个元素
   
   // 删除所有元素
   arr.splice();
   ```

5. 更新（修改）

   ```js
   let arr = [1, 2, 3, 4, 5];
   
   // 修改元素
   arr[2] = 10; // 将索引2的元素修改为10
   ```

6. 查询

   ```javascript
   let arr = [1, 2, 3, 4, 5];
   // 查找元素的索引
   let index = arr.indexOf(3);
   
   // 查找指定条件的元素
   let foundElement = arr.find(item => item > 3); // 查找大于3的第一个元素
   let foundIndex = arr.findIndex(item => item > 3); // 查找大于3的第一个元素的索引
   ```

7. **遍历数组**

   用循环将数组中的每个元素都访问到，一般用for循环

   ```js
   for (let i = 0; i < 数组名.length; i++) {
       数组名[i]
   }
   ```



#### 数组中的方法：

- `indexOf()`：查找数组中某个元素第一次出现的索引。

  用于查找数组中某个元素 **第一次出现** 的索引。如果找到了指定元素，则返回该元素在数组中的索引；如果未找到，则返回 **-1**。

  ```js
  let arr = [1, 2, 3, 4, 5];
  
  let index = arr.indexOf(3);
  console.log(index); // 输出 2，因为 3 的索引是 2
  ```

  如果数组中存在多个相同的元素，`indexOf()` 方法将返回第一个匹配的元素索引。

  

- `lastIndexOf()`：查找数组中某个元素最后一次出现的索引。

  与 `indexOf()` 类似，但是它用于查找数组中某个元素 **最后一次出现**的索引。

  如果找到了指定元素，则返回该元素在数组中最后一次出现的索引；如果未找到，则返回 **-1**。

  ```js
  let arr = [1, 2, 3, 4, 2, 5];
  
  let lastIndex = arr.lastIndexOf(2);
  console.log(lastIndex); // 输出 4，因为 2 最后一次出现的索引是 4
  ```

  

- `map`方法-迭代数组

  `map` 可以遍历数组处理数据，并且 ==**返回新的数组**==

  ```js
  const arr = ['red','blue', 'green']
  const newArr = arr.map(function (item,index) {
  	console.log(item)	// item得到数组元素'pink'	'red'	'blue'
  	console.log(index)	// index得到索引号0 1 2
  	return item + '颜色'
  })
  console.log(newArr)	// ['red颜色'，'blue颜色', 'green颜色']
  ```

- `join` 方法

  - **作用：**`join() `方法用于把数组中的所有元素转换成一个字符串

  - 语法：

    ```js
    const arr = ['red颜色'，'blue颜色', 'green颜色']
    console.log(arr.join(''))	// red颜色blue颜色green颜色
    ```

    数组元素是通过参数里面指定的分隔符进行分隔的，**空字符串`''`**，则所有元素之间都 **没有任何字符**。
    
    

- `filter`

  - 作用：提供了一种便捷的方式来筛选数组中的元素，以满足特定的条件

  - 语法：

    ```js
    arr.filter(function(element) {
      return 筛选条件
    })
    
    // 示例
    let arr = [1, 2, 3, 4, 5];
    
    let evenNumbers = arr.filter(function(element) {
      return element % 2 === 0;
    });
    
    console.log(evenNumbers); // 输出 [2, 4]
    
    ```

    传递给 `filter` 方法的回调函数应该返回一个布尔值，用来指示是否保留当前元素在最终结果中。

    

- `some()`：检查数组中是否有至少一个元素满足指定条件。

  用于检查数组中是否至少有一个元素满足指定条件。

  它会对数组中的每个元素执行提供的测试函数，如果某个元素满足测试函数的条件，那么 `some()` 将返回 `true`；否则返回 `false`。

  ```javascript
  let arr = [1, 3, 5, 7, 8];
  
  let hasEvenNumber = arr.some(function(element) {
    return element % 2 === 0;
  });
  
  console.log(hasEvenNumber); // 输出 true，因为数组中存在偶数 8
  ```

  `some()` 方法通常用于检查数组中是否至少有一个元素满足某种条件，如果满足则执行相应的操作。

  

- `every()`：检查数组中的所有元素是否满足指定条件。

  用于检查数组中的所有元素是否满足指定条件。

  它会对数组中的每个元素执行提供的测试函数，如果数组中所有元素都满足测试函数的条件，那么 `every()` 将返回 `true`；否则返回 `false`。

  ```javascript
  let arr = [2, 4, 6, 8];
  
  let allEvenNumbers = arr.every(function(element) {
    return element % 2 === 0;
  });
  
  console.log(allEvenNumbers); // 输出 true，因为数组中所有元素都是偶数
  ```

- 更多方法查看：[更多数组方法](内置构造函数方法.html)

#### 遍历数组

- `for...of`

  是在 JavaScript 中用来遍历可迭代对象的循环语句。它能够遍历数组、字符串、Map、Set等可迭代的数据结构，提供了一种简洁且直观的循环方式。

  ```js
  let arr = [1, 2, 3, 4, 5];
  
  for (let num of arr) {
    console.log(num)
  }
  ```

  `for...of` 循环遍历了数组 `arr` 中的每个元素，并将其依次输出到控制台。

  `for...of` 在遍历对象时并不适用，对于遍历对象的属性，可以使用 `for...in` 循环。

- `forEach`

  是 JavaScript 中数组对象的一个内建方法，用于对数组中的每个元素执行提供的回调函数。使用 `forEach` 方法可以简洁地遍历数组，并对每个元素执行相同的操作。

  ```javascript
  let arr = [1, 2, 3, 4, 5];
  
  arr.forEach(function(item) {
    console.log(item)
  })
  ```

  `forEach` 方法遍历了数组 `arr` 中的每个元素，并对每个元素执行了一个输出操作。

  - 需要注意的是，`forEach` 方法提供的回调函数可以接收三个参数：当前元素的值、当前元素的索引和被遍历的数组本身。

    ```js
    arr.forEach(function(item, index, arr) {}
    ```

    

  - 与传统的 `for` 循环相比，`forEach` 方法提供了一种更简洁的方式来遍历数组，特别适用于需要对数组中的每个元素执行相同操作的情况。

### `Object`-对象 

- 对象(`object`)：JavaScript 里的一种数据类型
- 可以理解为是一种 **无序** 的数据集合，注意数组是有序的数据集合
- 用来描述某个事物，例如描述一个人
  - 一人有姓名、年龄、性别等信息、还有吃饭睡觉打代码等功能
  - 如果用多个变量保存则比较散，用对象比较统一

#### 声明对象

```js
let 对象名 = {}

let 对象名 = new Object()
```



#### 对象的组成

**对象有属性和方法组成**：

- 属性：信息或叫特征（名词）。比如手机尺寸、颜色、重量等

  - 数据 **描述性** 的信息称为属性
  - 属性是成对出现的，包括属性名和值，中间用英文“:”分隔
  - 多个属性之间用英文“,"分隔
  - 属性就是依附在对象上的变量（外面是变量，对象内是属性）
  - 属性名可以使用" "或' '，**一般情况下省略**，除非名称遇到特殊符号如空格、中横线等

- 方法：功能或叫行为（动词）。比如手机打电话、发短信、玩游戏…

  - 数据行为性的信总称为方法，如跑步、唱歌等，一股是动词性的，其本质是函致。
  - 方法是由方法名和函数两部分构成，它们之间使用：分隔
  - 多个属性之间使用英文，分隔
  - 方法是依附在对象中的函数
  - 方法名可以使用" "或' '，一般情况下省略，除非名称遇到特殊符号如空格、中横线等

  

  ```js
  let 对象名 = {
      属性名：属性值，
      方法名：函数
  }
  
  let person = {
      name: 'andy',
      sayHi: function() {
          document.wrtie('hi~')
      }
  }
  ```

  

#### 对象的增加

```js
对象.新属性名 = 新值
```

添加一个新属性，值为新值

#### 对象的删除

```js
delete 对象.属性名
```

删除一个已有属性

#### 对象的修改

```js
对象.属性名 = 新值
```

修改一个属性的值为新值

#### 对象的查询

语法

```js
对象.属性
对象['属性']
```

查询一个属性的值



#### 对象的函数调用

```js
对象.方法()

let person = {
    name: 'andy',
    sayHi: function(x, y) {
        document.wrtie('hi~')
    }
}

person.sayHi(1, 2)	// 调用sayHi
```



#### 对象的遍历

```js
for (let key in Obj) {
    console.log(key + " : " + Obj[key]);
}
```

- 一般不用这种方式遍历数组、主要是用来遍历对象
- `for in`语法中的`key`是一个变量，在循环的过程中依次代表对象的属性名
- 由于`key`是变量，所以必须使用`[]`语法解析
- 一定记住：`key`是获得对象的属性名，对象名`[key]`是获得属性值



### 检测数据类型

通过 **`typeof`** 关键字检测数据类型

- 作为运算符：**`typeof  x`**（常用方法）
- 函数形式：**`typeof(x)`**

换言之，有括号和没有括号，得到的结果是一样的，所以直接使用 **运算符** 的写法。

```js
let name = "小明"
let age = 20
let isCool = true
let und
let nu = null
console.log(`typeof name: ${typeof name}；typeof age: ${typeof age}；typeof isCool: ${typeof isCool}；typeof und: ${typeof und}；typeof nu: ${typeof nu}；`)	
// 控制台输出：typeof name: string；typeof age: number；typeof isCool: boolean；typeof und: undefined；typeof nu: object；
```



### 类型转换

#### 隐式转换

某些运算符被执行时，系统内部自动将数据类型进行转换，这种转换称为隐式转换。

**规则**：

- +号两边只要有一个是字符串，都会把另外一个转成字符串
- **除了 `+` 以外** 的算术运算符，比如 `- ~ * /` 等都会把数据转成数字类型

**缺点**：

- 转换类型不明确，靠经验才能总结

**小技巧**：

- <font color=red>`+`号作为正号解析可以转换成数字型</font>
- <font color=red>任何数据和字符串相加结果都是字符串</font>



### 显示转换

​	编写程序时过度依，系统内部的隐式转换是不严禁的，因为隐式转换规律并不清晰，大多是靠经验总结的规律。
​	为了避免因隐式转换带来的问题，通常根逻辑需要对数据进行显示转换。

概念：自己写代码告诉系统该转换成什么类型



**转换为数字型**：

- `Number`（数据）：

  - 转换成数字类型
  - 如果字符串内容包含 **非数字**，转换失败时结果为 **`NaN`（not a number）**，即不是一个数字
  - `NaN` 也是 `number` 类型的数据，代表非数字

- `parseInt`（数据）

  - 只保留整数

    ```js
    console.log(parseInt('12px'))		// 12
    console.log(parseInt('12.56px'))		// 12
    console.log(parseInt('abc12.56px'))		// NaN
    ```

    

- `parseFloat`（数据）

  - 可以保留小数

    ```js
    console.log(parseFloat('12px'))		// 12
    console.log(parseFloat('12.56px'))		// 12.56
    console.log(parseFloat('abc12.56px'))		// NaN
    ```



## 运算符

### 赋值运算符

对变量进行赋值的运算符：

- 赋值运算符：**`=`** 将等号 **右边** 的值赋予 **给左边**，要求 **左边** 必须是一个 **容器**
- 其他赋值运算符：
  - `+=`：将 **左边** 的值 + 右边的值 后的 **结果** 赋予 **给左边**
  - `-=`：将 **左边** 的值 - 右边的值 后的 **结果** 赋予 **给左边**
  - `*=`：将 **左边** 的值 * 右边的值 后的 **结果** 赋予 **给左边**
  - `/=`：将 **左边** 的值 / 右边的值 后的 **结果** 赋予 **给左边**
  - `%=`：将 **左边** 的值对 **右边的值取模** 后的 **结果** 赋予 **给左边**

### 一元运算符

众多的 JavaScript 的运算符可以根据所需表达式的个数，分为一元运算符、二元运算符、三元运算符

- 二元运算符：

  - 例：

    ```js
    let num = 10 + 20
    ```

- 一元运算符

  - **`+`**：正号（`+x`）
  - **`-`**：负号（`-x`）
  - **`++`**：自增
    - <font color=red>前自增：`++x`（<b>先加</b>再用）</font>
    - <font color=red>后自增：`x++`（**先用**再加）</font>
  - **`--`**：自减
    - <font color=red>前自减：`--x`（**先减**再用）</font>
    - <font color=red>后自减：`x--`（**先用**再减）</font>

### 比较运算符

比较两个数据的大小、是否相等

- **`>`**：左边是否大于右边
- **`<`**：左边是否小于右边
- **`>=`**：左边是否大于等于右边
- **`<=`**：左边是否小于等于右边
- **`==`**：<font color=red>左右两边 **值** 是否 **相等**</font>
- **`!=`**：<font color=red>左右两边 **值** 是否 **不相等**</font>
- **`===`**：<font color=red>左右两边 **值和类型** 是否都 **相等**</font>
- **`!==`**：左右两边是否 **不全相等**

返回结果为 **`Boolean`** 类型

### 逻辑运算符

逻辑运算符用来解决多重条件判断

| 符号 |  名称  | 日常读法 |
| :--: | :----: | :------: |
|  &&  | 逻辑与 |   并且   |
| \|\| | 逻辑或 |   或者   |
|  !   | 逻辑非 |   取反   |

### 运算符优先级

| 优先级 | 运算符     | 顺序                 |
| ------ | ---------- | -------------------- |
| 1      | 小括号     | ( )                  |
| 2      | 一元运算符 | ++  --  !            |
| 3      | 算术运算符 | 先 * / % 后 + -      |
| 4      | 关系运算符 | >   >=   <   <=      |
| 5      | 相等运算符 | ==   !=   ===   !\== |
| 6      | 逻辑运算符 | 先 && 后 \|\|        |
| 7      | 赋值运算符 | =                    |
| 8      | 逗号运算符 | ,                    |



## 语句

**表达式**：是可以被求值的代码，JavaScript 引擎会将其计算出一个结果

**语句**：是一段可以执行的代码



**分支语句**：

- **`if`** 分支语句

  - 三种使用：单分支、双分支、多分支

  - 语法：

    ```js
    if (条件1) {
        满足条件1要执行的语句
    } else if (条件2) {
        满足条件2要执行的语句
    } else {
        前面条件都不满足时要执行的语句
    }
    ```

    

- **三元运算符**

  - 就是双分支if语句，可以书写 **简单** 的分支语句

  - 语法：

    ```js
    条件 ? 满足条件执行的代码 : 不满足条件执行的代码
    ```

  - 一般用来取值

- **`switch`** 语句

  ```js
  switch (数据) {
  	case 值1：
          代码1
          break
      case 值2：
          代码2
          break
      default：
          代码n
          break
  }
  ```

  - 找到跟小括号里数据 **全等** 的 `case` 值，并执行里面的代码
  - 若没有 **全等** 的，则执行 `default` 中的代码
  - <font color=red>`switch case` 语句一般用于 **等值判断**，**不适合** 于 **区间判断**</font>
  - <font color=red>`switch case` 一般需要配合 **`break`** 关键字使用没有`break`会造成 **case穿透**</font>



**循环语句**：

重复执行一些操作

- 循环三要素：
  1. 变量起始值
  2. 终止条件（没有终止条件，循环会一直执行，造成死循环）
  3. 变量变化量（用自增或者自减）

- **`while`**：

  在……期间，所以 **while循环** 就是在 **满足条件** 期间，重复执行一些代码

  - 基本语法：

    ```js
    while (循环条件) {
        要重复的代码（循环体）
    }
    ```

    

- **`for`**

  作用：重复执行代码

  ```js
  for (变量起始值; 终止条件; 变量变化量) {
      循环体
  }
  
  for(;;) {}	// 无限循环
  ```

  - <font color=red>**for**循环的主要作用：**遍历对象**</font>

    ```js
    // 遍历数组
    for (let 临时变量 of 数组) {	// of：临时变量获取数组中的元素
        循环体
    }
    for (let 临时变量 in 数组) {	// in：临时变量获取数组中元素的下标
        循环体
    }
    ```

    

- **循环的退出**

  作用：结束循环

  - **`break`**：退出整个循环
  - **`continue`**：结束本次循环，进行下一次循环



**for循环和while循环有什么区别**：

- 当 **明确** 了循环的 **次数** 的时候推荐使用 **for** 循环
- 当 **不明确** 循环的 **次数** 的时候推荐使用 **while** 循环





## 函数

作用：代码复用

`function`：是被设计为 **执行特定任务** 的代码块

函数可以把具有相同或相似逻辑的代码“包裹”起来，通过函数调用执行这些被“包裹”的代码逻辑，这么做的优势是有利于**精简代码方便复用**。



### 基础

#### 函数的声明语法：

```js
function 函数名(参数1 = 默认值，参数2 = 默认值，……，参数n = 默认值) {	// 参数可以为空
	函数体
    return
}
```

函数的命名规范：

- 和变量命名基本一致
- 尽量小驼峰式命名法
- 前缀应该为动词



##### 函数的调用：

```js
函数名(参数1，参数2，……，参数n)	// 没有参数时，括号内留空
```



##### 函数的参数

- 形参

  形参是函数定义中声明的参数，它们是函数定义中列出的变量名。在函数体内部，这些变量被用来引用传递给函数的实际参数的值。

- 实参

  实参是在函数调用时传递给函数的值。它们是函数调用时真正传递的参数，作为输入被传递给函数执行。

- 区别

  - 形参是函数定义中声明的变量，用于接收函数调用时传入的参数值。
  - 实参是函数调用时实际传递的参数值。

总的来说，形参和实参是函数定义和函数调用中的两种概念，形参是函数的参数列表中的占位符，实参是函数调用时传递给函数的具体值。





##### 函数的返回值

函数的返回值指的是当函数被调用执行后，函数执行完毕并返回的结果。

函数可以根据需要返回不同类型的值，比如数字、字符串、对象等。



- **定义返回值**

  在JavaScript中，可以使用 `return` 语句来定义函数的返回值。当函数执行到 `return` 语句时，将立即返回指定的值，并结束函数的执行。

  ```js
  function add(x, y) {
      return x + y;
  }
  
  let result = add(3, 5); // result 将会得到 add 函数返回的值 8
  ```

  

- **返回多个值**

  在像 JavaScript 这样的语言中，函数一次**只能**返回**一个值**。但可以通过返回一个对象、数组等数据结构来实现类似于返回多个值的效果。

  ```js
  function calculate(x, y) {
      return {
          sum: x + y,
          difference: x - y
      };
  }
  
  let result = calculate(5, 3); // result 将会得到 { sum: 8, difference: 2 }
  ```

  

- **没有返回值**

  如果函数没有明确使用 `return` 语句返回值，或者 `return` 后面没有跟任何表达式，那么函数将会返回 `undefined`。

  ```js
  function greet(name) {
      console.log("Hello, " + name);
      // 没有明确的返回语句，函数将返回 undefined
  }
  
  let result = greet("John"); // result 将会是 undefined
  ```

- **捕获返回值**

  在函数调用时，可以通过将返回值赋给一个变量来捕获函数的返回值。

  ```js
  function getGreeting(name) {
      return "Hello, " + name;
  }
  
  let greeting = getGreeting("Alice"); // greeting 将会得到 "Hello, Alice"
  ```

函数返回值是函数执行完毕后返回的结果，可以根据具体的业务逻辑和需求来设计和使用返回值。



##### 细节补充

- 两个 **相同** 的函数后面的会 **覆盖前面** 的函数

- 在到 javascript 中实参的个数和形参的个数可以不一致

  - 如果形参过多会自动填上 `undefined`

  - 如果实参过多那么多余的实参会被忽略（函数内部有一个`arguments`，里面装着所有的实参）

- 函数一旦碰到 `return` 就不会在往下执行了函数的结束用 `return `

### 匿名函数

具名函数：

- 声明：`function fn() {}`
- 调用：`fn()`



匿名函数：

- `function() {}`

**没有名字的函数，无法直接使用。**
使用方式：

- 函数表达式

  - 将匿名函数 **赋值给一个变量**，并且通过 **变量名称进行调用** ，将这个称为 **函数表达式**

    ```js
    // 声明函数
    let fn = function() {}
    
    // 调用
    fn()
    ```

  - 与具名函数的区别

    1. 具名函数声明会在代码执行之前进行预解析，因此可以在声明之前调用函数；而函数表达式必须在创建后才能使用。
    2. 具名函数在函数内部有效，可以在函数体内部通过函数名称引用自身；函数表达式中的具名函数只在函数内部有效，函数体外部无法通过函数名称引用自身。
    3. 匿名函数表达式的变量名是可选的，而具名函数表达式的变量名是必须的。

- 立即执行函数

  - 作用：避免全局变量的污染

  - 语法：

    ```js
    // 方式一
    (function () {函数体})();
    
    // 方式二
    (function () {函数体}());
    
    // 不用调用，立即执行
    ```

    

    <font color=red><b>注意</b>：多个立即执行函数要用：隔开，要不然会报错</font>

  - 与具名函数的区别

    1. **命名**：具名函数有函数名，而立即执行函数通常是匿名的。
    2. **调用方式**：具名函数可以在任何需要调用的地方多次调用，而立即执行函数在定义后立即执行一次，不会再次调用。



## JS 执行机制

JavaScript 语言的一大特点就是 ==**单线程**==，也就是说，==**同一个时间只能做一件事**==。

这是因为 Javascript 这门脚本语言诞生的使命所致——JavaScript 是为处理页面中用户的交互，以及操作

DOM 而诞生的。比如对某个 DOM 元素进行添加和删除操作，不能同时进行。 应该先进行添加，之

后再删除。

单线程就意味着，所有任务需要排队，前一个任务结束，才会执行后一个任务。这样所导致的问题是：

如果 JS 执行的时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉。



为了解决这个问题，利用多核 CPU 的计算能力，HTML5 提出 Web Worker 标准，允许 JavaScript 脚本创建多个

线程。于是，JS 中出现了 ==**同步**== 和 ==**异步**==。 

- **同步**

  前一个任务结束后再执行后一个任务，程序的执行顺序与任务的排列顺序是一致的、同步的。比如做饭的同步做法：要烧水煮饭，等水开了（10分钟之后），再去切菜，炒菜。 

- **异步**

  你在做一件事情时，因为这件事情会花费很长时间，在做这件事的同时，你还可以去处理其他事

  情。比如做饭的异步做法，在烧水的同时，利用这10分钟，去切菜，炒菜。

**<font color=red>他们的本质区别： 这条流水线上各个流程的执行顺序不同。</font>**



### 同步任务

同步任务都在主线程上执行，形成一个**执行栈。**

<img src="images/执行栈.png" alt='执行栈' style="height:200px;border:1px solid #67a9ff">

### **异步任务**

JS 的异步是通过回调函数实现的。

一般而言，异步任务有以下三种类型:

1、普通事件，如 `click`、`resize` 等

2、资源加载，如 `load`、`error` 等

3、定时器，包括 `setInterval`、`setTimeout` 等

异步任务相关添加到 ==**任务队列**== 中（任务队列也称为消息队列）

<div style="width:200px;text-align:center;font-size:20px"><div style="margin:5px auto;width:160px;height:40px;line-height:40px;background-color:#95B3D7;border:2px solid #385D8A">任务队列</div><div style="width:200px;height:60px;line-height:60px;background-color:#95B3D7;border:2px solid #385D8A">fn</div></div>



### 执行过程

1. 先执行 ==**执行栈中的同步任务**==。

2. 异步任务放入任务队列中。

3. 一旦执行栈中的所有同步任务执行完毕，系统就会按次序读取任务队列中的异步任务，于是被读取的异步任务结束等待状态，进入执行栈，开始执行

<img src="images/JS任务执行过程.png" alt='JS任务执行过程' style="width:400px;border:1px solid #67a9ff">

<img src="images/JS任务执行过程2.png" alt='JS任务执行过程2' style="width:800px;">

由于主线程不断的重复获得任务、执行任务、再获取任务、再执行，所以这种机制被称为==**事件循环(event loop)**==。



# Web APIs

操作DOM、BOM。比如 控制网页元素交互等各种网页交互效果

## Web APIs 基本认知

作用：就是使用 JS 去操作 html 和浏览器
分类：**DOM** (文档对象模型)、**BOM** (浏览器对象模型)



### DOM

**DOM** (Document Object Model——文档对象模型) 是用来呈现以及与任意 HTML 或 XML 文档交互的APl

即：**DOM** 是浏览器提供的一套专门用来 **操作网页内容** 的功能

**作用**：开发网页内容特效和实现用户交互



**DOM**树：

- 将HTML文档以树状结构直观的表现出来，称之为 文档树 或 DOM 树

- 描述网页内容关系的名词

- 作用：**文档树直观的体现了标签与标签之间的关系**

- 演示：

  - html 结构

    ```javascript
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>标题</title>
    </head>
    <body>
        文本
    	<a href="">链接名</a>
    	<div id="" class="">文本</div>
    </body>
    </html>
    ```

  - DOM 树

    ```mermaid
    	graph TB
    	subgraph DOM树
    		A([document])
    		B(HTML)
    		C1(head)
    		C2(body)
    		D1(meta)
    		D2(title)
    		D3(更多...)
    		D4((文本))
    		D5(a)
    		D6(div)
    		D7(更多...)
    		E1{{conoent}}
    		E2((标题))
    		E3{{href}}
    		E4((链接名))
    		E5{{id}}
    		E6{{class}}
    		E7((文本))
    		A---B
    		B---C1---D1---E1
    		B---C2---D4
    		C1---D2---E2
    		C1---D3
    		C2---D5---E3
    		C2---D6---E5
    		C2---D7
    		D5---E4
    		D6---E6
    		D6---E7
    	end
    	subgraph 图例
    		G(元素节点)
    		H{{属性节点}}
    		I((文字节点))
    	end
    	
    ```

  - DOM对象（重要）

    - 浏览器根据 html 标签生成的 JS 对象

      - 所有的标签属性都可以在这个对象上面找到

      - 修改这个对象的属性会自动映射到标签身上

    - DOM的核心思想

      - 把网页内容当作 **对象** 来处理

    - document对象

      - 是 DOM 里提供的一个 **对象**
      - 所以它提供的属性和方法都是 **用来访问和操作网页内容的**。例：`document.write( )`
      - 网页所有内容都在document里面



#### 获取DOM对象

查找元素DOM元素就是利用JS选择页面中标签元素

- 根据 CSS 选择器来获取DOM 元素

  - 选择匹配的 **第一个** 元素

    ```js
    document.querySelector('css选择器')
    ```

    **参数**：包含一个或多个有效的CSS选择器 ==**字符串**==

    **返回值**：CSS选择器匹配的 **第一个元素**，一个 HTMLElement 对象。没匹配到则返回 **`null`**

    

  - 选择匹配的多个元素

    ```js
    document.querySelectorAll('一个或多个css选择器')
    
    document.querySelectorAll('ul li')
    ```

    **参数**：包含一个或多个有效的CSS选择器 ==**字符串**==

    **返回值**：CSS选择器匹配的 ==**NodeList 对象集合**==

    **得到的是一个 ==伪数组==**：

    - 有长度有索引号的数组

    - 但是没有`pop()`、`push()`等数组方法

    想要得到里面的每一个对象，则需要遍历`for`的方式获得。

- 其他获取方法：

  ```js
  // 根据id获取一个元素
  document.getElementById('nav')
  // 根据 标签获取一类元素 获取页面 所有div
  document.getElementsByTagName('div')
  // 根据 类名获取元素 获取页面 所有类名为w的
  document.getElementsByClassName('w')
  ```



#### 操作元素内容

DOM 对象都是根据标签生成的，所以操作标签，本质上就是操作 DOM 对象。

就是操作对象使用的点语法。

如果想要修改标签元素的里面的 ==**内容**==，则可以使用如下几种方式：

-  对象.innerText 属性
  - 将文本内容添加/更新到任意标签位置
  - 显示==纯文本==，不解析标签
- 对象.innerHTML 属性
  - 将文本解析后，添加/更新到任意标签位置



#### 操作元素属性

- 操作元素 **常用**属性

  通过 JS 设置/修改标签元素属性，比如通过 `src`更换图片

  语法：

  ```js
  对象.属性 = 值
  ```

  

- 操作元素 **样式** 属性

  还可以通过 JS 设置/修改标签元素的样式属性。

  - 比如通过轮播图小圆点自动更换颜色样式

    

  1、**通过 style 属性操作 CSS**

  ```js
  对象.style.样式属性 = 值
  
  // 对于用 “-” 符号连接的属性，将连接符去掉，改用小驼峰写法
  div.style.backgroundColor = 'pink'
  ```

  修改样式通过style属性引出

  如果属性有`-`连接符，需要转换为 ==**小驼峰命名法**==

  赋值的时候，需要的时候不要忘记加 ==**CSS 单位**==

  

  2、通过操作类名（className）操作CSS

  如果修改的样式比较多，直接通过 `style` 属性修改比较繁琐，可以通过借助于CSS类名的形式。

  ```js
  //active是一个css类名
  元素.className = 类名
  
  // 通过操作类名（className）操作CSS
  元素.className = 'oneclass'
  ```

  

  **注意**：

  - 由于`class`是关键字，所以使用`className`去代替

  - `className`是使用新值 **换** 旧值，如果需要添加一个类，需要保留之前的类名

  

  3、通过 classList 操作类控制CSS

  为了解决`className`容易覆盖以前的类名，可以通过`classList`方式追加和删除类名

  ```js
  // 追加类名anotherclass
  元素.classList.add('类名')
  // 如果img元素上有类名anotherclass，则移除，如果没有，则添加
  元素.classList.toggle('类名')
  // 移除类名oneclass
  元素.classList.remove('类名')
  ```

  

- 操作 **表单元素** 属性

  表单很多情况，也需要修改属性，比如点击眼睛，可以看到密码，本质是把表单类型转换为文本框

  正常的有属性有取值的跟其他的标签属性没有任何区别

  **<font color=red>innerHTML 得不到表单的内容</font>**

  ```js
  元素.value	// 表单元素的值
  元素.type		// 表单元素的类型
  ```

  **表单属性中==添加就有效果==，==移除就没有效果==，一律==使用布尔值表示==如果为 `true` 代表添加了该属性，如果是 `false` 代表移除了该属性**。比如：`disabled`、`checked`、`selected`

- 自定义属性

  **标准属性**：标签天生自带的属性比如 `class`、`id`、`title` 等，可以直接使用点语法操作比如：`disabled`、`checked`、`selected`

  **自定义属性**：

  - 在html5中推出来了专门的`data-`自定义属性

  - 在标签上一律以`data-`开头

  - 在DOM对象上一律以dataset对象方式获取

  ```html
  <body>
  	<div data-id="1"  data-spm="不知道">1</div>
      <div data-id="2">2</div>
      <div data-id="3">3</div>
      <div data-id="4">4</div>
      
      <script>
      	const one = document.querySelector('div')
          const two = document.querySelector('div:nth-child(2)')
          console.log(one.dataset)		// DOMStringMap {id: '1', spm: '不知道'}
          console.log(one.dataset.id)		// 1
          console.log(one.dataset.spm)	// 不知道
          console.log(two.dataset)		// DOMStringMap {id: '2'}
      </script>
  </body>
  ```





#### 定时器-间歇函数

定时器函数可以开启和关闭定时器

1. 开启定时器

   ```js
   setInterval(函数，间隔时间)
   ```

   一旦开始，就不会停歇

   函数名字==**不需要加括号**==

   ==**定时器返回的是一个id数字**==

2. 关闭定时器

   每一个定时器都会返回一个编号

   通过编号关闭定时器

   ```js
   let 变量名 = setInterval(函数, 间隔时间)
   clearInterval(变量名)
   ```





#### 事件监听

事件是在编程时系统内发生的 **动作** 或者发生的事情。比如用户在网页上 **单击** 一个按钮

事件监听：就是让程序检测是否有事件产生，一旦有事件触发，就立即调用一个函数做出响应，也称为绑定事件或者

注册事件。比如鼠标经过显示下拉菜单，比如点击可以播放轮播图等等

- 语法

  ```js
  元素对象.addEventListenner('事件类型', 要执行的函数)
  ```

- 三要素

  - **事件源**：那个 dom 元素被事件触发了，要获取 dom 元素
  - **事件类型**：用什么方式触发，比如鼠标单击 `click`、鼠标经过 `mouseover` 等
  - **事件调用的函数**：要做什么事

- 注意：

  1. 事件类型要 ==**加引号**==
  2. **函数是点击之后再去执行，每次点击都会执行一次**

- 事件监听版本

  - DOM L0

    事件源.on事件=function( ){ }

  - DOM L2

    事件源.addEventListener(事件，事件处理函数)

  - 区别

    `on`方式会被覆盖，`addEventListener`方式可绑定多次，拥有事件更多特性，推荐使用

  - 发展史

    - DOML0：是DOM的发展的第一个版本；L：level
    - DOML1：DOM 级别1 于1998年10月1日成为W3C推荐标准
    - DOML2：使用addEventListeneri注册事件
    - DOML3：DOM3级事件模块在DOM2级事件的基础上重新定义了这些事件，也添加了一些新事件类型

##### 事件类别

- 鼠标事件：由鼠标触发

  - `click`：鼠标点击
  - `mouseenter`：鼠标经过
  - `mouseleave`：鼠标离开

- 焦点事件：表单获得光标

    - `focus`：获得焦点
    - `blur`：失去焦点

- 键盘事件：由键盘触发

  - `Keydown`：键盘按下触发

  - `Keyup`：键盘抬起触发

- 文本事件：表单输入触发

  - `input`：用户输入事件

1. 鼠标事件（Mouse Events）：用户与页面交互时触发，如点击（`click`）、移动（`mousemove`）、悬停（`mouseover`）、离开（`mouseleave`）等。

   ```js
   element.addEventListener('click', function(event) {
     // 处理点击事件
   });
   ```

   

2. 键盘事件（Keyboard Events）：用户在页面上按下或释放键盘按键时触发，如按键按下（`keydown`）、按键释放（`keyup`）等。

   ```js
   document.addEventListener('keydown', function(event) {
     // 处理按键按下事件
   });
   ```

   

3. 表单事件（Form Events）：涉及到表单元素的交互时触发，如提交表单（`submit`）、重置表单（`reset`）等。

   ```js
   formElement.addEventListener('submit', function(event) {
     // 处理表单提交事件
   });
   ```

   

4. 文档加载事件（Document Loading Events）：页面加载过程中触发，如文档加载完成（`DOMContentLoaded`）、资源加载完成（`load`）等。

   ```js
   document.addEventListener('DOMContentLoaded', function(event) {
     // 页面加载完成后执行操作
   });
   ```

   - DOMContentLoaded

     - 当初始的HTML文档被完全加载和解析完成之后，DOMContentLoaded事件被触发，而无需等待样式表、图等完全加载

     - 事件名：`DOMContentLoaded`

     - 监听页面DOM加载完毕：

       - 给document添加DOMContentLoaded事件

       ```js
       document.addEventListener('DOMContentLoaded', function() {})
       ```

       

   - load

     - 加载外部资源（如图片、外联 CSS 和 JavaScript 等）加载完毕时触发的事件

     - 事件名：`load`

     - 监听页面所有资源加载完毕：

       - 给window添加load事件

       ```js
       window.addEventListener('load', function() {})
       ```

     - 注意：不光可以监听整个页面资源加载完毕，也可以针对某个资源绑定1od事件

     - 给img添加load事件

       ```js
       img.addEventListener('load', function() {})
       ```

       

5. 视图事件（View Events）：与页面的可见部分相关的事件，如窗口大小改变（`resize`）、滚动（`scroll`）等。

   ```js
   window.addEventListener('resize', function(event) {
     // 处理窗口大小改变事件
   });
   ```

   - resize

     - 会在窗口尺寸改变的时候触发事件

     - **<font color=red>获取元素宽高</font>**:

       - 获取元素的可见部分宽高（不包含边框，`margin`，滚动条等）

       - **<font color=red>`clientWidth` 和 `clientHeight`</font>**

         <img src="images/页面-clientWidth和clientHeight.png" alt="页面-clientWidth和clientHeight" style="width:400px;" />

   - scroll

     - `scrollLeft` 和 `scrollTop`

       - 获取被卷去的大小
       - 获取元素内容往左、往上滚出去看不到的距离
       - 这两个值是可**读写**的

       <img src="images/scroll页面关系.png" alt="scroll页面关系" style="width:400px" />

       |            属性             |          作用          | 说明                                                     |
       | :-------------------------: | :--------------------: | -------------------------------------------------------- |
       |    scrollLeft和scrollTop    |   被卷去的头部和左侧   | 配合页面滚动来用，可读写                                 |
       | clientWidth 和 clientHeight |   获得元素宽度和高度   | 不包含border,margin，滚动条 用于js获取元素大小，只读属性 |
       |  offsetWidth和offsetHeight  |   获得元素宽度和高度   | 包含border、padding，滚动条等，只读                      |
       |    offsetLeft和offsetTop    | 获取元素距离自己定位父 | 级元素的左、上距离                                       |

       

6. 触摸事件（Touch Events）：针对触摸屏设备的触摸交互事件，如触摸开始（`touchstart`）、触摸移动（`touchmove`）、触摸结束（`touchend`）等。

   ```js
   element.addEventListener('touchstart', function(event) {
     // 处理触摸开始事件
   });
   ```

   

7. 拖放事件（Drag and Drop Events）：处理拖放操作的事件，如拖动开始（`dragstart`）、拖动结束（`dragend`）、放置（`drop`）等。

   ```js
   dragSource.addEventListener('dragstart', function(event) {
     // 处理拖动开始事件
   });
   ```

   

8. 媒体事件（Media Events）：与音频、视频等媒体元素相关的事件，如播放（`play`）、暂停（`pause`）、播放结束（`ended`）等。

   ```js
   videoElement.addEventListener('play', function(event) {
     // 处理播放事件
   });
   ```

   

9. Websocket事件（WebSocket Events）：与WebSocket通信相关的事件，如连接建立（`open`）、接收消息（`message`）、连接关闭（`close`）等。

   ```js
   websocket.addEventListener('message', function(event) {
     // 处理接收消息事件
   });
   ```



##### 事件对象

也是个对象，这个对象里有事件触发时的相关信息

例如：鼠标点击事件中，事件对象就存了鼠标点在哪个位置等信息



- 获取事件对象

  - 在事件绑定的回调函数的第一个参数就是事件对象
  - 一般命名为`event`、`ev`、`e`

  ```js
  元素.addEventListener('click', function (e) {})
  ```



**<font color=red>部分常用事件对象属性</font>**

- `type`
  - 获取当前的事件类型
- `clientX/clientY`
  - 获取光标相对于浏览器 **可见窗口** 左上角的位置
- `offsetX/offsetY`
  - 获取光标相对于当前 DOM 元素左上角的位置
- `key`
  - 用户按下的键盘键的值
  - 现在不提倡使用`keyCode`



##### 环境对象

**环境对象**：指的是函数内部特殊的 **变量`this`**，它代表着当前函数运行时所处的环境

**作用**：弄清楚 `this` 的指向，可以让代码更简洁

- 函数的调用方式不同，`this`指代的对象也不同
- **【谁调用，`this`就是谁】**是判断 `this` 指向的粗略规则
- 直接调用函数，其实相当于是 window 函数，所以 `this` 指代 `window`



##### 回调函数

如果将函数 A 做为参数传递给函数 B 时，称函数 A 为 **回调函数**



### DOM事件进阶

#### 事件流

==**事件流**== 指的是事件完整执行过程中的流动路径

##### 事件流和两个阶段

==**捕获阶段**== 和 ==**冒泡阶段**==

<img src="images/事件流.png" alt="事件流" style="zoom:50%;" />

说明：假设页面里有个div，当触发事件时，会经历两个阶段，分别是捕获阶段、冒泡阶段

简单来说：捕获阶段是 从父到子 ，冒泡阶段是 从子到父

**<font color=red>实际工作都是使用事件冒泡为主</font>**



##### 事件捕获

概念：从 DOM 的根元素开始去执行对应的事件（从外到里）

- 事件捕获需要写对应代码才能看到效果

- 代码：

  ```js
  DOM.addEventListener(事件类型，事件处理函数，是否使用捕获机制)
  ```

  

- 说明：

  - `addEventListener`：第三个参数传入`true`代表是捕获阶段触发（很少使用）
  - 若传入`false`代表冒泡阶段触发，默认就是`false`
  - 若是用L0事件监听，则只有冒泡阶段，没有捕获

##### 事件冒泡

概念：当一个元素的事件被触发时，同样的事件将会在该元素的所有祖先元素中依次被触发。这一过程被称为事件冒泡

- 简单理解：当一个元素触发事件后，会依次向上调用所有父级元素的 ==**同名事件**==
- 事件冒泡是默认存在的
- L2事件监听第三个参数是`false`，或者默认都是冒泡

##### 阻止冒泡

- 问题：因为默认就有冒泡模式的存在，所以容易导致事件影响到父级元素

- 需求：若想把事件就限制在当前元素内，就需要阻止事件冒泡

- 前提：阻止事件冒泡需要拿到事件对象

- 语法：

  ```js
  事件对象.stopPropagation()
  
  // 示例
  e.stopPropagation()
  ```

- **注意：**此方法可以阻断事件流动传播，不光在冒泡阶段有效，捕获阶段也有效



##### 解绑事件

- `on` 事件方式，直接使用 `null` 覆盖偶就可以实现事件的解绑

  语法

  ```js
  btn.onclick = function () {
  	alert('点击了')
  }
  
  btn.onclick = null
  ```

  

- `addEventListener`方式

  - 必须使用：`removeEventListener(事件类型，事件处理函数，[获取捕获或者冒泡阶段])`

  示例

  ```js
  function fn() {
  	alert('点击了')
  }
  btn.addEventListener('click', fn)
  // L2 事件移除解绑
  btn.removeEventListener('click', fn)
  ```



- 鼠标经过事件的区别

  鼠标经过事件：

  - `mouseover` 和 `mouseout` 会有冒泡效果
  - `mouseenter` 和 `mouseleave` 没有冒泡效果（推荐）

**<font color=red>两种注册事件的区别</font>**

- 传统on注册(L0)
  - 同一个对象，后面注册的事件会覆盖前面注册（同一个事件）
  - 直接使用`null`覆盖偶就可以实现事件的解绑
  - 都是冒泡阶段执行的
- 事件监听注册(L2)
  - 语法：`addEventListener (事件类型，事件处理函数，是否使用捕获)`
  - 后面注册的事件不会覆盖前面注册的事件（同一个事件）
  - 可以通过第三个参数去确定是在冒泡或者捕获阶段执行
  - 必须使用 `removeEventListener (事件类型，事件处理函数，获取捕获或者冒泡阶段)`
  - 匿名函数无法被解绑

#### 事件委托

事件委托 是利用事件流的特征解决一些开发需求的知识技巧

- 优点：减少注册次数，可以提高程序性能

- 原理：事件委托其实是利用事件冒泡的特点。

  - 给 ==**父元素注册事件**==，当触发子元素的时候，会冒泡到父元素身上，从而触发父元素的事件

  ```js
  const ul = document.querySelector('ul')
  ul.addEventListener('click', function(event) {
  	if (event.target.tagName === 'LI') {
  		event.target.style.color = 'red'
  	}
  })
  ```



#### DOM节点

- DOM节点
  - DOM 树里每一个内容都称之为节点
- 节点类型
  - 元素节点
    - 所有的标签比如 `body`、`div`
    - `html` 是根节点
  - 属性节点
    - 所有的属性比如 `href`
  - 文本节点
    - 所有的文本
  - 其他



##### 查找节点

- **节点关系**：针对的找亲戚返回的都是对象
  - 父节点
  - 子节点
  - 兄弟节点



- **父节点查找**：

  - `parentNode` 属性
  - 返回最近一级的父节点找不到返回为 `null`

  ```js
  子元素.parentNode
  ```

  



- 子节点查找：

  - `childNodes`
    - 获得所有子节点、包括文本节点（空格、换行）、注释节点等
  - **`children`属性（重点）**
    - 仅获得所有元素节点
    - 返回的还是一个伪数组

  ```js
  父元素.children
  ```





- 兄弟关系查找：

  - 下一个兄弟节点

    `nextElementSibling` 属性

  - 上一个兄弟节点

    `previousElementSibling` 属性



##### 增加节点

1. 创建节点

   即创造出一个新的网页元素，再添加到网页内，一般先创建节点，然后插入节点

   - 创建元素节点方法：

     ```js
     // 创造一个新的元素节点
     document.createElement('标签名')
     ```

     

2. 追加节点

   要想在界面看到，还得插入到某个父元素中

   - 插入到父元素的最后一个子元素：

     ```js
     // 插入到这个父元素的最后
     父元素.appendChild(要插入的元素)
     ```

   - 插入到父元素中某个子元素的前面

     ```js
     // 插入到父元素中某个子元素的前面
     父元素.insertBefore(要插入的元素，在哪个元素前面)
     ```

3. 克隆节点

   - 特殊情况下，新增节点，按照如下操作：

     - 复制一个原有的节点
     - 把复制的节点放入到指定的元素内部

   - 克隆节点

     ```js
     // 可控一个已有的元素节点
     元素.cloneNode(布尔值)
     ```

   `cloneNode` 会克隆出一个跟原标签一样的元素，括号内传入布尔值

   - 若为`true`，则代表克隆时会包含后代节点一起克隆
   - 若为`false`，则代表克隆时不包含后代节点
   - 默认为`false`



##### 删除节点

若一个节点在页面中已不需要时，可以删除它

在 JavaScript 原生 DOM 操作中，要删除元素必须通过 **父元素删除**

- 语法

  ```js
  父元素.removeChild(要删除的元素)
  ```

- 注：

  - 如不存在父子关系则删除不成功
  - 删除节点和隐藏节点 `display:none`有区别的：隐藏节点还是存在的，但是删除，则从 html 中删除节点

### M端事件

==**移动端**== 也有自己独特的地方。比如触屏事件 touch（也称触摸事件），Android 和 IOS 都有。

- 触屏事件touch(也称触摸事件)，Android和IOS都有。

- touch对象代表一个触摸点。触摸点可能是一根手指，也可能是一根触摸笔。触屏事件可响应用户手指（或触控笔)对屏幕或者触控板操作。

- 常见的触屏事件如下：

  | 触屏touch事件 | 说明                                                       |
  | ------------- | ---------------------------------------------------------- |
  | touchstart    | 手指**<font color=red>触摸到</font>**一个 DOM 元素时触发   |
  | touchmove     | 手指在一个 DOM 元素上**<font color=red>滑动时</font>**触发 |
  | touchend      | 手指从一个 DOM 元素上**<font color=red>移开时</font>**触发 |



#### JS 插件

- 插件：就是别人写好的一些代码，只需要复制对应的代码，就可以直接实现对应的效果

- 学习插件的基本过程

  - 熟悉官网，了解这个插件可以完成什么需求

    https://www.swiper.com.cn/

  - 看在线演示，找到符合自己需求的demo

    https://www.swiper.com.cn/demo/index.html

  - 查看基本使用流程

    https://www.swiper.com.cn/usage/index.html

  - 查看AP文档，去配置自己的插件

    https://www.swiper.com.cn/api/index.html

  - 注意：多个swiperl同时使用的时候，类名需要注意区分 





### BOM

#### Windows 对象

##### BOM（浏览器对象模型）

BOM ( Browser Object Model ) 是浏览器对象模型

<img src="images/BOM.png" alt="BOM"  alt="BOM" style="width:700px; border: 1px solid #3ab7e9">

- window 对象是一个全局对象，也可以说是 JavaScript 中的顶级对象
- 像`document、alert( )、console.log( )`这些都是 window 的属性，基本 BOM 的属性和方法都是 window 的。
- 所有通过var定义在全局作用域中的变量、函数都会变成 window 对象的属性和方法
- window 对象下的属性和方法调用的时候可以省略 window



##### 定时器-延迟函数

JavaScript 内置的一个用来让代码延迟执行的函数，叫 `setTimeout`

- **语法**:

  ```js
  setTimeout(回调函数, 等待的毫秒数)
  ```

  - `setTimeout` 仅仅只执行一次，所以可以理解为就是把一段代码延迟执行, 平时省略 window

- **清除延时函数**:

  ```js
  let timer = setTimeout(回调函数, 等待的毫秒数)
  clearTimeout(timer)
  ```

- **注意点**

  - 延时器需要等待，所以后面的代码先执行
  - 每一次调用延时器都会产生一个新的延时器

- **两种定时器对比：**执行的次数

  - 延时函数：执行一次
  - 间歇函数：每隔一段时间就执行一次,除非手动清除

##### location 对象

- `location` 的数据类型是对象，它拆分并保存了 URL 地址的各个组成部分

- **常用属性和方法：**

  - **href** 属性获取完整的 URL 地址，对其赋值时用于地址的跳转

    ```js
    // 可以得到当前文件URL地址
    console.log(location.href)
    // 可以通过js方式跳转到目标地址
    location.href = 'http://www.baidu.com'
    ```

    

  - **search** 属性获取地址中携带的参数，符号 ？后面部分

    ```js
    console.log(location.search)
    ```

    

  - **hash** 属性获取地址中的啥希值，符号 # 后面部分

    ```js
    console.log(location.hash)
    ```

    - 后期vue路由的铺垫，经常用于不刷新页面，显示不同页面，比如 网易云音乐

    

  - **reload** 方法用来刷新当前页面，传入参数 `true` 时表示强制刷新

    ```js
    <button>点击刷新</button>
    <script>
    	let btn document.querySelector('button'
    	btn.addEventListener('click',function () {
             // 刷新当前页面
             location.reload()
            
             // 强制刷新 类似 ctrL + f5
    		location.reload(true)
    		
    	})
    </script>
    ```



##### navigator对象

- `navigator` 的数据类型是对象，该对象下记录了浏览器自身的相关信息

- **常用属性和方法：**

  - 通过 `userAgent` 检测浏览器的版本及平台

  ```
  // 检测 userAgent（浏览器信息）
  !(function () {
  	const userAgent = navigator.userAgent
  	// 验证是否为Android或iPhone
  	const android = userAgent.match(/(Android);?[\s\/]+([\d.]+)?/)
  	const iphone = userAgent.match(/(iPhone\sOS)\s([\d_]+)/)
  	
  	// 如果是Android或iPhone，则跳转至移动站点
  	if (android || iphone) {
  		location.href = 'http://www.baidu.com' 
  	}
  })()
  ```



##### histroy 对象

- `history` 的数据类型是对象，主要管理历史记录， 该对象与浏览器地址栏的操作相对应，如前进、后退、历史记录等

- | histroy对象方法 | 作用                                                      |
  | --------------- | --------------------------------------------------------- |
  | back()          | 可以后退功能                                              |
  | forward()       | 前进功能                                                  |
  | go(参数)        | 前进后退功能，参数如果是1前进1个页面，如果是-1后退1个页面 |

- `history` 对象一般在实际开发中比较少用，但是会在一些 OA 办公系统中见到。



#### 本地存储

- 以前页面写的数据一刷新页面就没有了
- 随着互联网的快速发展，基于网页的应用越来越普遍，同时也变的越来越复杂，为了满足各种各样的需求，会经常性在本地存储大量的数据，HTML5规范提出了相关解决方案。
- 1、数据存储在 **用户浏览器** 中
- 2、设置、读取方便、甚至页面刷新不丢失数据
- 3、容量较大，`sessionStorage` 和 `localStorage` 约 5M 左右
- 常见的使用场景：
  https://stackedit.cn/app#/页面刷新数据不丢失



##### 本地存储分类- `localStorage`

- **作用:** 可以将数据永久存储在本地(用户的电脑), 除非手动删除，否则关闭页面也会存在

- **特性：**

  - 可以多窗口（页面）共享（同一浏览器可以共享）
  - 以键值对的形式存储使用

- 语法

  - **存储数据：**

    ```js
    localStorage.setItem(key, value)
    ```

  - **获取数据：**

    ```js
    localStorage.getItem(key)
    ```

  - **删除数据：**

    ```js
    localStorage.removeItem(key)
    ```



##### 本地存储分类- `sessionStorage`

- **特性：**
  - 生命周期为关闭浏览器窗口
  - 在同一个窗口(页面)下数据可以共享
  - 以键值对的形式存储使用
  - 用法跟 `localStorage` 基本相同



本地存储只能存 **字符串** 



##### 存储复杂数据类型

- 本地只能存储字符串，无法存储复杂数据类型。

- **解决：**需要将复杂数据类型 **转换** 成 `JSON` 字符串，在存储到本地

  ```js
  const goods = {
      name: '小米14',
      price: 1999
  }
  
  localStorage.setItem('goods', JSON.stringify(goods))
  ```

  将复杂数据转换成 `JSON` 字符串 **存储** 本地存储中

- **问题：**因为本地存储里面取出来的是字符串，不是对象，无法直接使用

  ```js
  console.log(localStorage.getItem('goods'))	// {"name":"小米14,"price":1999} 字符串类型
  ```

- **解决：**把取出来的字符串转换为对象

  - **语法：JSON.parse(JSON字符串)**

  ```js
  const obj = JOSN.parse(localStorage.getItem('goods'))
  console.log(obj)
  ```





# JavaScript 进阶

## 作用域

作用域（scope）：规定了变量能够被访问的“范围”，离开了这个“范围”变量便不能被访问

作用域分为：

- [局部作用域](# 局部作用域)
- [全局作用域](# 全局作用域)

### 局部作用域

局部作用域分为 **[函数作用域](# 函数作用域)** 和 **[块作用域](# 块作用域)**。

#### 函数作用域

在函数内部声明的变量只能在函数内部被访问，外部无法直接访问

```js
<script>
	function getsum(){
		//函数内部是函数作用域，属于局部变量
		const num 10
	}
	console.log(num)	//此处报错，函数外部不能使用局部作用域变量
</script>
```



**总结**：

1. 函数内部声明的变量，在函数外部无法被访问

2. 函数的参数也是函数内部的局部变量

3. 不同函数内部声明的变量无法互相访问

4. 函数执行完毕后，函数内部的变量实际被清空了、



#### 块作用域

在 JavaScript 中使用`{}`包裹的代码称为代码块，代码块内部声明的变量外部将【**有可能**】无法被访问。

```js
for (let t = 1; t <= 6; t++) {
	// t只能在该代码块中被访问
	console.log(t)	//正常
)
// 超出了t的作用域
console.log(t)	//报错
```



**总结**：

1. `let` 声明的变量会产生块作用域，`var`不会产生块作用域

2. `const`声明的常量也会产生块作用域

3. 不同代码块之间的变量无法互相访问

4. 推荐使用`let`或`const`



### 全局作用域

<font color=red>\<script> 标签</font> 和 <font color=red>.js文件</font> 的【最外层】就是所谓的全局作用域，在此声明的变量在函数内部也可以被访问。全局作用域中声明的变量，任何其它作用域都可以被访问



**注意**：

1. 为window对象动态添加的属性默认也是全局的，不推荐！

2. 函数中未使用任何关键字声明的变量为全局变量，不推荐！！！

3. 尽可能少的声明全局变量，防止全局变量被污染



### 作用域链

作用域链本质上是底层的 **变量查找机制**。

- 在函数被执行时，会 **优先查找当前** 函数作用域中查找变量
- 如果当前作用域查找不到则会依次 **逐级查找父级作用域** 直到全局作用域



**总结**：

1. 嵌套关系的作用域串联起来形成了作用域链

2. 相同作用域链中按着从小到大的规则查找变量
3. 子作用域能够访问父作用域，父级作用域无法访问子级作用域



### 垃圾回收机制

#### 垃圾回收机制介绍

**垃圾回收机制 (Garbage Collection) 简称 GC**

JS中 **内存** 的分配和回收都是 **自动完成** 的，内存在不使用的时候会被 **垃圾回收器** 自动回收。

正因为垃圾回收器的存在，许多人认为JS不用太关心内存管理的问题

但如果不了解JS的内存管理机制，同样非常容易成内存泄漏（内存无法被回收）的情况

不再用到的内存，没有及时释放，就叫做 **内存泄漏**



#### 内存的生命周期

JS环境中分配的内存, 一般有如下 ==**生命周期**==：

1. ==**内存分配**==：当声明变量、函数、对象的时候，系统会自动为他们分配内存

2. ==**内存使用**==：即读写内存，也就是使用变量、函数等

3. ==**内存回收**==：使用完毕，由 **垃圾回收器** 自动回收不再使用的内存

4. 说明：
   - 全局变量一般不会回收(关闭页面回收)；
   - 一般情况下 **局部变量的值**, 不用了, 会被 **自动回** 收掉

==**内存泄漏**==：程序中分配的 **内存** 由于某种原因程序 **未释放** 或 **无法释放** 叫做内存泄漏



#### JS垃圾回收机制- **算法说明**

堆栈空间分配区别：

1. 栈（操作系统）：由 **操作系统自动分配释放** 函数的参数值、局部变量等，基本数据类型放到栈里面。

2. 堆（操作系统）：一般由程序员分配释放，若程序员不释放，由 **垃圾回收机制** 回收。**复杂数据类型** 放到堆里面。

两种常见的浏览器 **垃圾回收算法** ：**[引用计数法](# 引用计数法)** 和 **[标记清除法](# 标记清除法)**



##### 引用计数法

IE采用的引用计数算法, 定义“ **内存不再使用** ”，就是看一个 **对象** 是否有指向它的引用，没有引用了就回收对象算法：

1. 跟踪记录被 **引用的次数**

2. 如果被引用了一次，那么就记录次数1，多次引用会 **累加 ++**

3. 如果减少一个引用就 **减1 --**

4. 如果引用次数是 **0**，则释放内存

**缺点**：

引用计数法存在一个致命的问题：**嵌套引用**（循环引用）

如果两个对象 **相互引用** ，尽管他们已不再使用，垃圾回收器不会进行回收，导致内存泄露。

```js
function fn(){
	let o1 {}
	let o2 {}
	01.a=02
	02.a=01
	return '引用计数无法回收'
}
fn()
```

因为他们的引用次数永远不会是0。这样的相互引用如果说很大量的存在就会导致大量的内存泄露



##### **标记清除法**

现代的浏览器已经不再使用引用计数算法了。

现代浏览器通用的大多是基于 **标记清除算法** 的某些改进算法，总体思想都是一致的。

核心：

1. 标记清除算法将“不再使用的对象”定义为“ **无法达到的对象** ”。

2. 就是从 **根部**（在JS中就是全局对象）出发定时扫描内存中的对象。 凡是能从 **根部到达** 的对象，都是还 **需要使用** 的。

3. 那些 **无法** 由根部出发触及到的 **对象被标记** 为不再使用，稍后进行 **回收**。



```js
function fn() {
	let o1 = {}
	let o2 = {}
	o1.a = o2
	o2.a = o1
	return '引用计数无法回收'
}
fn()
```

根部已经访问不到，所以自动清除



### 闭包

**概念**：一个函数对周围状态的引用捆绑在一起，内层函数中访问到其外层函数的作用域

简单理解：**闭包 =  内层函数 + 外层函数的变量** 

```js
function outer(){
	const a = 1
	function f(){
	console.log(a)
	}
	f()
}
outer()
```

<img src="images/闭包.png" alt="闭包" style="width: 400px">





####**闭包作用**

封闭数据，提供操作，外部也可以访问函数内部的变量

**闭包的基本格式**:

```js
function outer() {
	let i = 1
	function fn() {
		console.log(i)
    }
	return fn
}
const fun = outer()
fun()	// 1
// 1外层函数使用内部函数的变量
```

简单写法：

```js
/1简约写法
function outer() {
	let i = 1
	return function () {
		console.log(i)
    }
}
const fun = outer()
fun()	// 调用fun	1
// 外层函数使用内部函数的变量
```



#### **闭包应用**

实现数据的私有

要做个统计函数调用次数，函数调用一次，就++

```js
let count = 1
function fn() {
    count++
    console.log(count)
}
fn()	// 2
fn()	// 3
```

<font color=red>但是，这个`count `是个全局变量，很容易被修改</font>

**可以使用闭包，实现数据的私有**：

```js
function fn() {
    let count = 1
    function fn2() {
        count++
        console.log(count)
    }
    return fn2
}
const result = fn()
result()	// 2
result()	// 3
```

这样实现了数据私有，无法直接修改 `count`



### 变量提升

变量提升是 JavaScript 中比较“奇怪”的现象，它允许在变量声明之前即被访问（仅存在于`var`声明变量）

```js
<script>
	// 提前访问变量
    console.log(str + 'world!')	// undefinedwoirld!
	// 声明变量
	var str = 'hello '
</script>
```



注意：

1. 变量在未声明即被访问时会报语法错误

2. 变量在`var`声明之前即被访问，变量的值为 `undefined`

3. **`let/const`** 声明的变量 **不存在变量提升**

4. 变量提升出现在相同作用域当中

5. **实际开发中推荐先声明再访问变量**

## 函数进阶

### 函数提升

函数提升与变量提升比较类似，是指函数在声明之前即可被调用。

```js
// 调用函数
fn()
//声明函数
function fn() {
	console.log('声明之前即被调用...')
}
```

但是，函数表达式不存在提升现像：

```js
// 不存在提升现象
bar()	// 错误
var bar = function () {
	console.log('函数表达式不存在提升现像..')
}
```



总结：

1. 函数提升能够使函数的声明调用更灵活

2. 函数表达式不存在提升的现象

3. 函数提升出现在相同作用域当中



### 函数参数

1. [动态参数](# 动态参数)
2. [剩余参数](# 剩余参数)

#### 动态参数

`arguments` 是函数内部内置的伪数组变量，它包含了调用函数时传入的所有实参

```js
// 计算所有参数的和
function sum() {
    let sum = 0
    for(let i = 0; i < arguments.lenght; i++) {
        sum += arguments[i]
    }
    console.log(sum)
}

sum(1,2,3)		// 6
sum(2,3,4,5,6)	// 20
```



**总结**：

1. `arguments` 是一个伪数组，只存在于函数中

2. `arguments` 的作用是动态获取函数的实参

3. 可以通过`for`循环依次得到传递过来的实参



#### 剩余参数

剩余参数允许将一个不定数量的参数表示为一个数组

1. `...` 是语法符号，置于最末函数形参之前，用于获取多余的实参

2. 借助 `...` 获取的剩余实参，是个**真数组**

```js
function fn(a, ...b) {
    console.log(a)	// 'x'
    console.log(b)	// ['y', 'z']
}

fn('x', 'y', 'z')
```



开发中，提倡多使用 **剩余参数。**

### 展开运算符

展开运算符`...`,将一个数组进行展开

```js
const arr = [1,2,3,4,5]
console.log(...arr)	// 1 2 3 4 5
```

**不会修改原数组**

**典型运用场景： 求数组最大值(最小值)、合并数组等**

```js
// 求最值
const arr = [1,2,3,4,5]
console.log(Math.max(...arr))
console.log(Math.min(...arr))

// 合并数组
const arr1 = [1,2,3]
const arr2 = [4,5,6]
const arr3 = [...arr1, ...arr2]
console.log(arr3)	// [1,2,3,4,5,6]
```



#### 展开运算符/剩余参数

剩余参数：**函数参数使用，得到真数组**

展开运算符：**数组中使用**，数组展开



### 箭头函数

**目的：**引入箭头函数的目的是更简短的函数写法并且不绑定`this`，箭头函数的语法比函数表达式更简洁

**使用场景：**箭头函数更适用于那些本来 **需要匿名函数的地方**

1. [基本语法](# 基本语法)

2. [箭头函数参数](# 箭头函数参数)

3. [箭头函数this](# 箭头函数的this)



#### 基本语法

- 语法一：

  ```js
  // 普通函数
  const fn = function() {
  	函数体
  }
  fn()
  
  // 箭头函数
  const fn = () => {
      函数体
  }
  fn()
  ```

- 语法二：**只有一个参数可以省略小括号**

  ```js
  // 普通函数
  const fn = function(x) {
  	return x + x
  }
  console.log(fn(1))	// 2
  
  // 箭头函数
  const fn = x => {
      return x + x
  }
  console.log(fn(1))	// 2
  ```

  

- 语法三：**如果函数体只有一行代码，可以写到一行上，并且无需写 return 直接返回值**

  ```js
  const fn = (x, y) => x + y
  console.log(fn(1, 2))	// 3
  ```

  

- 语法四：**加括号的函数体返回对象字面量表达式**

  ```js
  const fn = name => ({name: name})
  console.log(fn('John'))	// {name: 'John'}
  
  const fn1 = name => ({name})
  console.log(fn1('peter')) // {name: "peter"}
  ```



#### 箭头函数参数

1. 普通函数有 `arguments` 动态参数

2. 箭头函数 **没有** `arguments` 动态参数，但是**有** 剩余参数 `...args`

```js
const fn = (...arr) => {
    let sum = 0
    for(let i = 0; i < arr.lenght; i++) {
        sum += arr[i]
    }
    return sum
}

console.log(fn(1,2,3))	// 6
```



###箭头函数的this

在箭头函数出现之前，每一个新函数根据它是被 **如何调用的** 来定义这个函数的`this`值， 非常令人讨厌。

**箭头函数不会创建自己的`this`**，它只会从自己的作用域链的上一层沿用`this`。

```js
console.log(this)	// 此处为window
const sayHi function () {
	console.log(this)	// 普通函数指向调用者此处为window
}
btn.addEventListener('click',function () {
	console.log(this)	// 当前this 指向btn
})

// 箭头函数
const sayHi = () => {
	console.log(this)	// 箭头函数此处为window
}
btn.addEventListener('click', () => {
	console.log(this)//当前this指向window
})

const user = {
	name:'小明'，	
    // 该箭头函数中的 this 为函数声明环境中 this 一致
	walk: () => {
		console.log(this)	// 指向window 不是user
    }
}
user.walk()


const user = {
	name:'小明'，
	sleep: function () {
		console.log(this)	// 指向user
		const fn = () = {
			console.log(this)	// 指向user 该箭头函数中的 this 与 sLeep 中的 this 一致
    	}
		// 调用箭头函数
		fn()
	}
}
user.sleep()
```



在开发中【使用箭头函数前需要考虑函数中 this 的值】，事件回调函数使用箭头函数时，this 为全局的 window，因此**DOM事件回调函数为了简便，还是不太推荐使用箭头函数**



## 解构赋值

解构赋值是一种快速为变量赋值的简洁语法，本质上仍然是为变量赋值。

**分为**：

- [数组解构](# 数组解构)
- [对象解构](# 对象解构)



### 数组解构

数组解构是将数组的单元值快速批量赋值给一系列变量的简洁语法。

#### 基本语法

1. 赋值运算符 `=` 左侧的` [] `用于批量声明变量，右侧数组的单元值将被赋值给左侧的变量

2. 变量的顺序对应数组单元值的位置依次进行赋值操作

```js
const arr = [1, 2, 3]
const [a, b, c] = arr
console.log(a)	// 1
console.log(b)	// 2
console.log(c)	// 3
---------------------------
const [a, b, c] = [1, 2, 3]
console.log(a)	// 1
console.log(b)	// 2
console.log(c)	// 3
```



- 交换2个变量

  ```js
  let a = 1
  let b = 3;	// 这里必须有分号 ；
  [b, a] = [a. b]
  console.log(a)	// 3
  console.log(b)	// 1
  ```

-  **变量多 单元值少的情况：**

  ```js
  const [a, b, c, d] = ['x', 'y', 'z']
  console.log(a)	// x
  console.log(b)	// y
  console.log(c)	// z
  console.log(d)	// undefined
  ```

  变量的数量大于单元值数量时，多余的变量将被赋值为 `undefined`

- **变量少 单元值多的情况：**

  ```js
  const [a, b, c] = ['i', 'j', 'k', 'l']
  console.log(a)	// i
  console.log(b)	// j
  console.log(c)	// k
  ```

-  **利用剩余参数解决变量少 单元值多的情况：**

  ```js
  const [a, b, ...tel] = ['i', 'j', 'k', 'l', 'm', 'n']
  console.log(a)	// i
  console.log(b)	// j
  console.log(tel)	// ['k', 'l', 'm', 'n']
  ```

  剩余参数返回的还是一个数组

-  **防止有undefined传递单元值的情况，可以设置默认值：**

  ```js
  const [a = 'x', b = 'y'] = ['i']
  console.log(a)	// i
  console.log(b)	// y
  ```

  允许初始化变量的默认值，且只有单元值为 undefined 时默认值才会生效

- **按需导入，忽略某些返回值：**

  ```js
  const [a, , c, d] = ['i', 'j', 'k', 'l']
  console.log(a)	// i
  console.log(b)	// k
  console.log(c)	// l
  ```

- **支持多维数组的结构：**

  ```js
  const [a, b] = ['i', ['j', 'k', 'l']]
  console.log(a)	// i
  console.log(b)	// ['j', 'k', 'l']
  
  const [a, [b, c]] = ['i', ['j', 'k']]
  console.log(a)	// i
  console.log(b)	// j
  console.log(c)	// k
  ```

  

### 对象解构

对象解构是将对象属性和方法快速批量赋值给一系列变量的简洁语法

#### 基本语法

1. 赋值运算符 `=` 左侧的 `{}` 用于批量声明变量，右侧对象的属性值将被赋值给左侧的变量

2. 对象属性的值将被赋值给与属性名 **相同的** 变量

3. 注意解构的变量名不要和外面的变量名冲突否则报错

4. 对象中找不到与变量名一致的属性时变量值为 `undefined`

```js
const user = {
    name: '小明',
    age: 18
}
const {name, age} = user
console.log(name)	// 小明
console.log(age)	// 18
```



- **给新的变量名赋值：**

  可以从一个对象中提取变量并同时修改新的变量名

  ```js
  const user = {
      name: '小明',
      age: 18
  }
  // 把 原来的 name 变量 重命名为 uname
  
  const {name: uname, age} = user
  console.log(uname)	// 小明
  console.log(age)	// 18
  ```

  冒号表示“什么值：赋值给谁”

- **数组对象解构**

  ```js
  const pig = [{
      name: '佩奇',
      age: 6
  }]
  const [{name, age}] = pig
  console.log(name, age)
  ```

- **多级对象解构**

  ```js
  const pig = {
  name: '佩奇',
  family: {
  mother: '猪妈妈',
  father: '猪爸爸',
  brother: '乔治'
  },
  age: 6
  }
  
  const {name, family: {mother, father, brother}} = pig
  
  
  ```

  

## 深入对象

### 创建对象的三种方式

1. **利用对象字面量创建对象**

   ```js
   const a = {
       name: 'piter'
   }
   ```

2. **利用 `new Object` 创建对象**

   ```js
   const a = new Object({name: 'John'})
   ```

3. **利用[构造函数](# 构造函数)创建对象**

### 构造函数

*构造函数 ：**是一种特殊的函数，主要用来初始化对象

**使用场景：**常规的 {...} 语法允许创建一个对象。比如创建了一个对象，继续创建另一个对象还需要重新写一

遍，此时可以通过 **构造函数** 来 **快速创建多个类似的对象**。

```js
function people(name, age, gender) {
    this.name = name
    this.age = age
    this.gender = gender
}

// 创建John
const John = new people('John', 15, '男')
// 创建Smith
const Smith = new people('Smith', 17, '男')
```

构造函数在技术上是常规函数。

不过有两个约定：

1. 它们的命名以 **大写字母开头**。

2. 它们只能由 `new` 操作符来执行。

**说明**：

1. 使用 `new` 关键字调用函数的行为被称为 **实例化**

2. 实例化构造函数时没有参数时可以省略 `()`

3. 构造函数内部无需写`return`，返回值即为新创建的对象

4. 构造函数内部的 `return` 返回的值无效，所以不要写`return`

5. `new Object()`  `new Date()` 也是实例化构造函数



- **实例化执行过程**

  - 说明：

    1. 创建新对象

    2. 构造函数`this`指向新对象

    3. 执行构造函数代码，修改`this`，添加新的属性

    4. 返回新对象

### 实例成员&静态成员

#### 实例成员

**实例成员：**通过构造函数创建的对象称为实例对象，实例对象中的属性和方法称为实例成员。

说明：

1. ==**实例对象的属性和方法即为实例成员**==

2. 为构造函数传入参数，动态创建结构相同但值不同的对象

3. 构造函数创建的实例对象彼此独立互不影响。



#### **静态成员：**

**静态成员：**构造函数的属性和方法被称为静态成员

说明：

1. ==**构造函数的属性和方法被称为静态成员**==

2. 一般公共特征的属性或方法静态成员设置为静态成员

3. 静态成员方法中的 this 指向构造函数本身

## 内置构造函数

内置构造函数是预定义的构造函数，用于创建相应类型的对象。这些构造函数提供了创建内置对象（例如数组、日期、正则表达式等）的能力，以及执行类型转换和其他操作。

一些常见的内置构造函数：

1. `Array`：用于创建数组对象。
2. `Date`：用于创建表示日期和时间的对象。
3. `RegExp`：用于创建正则表达式对象，用于对字符串进行模式匹配。
4. `String`：用于创建字符串对象。
5. `Number`：用于创建数值对象。
6. `Boolean`：用于创建布尔对象。
7. `Object`：用于创建普通对象。
8. `Function`：用于创建函数对象。

**引用类型**：

- Object，Array，RegExp，Date 等

**包装类型**：

- String，Number，Boolean 等



### Object

#### 三个常见的静态方法

想要获得对象中的属性和值可以使用 `for...in`：

```js
const O = {name: 'John', age: 25}

for (let k in o) {
    console.log(k)	// 属性
    console.log(k[O])	// 值
}
```



1. `Object.keys`

   **作用**：`**Object.keys` 静态方法获取对象中 **所有属性（键）**

   ```js
   const O = {name: 'John', age: 25}
   const arr = Object.keys(O)	
   console.log(arr)	// ['name', 'age']
   ```

   **返回值是一个数组**

2. `Object.values`

   **作用：**`Object.values` 静态方法获取对象中**所有属性值**

   ```js
   const O = {name: 'John', age: 25}
   const arr = Object.values(O)	
   console.log(arr)	// ['John', 25]
   ```

   **返回值是一个数组**

3. `Object. assign`

   - **作用：**`Object. assign` 静态方法常用于 **对象拷贝**

     ```js
     // 把对象O 拷贝给Obj
     const O = {name: 'John', age: 25}
     const Obj = {}
     Object.assign(Obj, O)
     console.log(Obj)	// {name: 'John', age: 25}
     ```

     

   - 经常使用的场景给对象添加属性

     ```js
     // 给对象O 新增属性
     const O = {name: 'John', age: 25}
     Object.assign(O, { gender: '男' })
     console.log(O)	// {name: 'John', age: 25, gender: '男'}
     ```



- 更多方法查看：[更多对象方法](内置构造函数方法.html)

### Array

#### 常见方法

1. reduce

   **作用：**`reduce` 返回函数累计处理的结果，经常用于求和等

   ```js
   // arr.reduce(function(累计值，当前元素[，索引号][，源数组]){}，起始值) 方法对数组中的每个元素执行一个由您提供的reducer函数，将其结果汇总为单个返回值。
   const arr = [1, 2, 3, 4, 5]
   const sum = arr.reduce((prev, item) => prev + item, 0)
   console.log(sum) // 15
   ```

   **参数：**起始值可以省略，如果写就作为第一次累计的起始值

   **累计值参数：**

   1. 如果有起始值，则以起始值为准开始累计， 累计值 = 起始值

   2. 如果没有起始值， 则累计值以数组的第一个数组元素作为起始值开始累计

   3. 后面每次遍历就会用后面的数组元素 累计到 **累计值** 里面 （类似求和里面的 sum ）

- 更多方法查看：[更多数组方法](内置构造函数方法.html)

## 编程思想

### 面向过程

**面向过程**：就是分析出解决问题所需要的步骤，然后用函数把这些步骤一步一步实现，使用的时候再一个一个的依次

调用就可以了。

面向过程，就是按照分析好了的步骤，按照步骤解决问题。





### 面向对象

**面向对象**：是把事务分解成为一个个对象，然后由对象之间分工与合作。

面向对象是以对象功能来划分问题，而不是步骤。

- 在面向对象程序开发思想中，每一个对象都是功能中心，具有明确分工。
- 面向对象编程具有灵活、代码可复用、容易维护和开发的优点，更适合多人合作的大型软件项目。
- 面向对象的特性：
  - 封装性
  - 继承性
  - 多态性



### 面向过程和面向对象的对比

- **面向过程编程** 
  - **优点：**性能比面向对象高，适合跟硬件联系很紧密的东西，例如单片机就采用的面向过程编程。
  - **缺点：**没有面向对象易维护、易复用、易扩展
- **面向对象编程**
  - **优点：**易维护、易复用、易扩展，由于面向对象有封装、继承、多态性的特性，可以设计出低耦合的系统，使系统 更加灵活、更加易于维护
  - **缺点：**性能比面向过程低





## 构造函数

- 封装是面向对象思想中比较重要的一部分，js面向对象可以通过构造函数实现的封装。

- 同样的将变量和函数组合到了一起并能通过 this 实现数据的共享，所不同的是借助构造函数创建出来的实例对象之间是彼此不影响的

```js
function people(name, age, gender) {
    this.name = name
    this.age = age
    this.gender = gender
    this.sing = function () {
        console.log('我会唱歌')
    }
}

// 创建John
const John = new people('John', 15, '男')
// 创建Smith
const Smith = new people('Smith', 17, '男')
```



**总结**：

1. 构造函数体现了面向对象的封装特性

2. 构造函数实例创建的对象彼此独立、互不影响



封装是面向对象思想中比较重要的一部分，js面向对象可以通过构造函数实现的封装。

构造函数方法很好用，但是 **存在浪费内存的问题**

**面向对象编程的特性**：比如封装性、继承性等，可以借助于构造函数来实现



## 原型

### 原型

- 构造函数通过原型分配的函数是所有对象所 **共享的**。
- JavaScript 规定，**每一个构造函数都有一个 `prototype` 属性**，指向另一个对象，所以我们也称为原型对象
- 这个对象可以挂载函数，对象实例化不会多次创建原型上函数，节约内存
- **我们可以把那些不变的方法，直接定义在 `prototype` 对象上，这样所有对象的实例就可以共享这些方法。**
- **构造函数和原型对象中的`this`都指向 实例化的对象**



构造函数和原型对象中的`this`都指向 **实例化的对象**



### constructor 属性

每个原型对象里面都有个`constructor`属性（constructor 构造函数）

**作用：**该属性指向该原型对象的构造函数

<img src="images/constructor 属性.png" alt="constructor 属性" style="width: 600px;">

如果有多个对象的方法，可以给原型对象采取对象形式赋值.

但是这样就会覆盖构造函数原型对象原来的内容，这样修改后的原型对象 constructor 就不再指向当前构造函数了

此时，可以在修改后的原型对象中，添加一个 constructor 指向原来的构造函数。



### 对象原型

**对象都会有一个属性 `__proto__`** 指向构造函数的 prototype 原型对象，之所以对象可以使用构造函数 prototype 原型对象的属性和方法，就是因为对象有 `__proto__` 原型的存在。

<img src="images/对象原型.png" alt="constructor 属性" style="width: 600px;">

**注意**：

- `__proto__` 是 JS 非标准属性
- `[[prototype]]`和`__proto__`意义相同
- 用来表明当前实例对象指向哪个原型对象prototype
- `__proto__` 对象原型里面也有一个 constructor属性，==**指向创建该实例对象的构造函数**==



### 原型继承

继承 是 面向对象 编程的另一个特征，通过继承进一步提升代码封装的程度，JavaScript 中大多是借助原型对象实现继承的特性。

```js
function Man() {
	this.head = 1;
	this.eyes = 2;
	this.legs = 2;
	this.say = function () {}
	this.eat = function () {}
}
const John new Man()
    
function Woman() {
	this.head = 1;
	this.eyes = 2;
	this.legs = 2;
	this.say = function () {}
	this.eat = function () {}
	this.birth = function () {}
}
const wier new Woman()
```



#### **封装-抽取公共部分**

1. **封装：**把男人和女人公共的部分抽取出来放到人类里面

   ```js
   // 人
   const Person = {
               head: 1,
               eyes: 2,
               legs: 2,
               say: function () { },
               eat: function () { }
   }
   
   // 男
   function Man() {
   }
   
   // 女
   function Woman() {
   	this.birth = function () {}
   }
   ```

   

2. **继承：**让 男 和 女 都能继承人的一些属性和方法

   - 把男女公共的属性和方法抽取出来 `Person`
   - 然后赋值给Man的原型对象，可以共享这些属性和方法
   - 注意让 `constructor` 指回 `Man` 这个构造函数

   ```js
   // 把公共的属性和方法给原型，这样就可以共享了
   Man.prototype = Person
   // 注意让 constructor 指回 Man 这个构造函数
   Man.prototype.constructor = Man
   ```

   

3. 问题：





### 原型链











# 正则表达式

正则表达式（Regular Expression）是用于匹配字符串中字符组合的模式。在 JavaScript 中，正则表达式也是对象

通常用来查找、替换那些符合正则表达式的文本



正则表达式在 JavaScript 中的使用场景：

- 例如验证表单：用户名表单只能输入英文字母、数字或者下划线， 昵称输入框中可以输入中文(匹配)
  - 比如用户名: `/^[a-z0-9_-]{3,16}$/`
- 过滤掉页面内容中的一些敏感词(替换)，或从字符串中获取想要的特定部分(提取)等 。



## 语法

JavaScript 中定义正则表达式的语法有两种，其中比较简单的方法：

1、**定义正则表达式语法：**

```js
const 变量名 = /表达式/
```

其中 /  / 是正则表达式字面量



2、 **判断是否有符合规则的字符串：**

- **`test()`** 方法 用来查看正则表达式与指定的字符串是否匹配

  ```js
  regObj.test(被检测的字符串)
  ```

- 示例：

  ```js
  //要检测的字符电
  const str='查看正则表达式与指定的字符串是否匹配'
  //1.定义正则表达式，检测规则
  const reg=/正则表达式/
  //2.检测方法
  console.log(reg.test(str))	//true
  ```

- 如果正则表达式与指定的字符串匹配 ，返回 `true`，否则 `false`

3、 **检索（查找）符合规则的字符串：**

- **`exec()`** 方法 在一个指定字符串中执行一个搜索匹配

- **语法：**

  ```js
  regObj.exec(被检测的字符串)
  ```

- 示例：

  ```js
  //要检测的字符串
  const str='查看正则表达式与指定的字符串是否匹配'
  //1.定义正则表达式，检测规则
  const reg=/正则表达式/
  //2.检测方法
  console.log(reg.exec(str))	//返回的是数组
  ```

- 如果匹配成功，`exec()` 方法返回一个数组，否则返回 `null`



## 元字符

- **普通字符:**

  大多数的字符仅能够描述它们本身，这些字符称作普通字符，例如所有的字母和数字。也就是说普通字符只能够匹配字符串中与它们相同的字符。

- **元字符(特殊字符）**

  是一些具有特殊含义的字符，可以极大提高了灵活性和强大的匹配功能。

  - 元字符分类：
    - [<font color=red>边界符（表示位置，开头和结尾，必须用什么开头，用什么结尾）</font>](# 边界符)
    - [量词 （表示重复次数）](# 量词)
    - [字符类 （比如  \d  表示 0~9）](# 字符类)

### 边界符

正则表达式中的边界符（位置符）用来 **提示字符所处的位置**，主要有两个字符

| 边界符 | 说明                           |
| ------ | ------------------------------ |
| ^      | 表示匹配行首的文本（以谁开始） |
| $      | 表示匹配行尾的文本（以谁结束） |

如果 ^ 和 $ 在一起，表示必须是精确匹配。

```js
console.1og(/哈/.test('哈'))		//true
console.1og(/二哈/.test('二哈'))	//true
console.1og(/二哈/.test('很二哈哈'))	//true
// ^ 开头
console.1og(/^二哈/.test('很二哈哈'))	//false
console.1og(/^二哈/.test('二哈很傻'))	//true
// $ 结尾
console.1og(/^二哈$/.test('二哈很傻'))	//false
console.1og(/^二哈$/.test('二哈二哈'))	//false
console.1og(/^二哈$/.test('二哈')	//true
```



### 量词

量词用来 **设定某个模式出现的次数**

| 量词  | 说明                |
| ----- | ------------------- |
| *     | 表示匹配0次或更多次 |
| +     | 表示匹配1次或更多次 |
| ?     | 表示匹配0次或1次    |
| {n}   | 表示匹配n次         |
| {n,}  | 表示匹配n次或更多次 |
| {n,m} | 表示匹配n到m次      |

**<font color=red>注意： 逗号左右两侧千万不要出现空格</font>**



###  **字符类：**

####`[]`匹配字符集合

* `/[abc]/`：后面的字符串只要包含 abc 中任意 **一个字符**，都返回 true 。

* `[]`里面加上`- `连字符
  * 使用连字符 `-` 表示一个范围
  * `[a-z]`：表示 **a 到 z**	26个英文字母都可以
  * `[a-zA-Z]`：表示 **大小写** 都可以
  * `[0-9]`：表示 0~9 的数字都可以
* `[]`里面加上 `^` 取反符号
  * `[^a-z]`：匹配除了小写字母以外的字符
  * 注意：`^`要写到中括号里面
* `.` 匹配除换行符之外的任何单个字符



#### 预定义：指的是 ==**某些常见模式的简写方式**==。

| 预定义 | 说明                                                  |
| ------ | ----------------------------------------------------- |
| \d     | 匹配一个数字字符。等价于 [0-9]。                      |
| \D     | 匹配一个非数字字符。等价于 [\^0-9]。                  |
| \w     | 匹配一个字母、数字或下划线。等价于 [A-Za-z0-9_]。     |
| \W     | 匹配一个非字母、数字或下划线。等价于 [\^A-Za-z0-9_]。 |
| \s     | 匹配一个空白字符。等价于 [\f\n\r\t\v]。               |
| \S     | 匹配一个非空白字符。等价于 [\^ \f\n\r\t\v]。          |
| \b     | 匹配一个单词边界，也就是指单词和空格间的位置。        |
| \B     | 匹配非单词边界。                                      |
| \|     | 匹配两个或更多的表达式。                              |



## 修饰符

- 修饰符约束正则执行的某些细节行为，如 **是否区分大小写、是否支持多行匹配** 等

  - 语法：

    ```js
    /表达式/修饰符
    ```

    - `i` 是单词 `ignore` 的缩写，正则匹配时字母 **不区分** 大小写
    - `g` 是单词 `global` 的缩写，匹配所有满足正则表达式的结果

- **`replace` 替换**

  - 语法：

    ```js
    字符串.replace(/正则表达式/，'替换的文本')
    ```

    

    
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkwNDA3NjVdfQ==
-->