---
title: Postman测试功能编写及使用
date: 2023-01-12 11:03:34
categories: 开发工具
tags: [Postman, 测试]
---

>该文档是参考官网教程，并基于自己的理解和使用进行了个别修改，需要更详细的内容请转官网；<https://learning.postman.com/docs/writing-scripts/test-scripts/>

测试脚本能够帮助你确认API是否按预期工作，服务之间的集成是否可靠，以及确认任何更改都没有破坏现有功能。

也可以使用测试代码调试api中错误处理逻辑。例如，发送请求时包含不完整数据或错误参数来验证 API的错误处理逻辑是否正常。

测试脚本可以使用 JavaScript语言编写。

## 1、添加测试脚本

测试脚本可以添加到请求、集合或文件夹中；Postman提供一些常用的测试脚本代码片段模板，可以参考模板更改为适合自己的测试逻辑。

以单个请求添加测试脚本为例，打开请求在【Tests】选项卡中输入测试脚本。测试脚本将在请求运行后执行。输出位于响应的【Test Results】选项卡中。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/97520766ed1e4ee6b253ee6fce88ef8e~tplv-k3u1fbpfcp-zoom-1.image)

## 2、编写测试脚本

测试脚本可以使用动态变量，对响应数据执行测试断言，并在请求之间传递数据。

在请求的【Tests】选项卡中，手动输入JavaScript测试代码或者选择代码编辑器旁边的测试代码模板。

点击按钮【Send】时，Postman 会在响应数据返回后运行测试脚本。

### 2.1、验证响应数据

若要验证请求返回的数据，可以在测试中使用 pm.response 对象。

使用 pm.test 函数定义测试，提供一个名称和函数，该函数返回一个布尔值（真或假），指示测试是通过还是失败。在断言中使用 ChaiJS BDD 语法和 pm.expect 来测试响应详细信息。

pm.test 函数的第一个参数是将在【Test Results】输出，使用它来识别您的测试预期，并将测试的目的传达给查看结果的任何人。

例如，测试响应状态代码是否为 200：

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

【Test Results】选项卡标题显示通过的测试数和总共运行的测试数。还可以点击Passed、Skipped、Failed查看各自的测试结果。

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3005d2a83c48469e82ac7f9d4d70bd5a~tplv-k3u1fbpfcp-zoom-1.image)

### 2.2、使用 pm.expect 格式化测试结果

使用 pm.expect 语法可为测试结果提供不同的格式。

测试请求环境示例：
```javascript
pm.test("environment to be production", function () {
    pm.expect(pm.environment.get("env")).to.equal("production");
});
```

你可以根据自己的程序使用不同的语法编写测试逻辑脚本
```
pm.test("response should be okay to process", function () {
    pm.response.to.not.be.error;
    pm.response.to.have.jsonBody("");
    pm.response.to.not.have.jsonBody("error");
});
```
也可以针对响应数据格式使用定制的语法来确定请求响应的有效性。
```
pm.test("response must be valid and have a body", function () {
    pm.response.to.be.ok;
    pm.response.to.be.withBody;
    pm.response.to.be.json;
});
```
脚本可以包含所需的任意数量的测试，并在选择【Save】时与请求详细信息的其余部分一起保存。如果您共享集合、发布文档或使用【Run in Postman】功能，您的测试代码可以被任何人查看或者导入。

### 2.3、测试脚本模板

不熟悉测试语法的同学可以使用提供的测试脚本模板来编写测试。模板位于脚本编辑器的右侧。选择模板会自动将所需的代码添加到脚本中，从而帮助您快速开始测试。添加到脚本后，您可以编辑代码段以满足特定的测试要求。

  


## 3、调试测试脚本

如果您在测试中遇到问题：

-   检查脚本中是否有任何错误。红色标记将突出显示有错误的脚本。您还可以检查响应部分以确定错误。

<!---->

-   使用 log 语句调试测试，以确保断言正确的数据。

在控制台打印日志代码：console.log()、console.info()等，具体查看：<https://learning.postman.com/docs/sending-requests/troubleshooting-api-requests/#using-log-statements>

![](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ec4f84c609ea4129a9f1574fcb0d37dc~tplv-k3u1fbpfcp-zoom-1.image)
