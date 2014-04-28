JavaScript 编码规范
=========================

此为前端开发团队遵循和约定的 JavaScript 编码规范，意在提高代码的规范性和可维护性。

## 说明

文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL
NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在 [RFC2119](http://oss.org.cn/man/develop/rfc/RFC2119.txt) 中有说明。

* 所有带「MUST」说明的规则将提供检测工具检测。
* 所有带「SHOULD」和「MUST」说明的规则将提供格式化工具自动排版。

**还未定稿，对规范中提及的点有不赞同的欢迎[提出 issues](https://github.com/fex-team/styleguide/issues/new)(请添加`JavaScript`标签)讨论。**

## 目录

1. [空格](#空格)
1. [换行](#换行)
1. [变量](#变量)
1. [字符串](#字符串)
1. [块状代码](#块状代码)
1. [类型检测](#类型检测)
1. [条件判断](#条件判断)
1. [命名](#命名)
1. [注释](#注释)
1. [其他](#其他)

## 空格

在特定的位置加上空格可以提高代码的可读性。

* 必须「MUST」采用4个空格为一次缩进。

    ```javascript
    // bad
    function() {
    ∙∙var name;
    }

    // bad
    function() {
    ∙var name;
    }

    // good
    function() {
    ∙∙∙∙var name;
    }
    ```

* 在大括号开始处的前面必须「MUST」使用空格。

    ```javascript
    // bad
    function test(){
      console.log('test');
    }

    // good
    function test() {
      console.log('test');
    }

    // bad
    dog.set('attr',{
      age: '1 year',
      breed: 'Bernese Mountain Dog'
    });

    // good
    dog.set('attr', {
      age: '1 year',
      breed: 'Bernese Mountain Dog'
    });
    ```

* 在以下关键词后面必须「MUST」使用空格: if/else/for/while/do/try/catch/finanlly。

    ```javascript
    // good
    if (condition) {
      // statements
    }

    while (condition) {
      // statements
    }

    for (var i = 0; i < 100; i++) {
      // statements
    }

    if (true) {
      // statements
    } else {
      // statements
    }
    ```

* 在对象属性中的 `:` 后面「MUST」使用空格。
* 在对象属性中的 `:` 前面不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    var obj = {
        a : 1,
        b:2,
        c :3
    };

    // good
    var obj = {
        a: 1,
        b: 2,
        c: 3
    };
    ```
* 在运算符左右必须「MUST」使用空格。

    ```javascript
    // bad
    var x=y+5;

    // good
    var x = y + 5;
    ```

* 一元运算符（如：!, ++ 等等）与操作对象之间不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    var a = ! arr.length;

    a ++;

    // good
    var a = !arr.length;

    a++;
    ```

* 关键字 `function` 后面必须「MUST」使用空格，但是如果是匿名方法，关键字 `function` 后面不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    var funcA = function () {
        // statement
    };

    // good
    var funcA = function() {
        // statement
    };

    function funcA() {
        // statement
    }
    ```

* 函数参数与左右括号之间不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    function funA( a, b ) {

    }

    var funB = function( c ) {

    };

    funA( 1, 2 );
    funB( 3 );

    // good
    function funA(a, b) {

    }

    var funB = function(c) {

    };

    funA(1, 2);
    funB(3);
    ```

* `,` 和 `;` 前面不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    callFunA(a , b) ;

    // good
    calFunA(a, b);
    ```

* 在行末和空行中不允许「MUST NOT」使用空格。

**[⬆ Top](#目录)**

## 换行

适当的换行和空行可以提高代码可读性。

* 每一行代码严格以 120 字符为最大长度，即一行包括前后的空格， 不应该「SHOULD NOT」超过 120 个字符。
* 每个独立语句结束后面必须「MUST」使用换行。

    ```javascript
    // bad
    api.callFunA(); api.callFunB();

    // good
    api.callFunA();
    api.callFunB();
    ```

* 换行后不得「MUST NOT」让操作符位于位于新行行首。

    ```javascript
    // bad
    a = 124343 + 34343
        + 45454;

    // good
    a = 124343 + 34343 +
        45454;

    // bad
    if (condition1
        && condition2
        && condition3) {

    }

    // good
    if (condition1 &&
        condition2 &&
        condition3) {

    }

    // bad
    function funA(firstArg, sencondArg
        , thirdArg) {
        // statement
    }

    // good
    function funA(firstArg, sencondArg,
        thirdArg) {
        // statement
    }
    ```
* 在文件结尾处应该「SHOULD」留一个空行。

    ```javascript
    // bad
    (function(global) {
      // ...stuff...
    })(this);
    ```

    ```javascript
    // good
    (function(global) {
      // ...stuff...
    })(this);

    ```

* 链式调用较长时应当「SHOULD」采用缩进进行调整。

    ```javascript
    // bad
    $('#items').find('.selected').highlight().end().find('.open').updateCount();

    // good
    $('#items')
        .find('.selected')
            .highlight()
            .end()
        .find('.open')
            .updateCount();
    ```

* 块状代码与其他部分应该「SHOULD」使用至少一个空行分割。

    ```javascript
    // bad
    callFunA();
    if (condition) {
        doSomeThings();
    }
    callFunB();

    obj = {
        a: 1,
        b: 2,
        c: function() {
            // do some things.
        },
        d: {
            x: 1,
            y: 2
        }
    };

    // good
    callFunA();

    if (condition) {
        doSomeThings();
    }

    callFunB();

    obj = {
        a: 1,
        b: 2,

        c: function() {
            // do some things.
        },

        d: {
            x: 1,
            y: 2
        }
    };

    ```

**[⬆ Top](#目录)**

## 变量

* 变量在使用前必须「MUST」使用 `var` 申明，不要污染到全局。

    ```javascript
    // bad
    superPower = new SuperPower();

    // good
    var superPower = new SuperPower();
    ```

* 多个变量申明，应当「SHOULD」采用多个 `var` 来申明，每个 `var` 申明独占一行，且一次申明一个变量。

    ```javascript
    // bad
    var items = getItems(),
        goSportsTeam = true,
        dragonball = 'z';

    // good
    var items = getItems();
    var goSportsTeam = true;
    var dragonball = 'z';
    ```

* 多个非赋值的变量申明可以「MAY」共用一个 `var`，但是单行不得超出120个字符字符。

    ```javascript
    // good.
    var a = 1;
    var b = 2;
    var c, d, e, f, g;
    ```

* 同一个作用域下的变量应当「SHOULD」统一在 `function` 头部申明。

    ```javascript
    // bad
    function funA(arg) {
        doSomething();

        var a = 3;

        if (condition) {
            var b = 2;
        }

        var c = 1;
    }

    // good
    function funA(arg) {
        var a = 3;
        var c = 1;
        var b;

        doSomething();

        if (condition) {
            b = 2;
        }
    }
    ```

更多关于 [oneVar](http://benalman.com/news/2012/05/multiple-var-statements-javascript/)的讨论。

**[⬆ Top](#目录)**

## 字符串

* 必须「MUST」统一采用单引号 `''`。

    ```javascript
    // bad
    var name = "Bob Parr";

    // good
    var name = 'Bob Parr';

    // bad
    var fullName = "Bob " + this.lastName;

    // good
    var fullName = 'Bob ' + this.lastName;
    ```

* 超长字符串应当「SHOULD」使用 `+` 进行换行。

    ```javascript
    // 正确
    var myString = 'A rather long string of English text, an error message ' +
                 'actually that just keeps going and going -- an error ' +
                 'message to make the Energizer bunny blush (right through ' +
                 'those Schwarzenegger shades)! Where was I? Oh yes, ' +
                 'you\'ve got an error and all the extraneous whitespace is ' +
                 'just gravy.  Have a nice day.';

    // 错误
    var myString = 'A rather long string of English text, an error message \
                  actually that just keeps going and going -- an error \
                  message to make the Energizer bunny blush (right through \
                  those Schwarzenegger shades)! Where was I? Oh yes, \
                  you\'ve got an error and all the extraneous whitespace is \
                  just gravy.  Have a nice day.';
    ```

**[⬆ Top](#目录)**

## 块状代码

所有的**多行**块状代码应当「SHOULD」使用大括号括起来。

```javascript
// bad
if (test)
  return false;

// good
if (test) return false;

// good
if (test) {
    return false;
}

// bad
function() { return false; }

// good
function() {
    return false;
}
```

**[⬆ Top](#目录)**

## 类型检测

### 基本类型检测

* String: `typeof variable === 'string'`
* Number: `typeof variable === 'number'`
* Boolean: `typeof variable === 'boolean'`
* Object: `typeof variable === 'object'`
* Array: 如果支持，使用：`Array.isArray( arrayLikeObject )`
* Node: `elem.nodeType === 1`
* null: `variable === null`
* null or undefined:: `variable == null`
* undefined
    * 全局变量: `typeof variable === 'undefined'`
    * 局部变量: `variable === undefined`
    * 属性:

        ```javascript
        object.prop === undefined
        object.hasOwnProperty( prop )
        'prop' in object
        ```

### 强制类型转换

以下是一些常见的类型装换的例子，推荐使用。

```javascript
var number = 1,
  string = '1',
  bool = false;

number;
// 1

number + '';
// '1'

string;
// '1'

+string;
// 1

+string++;
// 1

string;
// 2

bool;
// false

+bool;
// 0

bool + '';
// 'false'
```

```javascript
var number = 1,
  string = '1',
  bool = true;

string === number;
// false

string === number + '';
// true

+string === number;
// true

bool === number;
// false

+bool === number;
// true

bool === string;
// false

bool === !!string;
// true
```

```javascript
var array = [ 'a', 'b', 'c' ];

!!~array.indexOf('a');
// true

!!~array.indexOf('b');
// true

!!~array.indexOf('c');
// true

!!~array.indexOf('d');
// false
```

```javascript
var num = 2.5;

parseInt(num, 10);

// is the same as...

~~num;

num >> 0;

num >>> 0;

// All result in 2

// Keep in mind however, that negative numbers will be treated differently...

var neg = -2.5;

parseInt(neg, 10);

// is the same as...

~~neg;

neg >> 0;

// All result in -2
// However...

neg >>> 0;

// Will result in 4294967294
```

**注意** 使用`parseInt`进行数字类型转换的时候，应当「SHOULD」指定第二个参数，以免误当八进制解析。

**[⬆ Top](#目录)**

## 条件判断

* 应当「SHOULD」使用 `===` 和 `!==` 代替 `==` 和 `!=`。
* 条件判断遵循以下规则
    * **Objects** 等同于 **true**
    * **Undefined** 等同于 **false**
    * **Null** 等同于 **false**
    * **Booleans** 等同于**此布尔变量的值**
    * **Numbers** 如果是 **+0, -0, 或者 NaN** 等同于 **false**，其他情况等同于 **true**。
    * **Strings**，当字符是空字符串 `''` 时，等同于 **flase**，其他情况等同于 **true**。

    ```javascript
    if ([0]) {
      // true
      // 数组属于Objects,等同于true
    }
    ```

* 应当「SHOULD」使用最简捷的方式判断。

    ```javascript
    // bad
    if (name !== '') {
      // ...stuff...
    }

    // good
    if (name) {
      // ...stuff...
    }

    // bad
    if (collection.length > 0) {
      // ...stuff...
    }

    // good
    if (collection.length) {
      // ...stuff...
    }
    ```

更多信息请查看 [Truth Equality and JavaScript](http://javascriptweblog.wordpress.com/2011/02/07/truth-equality-and-javascript/#more-2108)。

**[⬆ Top](#目录)**

## 命名

**说明**

* camel 命名法，形如 thisIsAnApple
* pascal 命名法，形如 ThisIsAnApple
* 下划线命名法，形如 `this_is_an_apple`

根据不同类型的内容， 必须「MUST」严格采用如下的命名法：

* **变量名：**
    必须「MUST」使用 camel 命名法
* **参数名：**
    必须「MUST」使用 camel 命名法
* **函数名：**
    必须「MUST」使用 camel 命名法
* **方法、属性：**
    必须「MUST」使用 camel 命名法
* **私有成员、方法：**
    必须「MUST」以下划线 `_` 开头
* **常量名：**
    必须「MUST」使用全部大写的下划线命名法，如 IS_DEBUG_ENABLED
* **类名：**
    必须「MUST」使用 pascal 命名法
* **专有名词：**
    必须「MUST」使用官方写法，如 `HTML`，而不是 `Html`

### 语义

命名同时还需要关注语义，如：

* 变量名 应当「SHOULD」使用名词
* **Boolean** 类型的 应当「SHOULD」使用 **is**、**has** 等起头，表示其类型
* 函数名 应当「SHOULD」用动宾短语
* 类名 应当「SHOULD」用名词

**[⬆ Top](#目录)**

## 注释

* JS 文档注释，每个 JS 文件顶部都应当「SHOULD」包含关于 JS 文件功能的注释信息。

    ```javascript
    /**
     * @fileoverview 文件功能描述或一些其他相关信息.
     */
    ```

* 单行注释：以两个斜线开始，以行尾结束，两个斜线与内容之间必须「MUST」使用一个空格。

    ```javascript
    // 这是一个注释
    ```

    单行注释分以下两种：

    1. 独占一行，用来解释下一行代码。这行注释之前应当「SHOULD」有一个空行，且缩进层级和下一行代码必须「MUST」保持一致。
    1. 在代码行的尾部添加，代码结束到注释之间必须「MUST」至少有一个缩进。注释（包括前面的代码部分）不能「MUST NOT」超过单行最大字符数限制，如果超过则改成第一种注释。

    ```javascript
    function doSomething() {
        var a = 3;    // 这变量用来存长度

        // 这个变量用来存宽度
        var b;

        // 这个变量用来存高度
        var c;

        if (condition) {

            // 如果代码执行到这，则说明通过安全验证。
            popupDialog();
        }
    }
    ```

* 多行注释：当内容比较多用单行注释不能满足需求时，应当「SHOULD」使用多行注释，格式如下，前面应当「MUST」有个空格。

    ```javascript
    /*
     * 我的注释
     * 注释中的第二段
     */
    if (condition) {
        statement
    }
    ```

* 避免多余的注释，当代码很明了时不应当「SHOULD NOT」添加注释。

    ```
    // 不必要的注释

    // 初始化count
    var count = 10;
    ```

Doc 注释待完善，参考 [Doc生成工具](https://github.com/2betop/gmudoc)。

**[⬆ Top](#目录)**

## 其他

* 创建 Object/Array 时，应当「SHOULD」采用字面量方式。

    ```javascript
    // bad
    var item = new Object();

    // good
    var item = {};

    // bad
    var items = new Array();

    // good
    var items = [];
    ```

*  for-in 循环体中应当「SHOULD」用 hasOwnProperty 方法检查成员是否为自身成员。避免来自原型链上的污染。

    ```javascript
    // good
    for (name in object) {

        if (object.hasOwnProperty(name)) {
            doSomething();
        }
    }
    ```

* 不得「MUST NOT」使用 with, void, eval。
* 函数定义不得「MUST NOT」在 if、for、while 等代码块中定义函数，在函数中定义内嵌函数时应该把函数定义放在顶部，闭包除外。

    ```javascript
    // bad
    function outerFunc(va) {
        va = va || 0;

        if (va) {
            function innerFunc() {
                //to do....
            }

            innerFunc();
        }
    }

    // good
    function outerFunc(va) {
        va = va || 0;

        function innerFunc() {
            //to do....
        }

        if (va) {
            innerFunc();
        }
    }
    ```

* 立即执行函数应当「SHOULD」统一采用以下方式。更多信息请查看 [jsperf](http://jsperf.com/bang-function)。

    ```javascript
    // good
    (function() {
        // skiped
    })();

    // bad
    +function() {
        // skiped
    }();

    !function() {
        // skiped
    }();
    ```

**[⬆ Top](#目录)**

## 参考资料

* <https://github.com/airbnb/javascript>
* <https://github.com/ecomfe/spec>
* <https://github.com/rwaldron/idiomatic.js>
* <http://google-styleguide.googlecode.com/svn/trunk/htmlcssguide.xml>
* <http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml>
* <http://front-end-standards.com/>
* <https://github.com/styleguide/>
* <https://contribute.jquery.org/style-guide/js/>
