前端安全规范
========

本文档描述前端开发人员在应用开发中，需要关注的安全问题和相应的编码规范，旨在杜绝一些常见的安全隐患。

**说明：**文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在 RFC2119 中有说明。

## 背景知识

本文不会详细介绍 Web 安全的攻击和防御技术，所以请先参考如下资料了解相关知识：

[XSS]()

## XSS防御

请务必阅读：[终极XSS防护备忘录](http://www.fooying.com/chinese-translationthe-ultimate-xss-protection-cheatsheet-for-developers/) 根据其中的描述做好数据转义操作。

## 富文本数据

富文本数据「MUST」必须由 RD 依赖最小化原则进行处理，杜绝不安全的内容。

## CSRF

背景知识：
- [CSRF简单介绍及利用方法](http://drops.wooyun.org/papers/155)
- [Cross-Site Request Forgery (CSRF)](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29)

## Cookie使用

禁止「MUST NOT」给 baidu.com 域下设置 cookie，设置 cookie 请指定为当前域名。

禁止「MUST NOT」给页面设置 document.domain = "baidu.com"。

## 防钓鱼

似乎没啥好方法。

## 隐私数据

禁止「MUST NOT」在页面中出现 ip 相关信息 ，如有提交 ip 给 server 端的需求，请修改为其它形式，比如：由 rd 在 server 端间接获取 ip 信息。

用户的个人隐私信息：姓名、邮箱、电话、QQ 等，必须「MUST」遵守最小化原则，使用不到信息 禁止「MUST NOT」 出现在页面代码中，获取这些数据的 json 接口也必 「MUST」须经过权限控制。

## 页面跳转

获取 url 中的参数，跳转至另一个站点时， 禁止「MUST NOT」跳转至任意站点，「MUST」设置白名单，只允许跳转至规定的站点。

点击页面中的链接跳转至第三方站点的时候，建议「RECOMMENDED」 以类似百度、 Google 搜索结果中 Server 端跳转的形式进行，后端可以对 URL 进行安全性扫描，检测到是一个恶意网站、或者目标资源是可执行文件时，应给予用户强烈的警告，告知其风险。

## 第三方功能和资源

页面中嵌入的第三方功能，禁止「MUST NOT」直接内嵌第三方 JS 代码，建议以「RECOMMENDED」iframe 形式引入 。

页面中如果需要使用第三方的数据，建议 「RECOMMENDED」 由 RD 获取，尽量避免以 jsonp 方式获取，如必须使用 jsonp，请限制好第三方返回的 callback 函数名，对于不允许使用的函数名称，一律禁止。

原则上禁止「MUST NOT」使用第三方提供的资源：图片、文档等，如有必须，建议「RECOMMENDED」由 RD 抓取相关内容转存至自有 Server。因为，外链会产生站外请求，可以被利用实施 CSRF 攻击，而且往往存在性能问题。

## 点击劫持

对一些重要的操作，例如删除数据、支付等，建议「RECOMMENDED」先验证是否被嵌套。如果处于第三方页面的框架里，应弹出确认框提醒用户。确认框的坐标位置最好有一定的随机偏移，从而使攻击者构造的点击区域失效。验证方式为：

## Flash 使用

## 上传文件

建议「RECOMMENDED」上传接口所在的域名和主域名隔离，并且采用最小化原则限制允许上传的文件大小。

## JSON/JSONP协议

JSON 数据，必须「MUST」设置 http header Content-Type : application/json

以 JSONP 形式向第三方提供数据，必须「MUST」设置 http header Content-Type : application/javascript，并且callback function 名称只允许出现：数组、字母、下划线。

JSON/JSONP 方式提供数据，建议「RECOMMENDED」遵循最小化原则，只暴露需要暴露的信息，并且用白名单限制 referer 防止恶意抓取。

## Cross Domain 设置

在时 XML Httprequest 2（xhr2） 以及 font-face 如果需要支持跨域访问的需求，禁止「MUST」设置　header 为： Access-Control-Allow-Origin: * ，需要设置为允许访问的地址，比如： Access-Control-Allow-Origin: www.baidu.com


## 参考资料

[Web 前端攻防 2014](http://fex.baidu.com/blog/2014/03/web-sec-2014/)  
[New Tricks in XMLHttpRequest2](http://www.html5rocks.com/en/tutorials/file/xhr2/)  
[WooYun](http://www.wooyun.org/)  
[80sec](http://www.80sec.com/)  
[Open Web Application Security Project](https://www.owasp.org/)  
[知道创宇](http://blog.knownsec.com/)  
[上传攻击框架](http://www.owasp.org.cn/OWASP_Training/Upload_Attack_Framework.pdf)  
