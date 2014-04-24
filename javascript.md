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

    ```javascript
    // bad
    var obj = {
        a:'123',
        b:1
    };

    // good
    var obj = {
        a: '123',
        b: 1
    };
    ```
* 在操作符左右必须「MUST」使用空格。

    ```javascript
    // bad
    var x=y+5;

    // good
    var x = y + 5;
    ```
* 一元操作符（如：!, ++ 等等）与操作对象之间不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    var a = ! arr.length;

    a ++;

    // good
    var a = !arr.length;

    a++;
    ```
* 所有`,`，`;`前面不允许「MUST NOT」使用空格。
* 在对象属性中的`:`前面不允许「MUST NOT」使用空格。

    ```javascript
    // bad
    var a = {
        b : 1,
        c : 2
    };

    // good
    var a = {
        b: 1,
        c: 2
    };
    ```
* 在行末和空行中不允许「MUST NOT」使用空格。

**[⬆ Top](#目录)**
## 换行

## 块

## 类型转换
## 条件判断
## 命名
## 注释
## 其他
## 参考资料