CSS 编码规范
=========================

此为前端开发团队遵循和约定的 CSS 编码规范，意在提高代码的规范性和可维护性。

## 说明
文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL
NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在[RFC2119](http://oss.org.cn/man/develop/rfc/RFC2119.txt)中被说明。

* 所有带「MUST」说明的规则将提供检测工具检测。
* 所有带「SHOULD」说明的规则将提供格式化工具自动排班。

**还未定稿，对规范中提及的点有不赞同的欢迎[提出issues](https://github.com/fex-team/styleguide/issues/new)(请添加`CSS`标签)讨论。**

## 目录

* [代码风格](#代码风格)
* [组织格式](#组织格式)
* [代码注释](#代码注释)
* [样式重置](#CSS重置)

## 代码风格

* 代码应该「SHOULD」符合CSS语法有效性，可以使用[W3C CSS validator](http://jigsaw.w3.org/css-validator/validator.html.zh-cn)工具来验证。

* ID和Class应该「SHOULD」按照元素功能命名，不应该「SHOULD NOT」按照元素表现命名，命名应该「SHOULD」含义清晰。

    ```css
    /* bad: 含义不清 */
    #yee-1901 {}

    /* bad: 表现化 */
    .button-green {}
    .clear {}

    /* good: 功能化 */
    #gallery {}
    #login {}
    .video {}
    ```
* ID和Class命名应该「SHOULD」在保持含义清晰的前提下尽可能简短。

    ```css
    /* bad */
    #navigation {}
    .atr {}

    /* good */
    #nav {}
    .author {}
    ```
* ID和Class命名中单词应该「SHOULD」全部小写，并且使用"-"作为分隔符。

    ```css
    /* bad */
    #videoId {}
    .demoimage {}
    .error_status {}

    /* good */
    #video-id {}
    .ads-sample {}
    ```

* 不能「MUST NOT」把ID和Class选择符作为类型选择符的限定符。

    ```css
    /* bad */
    ul#example {}
    div.error {}

    /* good */
    #example {}
    .error {}
    ```
* CSS属性应该「SHOULD」尽可能使用简化方式书写。

    ```css
    /* bad */
    border-top-style: none;
    font-family: palatino, georgia, serif;
    font-size: 100%;
    line-height: 1.6;
    padding-bottom: 2em;
    padding-left: 1em;
    padding-right: 1em;
    padding-top: 0;

    /* good */
    border-top: 0;
    font: 100%/1.6 palatino, georgia, serif;
    padding: 0 1em 2em;
    ```
* CSS属性中的"0"值不应该「SHOULD NOT」带单位。

    ```css
    /* bad */
    margin: 0px;
    padding: 0px;

    /* good */
    margin: 0;
    padding: 0;
    ```
* CSS属性中数值介于-1到1之间的小数应该「SHOULD」忽略开头的"0"。

    ```css
    /* bad */
    font-size: 0.8em;

    /* good */
    font-size: .8em;
    ```
* CSS的色值应该「SHOULD」尽可能使用简化写法。

    ```css
    /* bad */
    color: #eebbcc;

    /* good */
    color: #ebc;
    ```
**[⬆ Top](#目录)**

## 组织格式

* 必须「MUST」采用4个空格为一次缩进。

* CSS属性声明应该「SHOULD」按字母升序排列。

    ```css
    /* good */
    background: fuchsia;
    border: 1px solid;
    -moz-border-radius: 4px;
    -webkit-border-radius: 4px;
    border-radius: 4px;
    color: black;
    text-align: center;
    text-indent: 2em;
    ```
* CSS每个代码块相对于父代码库必须「MUST」有缩进。

    ```css
    /*good*/
    @media screen, projection {

      html {
        background: #fff;
        color: #444;
      }

    }
    ```
* CSS属性声明必须「MUST」以分号结尾。
* CSS属性名冒号后必须「MUST」有一个空格。

    ```css
    /* bad */
    color:#eebbcc;

    /* good */
    color: #ebc;
    ```
* 最后的选择符与"{"之间必须「MUST」有一个空格。

    ```css
    /* bad */
    #video{
      margin-top: 1em;
    }
    .author
    {
      margin-top: 1em;
    }

    /* good */
    #video {
      margin-top: 1em;
    }
    ```
* 多个并列的选择符必须「MUST」换行。

    ```css
    /* bad */
    a:focus, a:active {
      position: relative; top: 1px;
    }

    /* good */
    h1,
    h2,
    h3 {
      font-weight: normal;
      line-height: 1.2;
    }
    ```
* CSS规则之间必须「MUST」以空白行分隔。

    ```css
    /* good */
    html {
      background: #fff;
    }

    body {
      margin: auto;
      width: 50%;
    }
    ```
* CSS属性值中所有使用到引号的位置必须「MUST」使用单引号。

    ```css
    /* bad */
    @import url("//www.google.com/css/maia.css");

    html {
      font-family: "open sans", arial, sans-serif;
    }

    /* good */
    @import url(//www.google.com/css/maia.css);

    html {
      font-family: 'open sans', arial, sans-serif;
    }
    ```
**[⬆ Top](#目录)**

## 代码注释

* CSS规则段落之前应该「SHOULD」添加注释说明。

    ```css
    /* good */
    /* Header */

    #adw-header {}

    /* Footer */

    #adw-footer {}

    /* Gallery */

    .adw-gallery {}
    ```
**[⬆ Top](#目录)**

## 样式重置

* 应该「SHOULD」使用推荐的`normalize.css`进行样式重置。

**[⬆ Top](#目录)**
