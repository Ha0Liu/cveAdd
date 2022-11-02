## 华夏ERP V2.3 SQL注入漏洞

华夏ERP默认集成了用户、权限、菜单、路由、分类、标签、日志、字段、表单、表格、上传、API等基本功能模块。华夏ERP是为了WEB应用敏捷开发和简化企业应用开发而诞生的、框架、模块、插件、模板均可独立升级和扩展。

华夏ERP后台在用户管理模块中的查询功能，未对前端传回的字符串进行过滤，可直接拼接SQL语句，存在SQL注入漏洞。

可通过构造SQL语句窃取系统数据库信息。

漏洞地址：http://IP:8080/index.html#/pages/manage/user.html

漏洞位置：在主页，点击系统管理-用户管理，在登录名称输入框内，插入payload点击查询。

### 漏洞利用

点击系统管理-用户管理，在登录名称输入框内，插入payload点击查询。

<img src="./pic/2.png" alt="1" style="zoom:200%;" />

查看后台日志，可以看出此payload拼接到SQL语句中进行查询。

<img src="./pic/3.jpg" alt="1" style="zoom:200%;" />
