Javascript 编码规范
=========================

此为前端开发团队遵循和约定的 Javascript 编码规范，意在提高代码的规范性和可维护性。

文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL
NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在[RFC2119](http://oss.org.cn/man/develop/rfc/RFC2119.txt)中被说明。

## 目录

1. [空白](#空白)
1. [换行](#换行)

## 空白
在特定的位置加上空格有助于代码的可读性。

* 必须「MUST」采用4个空格为一次缩进

    ```javascript
    // bad
    function() {
    ∙∙∙∙var name;
    }

    // bad
    function() {
    ∙var name;
    }

    // good
    function() {
    ∙∙var name;
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
* 在操作符左右必须「MUST」使用空格。

    ```javascript
    // bad
    var x=y+5;

    // good
    var x = y + 5;
    ```

**[⬆ Top](#目录)**
## 换行

## 块

## 类型转换
## 条件判断
## 命名
## 注释
## 其他
## 参考资料