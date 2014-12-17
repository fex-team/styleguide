Markdown 编写规范
==========================

此为前端开发团队遵循和约定的 **Markdown 编写规范**，意在提高文档的可读性。

## 说明

文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL
NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在 [RFC2119](http://oss.org.cn/man/develop/rfc/RFC2119.txt) 中有说明。

**还未定稿，对规范中提及的点有不赞同的欢迎[提出 issues](https://github.com/fex-team/styleguide/issues/new)（请添加 `markdown` 标签）讨论。**

## 规则

* 后缀必须「MUST」使用 `.md`。
* 文件名必须「MUST」使用小写，多个单词之间使用`-`分隔。
* 文件编码必须「MUST」用 UTF-8。
* 文档标题应该「SHOULD」这样写。

    ```
    Markdown 编写规范
    ==========================
    ```
* 章节标题必须「MUST」以 `##` 开始，而不是 `#`。
* 章节标题必须「MUST」在 `#` 后加一个空格，且后面没有 `#`。

    ```
    // bad
    ##章节1

    // bad
    ## 章节1 ##

    // good
    ## 章节1
    ```

* 章节标题和内容间必须「MUST」有一个空行。

    ```
    // bad
    ## 章节1
    内容
    ## 章节2

    // good
    ## 章节1

    内容

    ## 章节2
    ```

* 代码段的必须「MUST」使用 Fenced code blocks 风格，如下所示：

        ```
        console.log("");
        ```

* 表格的写法应该「SHOULD」参考 [GFM](https://help.github.com/articles/github-flavored-markdown)，如下所示：

    ```
    First Header  | Second Header
    ------------- | -------------
    Content Cell  | Content Cell
    Content Cell  | Content Cell

    | Left-Aligned  | Center Aligned  | Right Aligned |
    | :------------ |:---------------:| -----:|
    | col 3 is      | some wordy text | $1600 |
    | col 2 is      | centered        |   $12 |
    | zebra stripes | are neat        |    $1 |
    ```

* 中英文混排应该「SHOULD」采用如下规则：
    - 英文和数字使用半角字符
    - 中文文字之间不加空格
    - 中文文字与英文、阿拉伯数字及 @ # $ % ^ & * . ( ) 等符号之间加空格
    - 中文标点之间不加空格
    - 中文标点与前后字符（无论全角或半角）之间不加空格
    - 如果括号内有中文，则使用中文括号
    - 如果括号中的内容全部都是英文，则使用半角英文括号 
    - 当半角符号 / 表示「或者」之意时，与前后的字符之间均不加空格
    - 其它具体例子推荐[阅读这里](https://github.com/sparanoid/chinese-copywriting-guidelines)

* 中文符号应该「SHOULD」使用如下写法：
    - 用直角引号（「」）代替双引号（“”），不同输入法的具体设置方法请[参考这里](http://www.zhihu.com/question/19755746)
    - 省略号使用「……」，而「。。。」仅用于表示停顿
    - 其它可以参考[知乎规范](http://www.zhihu.com/question/20414919)

* 表达方式，应当「SHOULD」遵循《The Element of Style》：
    * 使段落成为文章的单元：一个段落只表达一个主题
    * 通常在每一段落开始要点题，在段落结尾要扣题
    * 使用主动语态
    * 陈述句中使用肯定说法
    * 删除不必要的词
    * 避免连续使用松散的句子
    * 使用相同的结构表达并列的意思
    * 将相关的词放在一起
    * 在总结中，要用同一种时态（这里指英文中的时态，中文不适用，所以可以不理会）
    * 将强调的词放在句末


