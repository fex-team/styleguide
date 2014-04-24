Javascript 编码规范
=========================

此为前端开发团队遵循和约定的 Javascript 编码规范，意在提高代码的规范性和可维护性。

## 说明
文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL
NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在[RFC2119](http://oss.org.cn/man/develop/rfc/RFC2119.txt)中被说明。

**还未定稿，对规范中提及的点有不赞同的欢迎[提出issues](https://github.com/fex-team/styleguide/issues/new)讨论。**

## 目录

1. [空格](#空格)
1. [换行](#换行)

## 空格
在特定的位置加上空格可以提高代码的可读性。

* 必须「MUST」采用4个空格为一次缩进

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
* 在以下关键后面必须「MUST」使用空格: if/else/for/while/do/try/catch/finanlly.

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
* 在对象属性中的`:`后面「MUST」使用空格。
* 在对象属性中的`:`前面不允许「MUST NOT」使用空格。

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
* 关键字`function`后面必须「MUST」使用空格，但是如果是匿名方法，关键字`function`后面不允许「MUST NOT」使用空格。

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
* 所有`,`，`;`前面不允许「MUST NOT」使用空格。

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

* 每一行代码严格以120字符为最大长度，即一行包括前后的空格， 不得「MUST NOT」超过120个字符。
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

## 块

## 类型转换
## 条件判断
## 命名
## 注释
## 其他
## 参考资料