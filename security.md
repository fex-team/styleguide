前端安全规范
========

本文档描述前端开发人员在应用开发中，需要关注的安全问题和相应的编码规范，旨在杜绝一些常见的安全隐患。

**说明：**文档中使用的关键字「MUST」,「MUST NOT」,「REQUIRED」,「SHALL」,「SHALL NOT」,「SHOULD」,「SHOULD NOT」,「RECOMMENDED」,「MAY」和「OPTIONAL」在 RFC2119 中有说明。

## XSS防御

请务必阅读：[终极XSS防护备忘录](http://www.fooying.com/chinese-translationthe-ultimate-xss-protection-cheatsheet-for-developers/) 根据其中的描述做好数据转义操作。

## 富文本数据

富文本数据「MUST」必须由 RD 依赖最小化原则进行处理，杜绝不安全的内容。

## CSRF

背景知识：[CSRF简单介绍及利用方法](http://drops.wooyun.org/papers/155) [Cross-Site Request Forgery (CSRF)](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29)

## Cookie使用

「MUST NOT」给 baidu.com 域下设置 cookie，设置 cookie 请指定为当前域名。

## 防钓鱼

## 隐私数据

禁止「MUST NOT」在页面中出现 ip 相关信息 ，如有提交 ip 给 server 端的需求，请修改为其它形式，比如：由 rd 在 server 端间接获取 ip 信息。

用户的个人隐私信息：姓名、邮箱、电话、QQ 等，必须「MUST」遵守最小化原则，使用不到信息 禁止「MUST NOT」 出现在页面代码中，获取这些数据的 json 接口也必 「MUST」须经过权限控制。

## 页面跳转

获取 url 中的参数，跳转至另一个站点时， 禁止「MUST NOT」跳转至任意站点，「MUST」设置白名单，只允许跳转至规定的站点。

## 第三方功能和资源

页面中嵌入的第三方功能，禁止「MUST NOT」直接内嵌第三方 JS 代码，建议以「RECOMMENDED」iframe 形式引入 。

页面中如果需要使用第三方的数据，建议 「RECOMMENDED」 由 RD 获取，尽量避免以 jsonp 方式获取，如必须使用 jsonp，请限制好第三方返回的 callback 函数名，对于不允许使用的函数名称，一律禁止。

在使用第三方提供的图片、文档时，建议「RECOMMENDED」由 RD 抓取相关内容

禁止「MUST NOT」

## Flash 使用
