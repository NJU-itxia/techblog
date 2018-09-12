---
title: 预约系统前端方案
date: 2018-09-08 13:08:53
tags:
categories:
- 项目文档
---

# itxia前端方案

> 整理自 刘洋@liuyang0717:/itxia前端方案(https://zybuluo.com/liuyang0717/note/1276062)

<!--more-->

## 技术选型(整体)

使用MVVM模式，选用vue这一MVVM框架，webpack为打包工具，nginx为代理服务器
参考开源项目:https://github.com/faisaltheparttimecoder/bulma-vuejs-demo-website
(有两个.vue文件写成.Vue了会导致报错, 改了就可以了，不行的话，就把模块导入改为全名不省略.vue后缀)

## 分工

- 视觉和样式设计(maorx,粥粥)
- 模块化/组件化开发(tipwheal/liuyang0717/天行/常卓)
- 整合测试(tipwheal/liuayang0717)

## 开发流程

|阶段|任务|
|---|---|
|第一阶段|样式设计/CSS|
|第二阶段|框架选型/构建脚手架|
|第三阶段|模块化/组件化开发|
|第三阶段|整合/测试|

### 样式设计

我们要做静态页面，用html+CSS来做，考虑响应式布局，尽可能快速布局，因为我们需要讨论然后修改

## 一些说明

> 待整理

## 参考链接

前后端分离 https://www.cnblogs.com/zhouyangla/p/7259906.html
一份django开发教程 https://legacy.gitbook.com/book/andrew-liu/django-blog/details
前后端分离 https://blog.csdn.net/justloveyou_/article/details/74379479
RESTful https://www.runoob.com/w3cnote/restful-architecture.html
不同类型数据的POST https://blog.csdn.net/xiaoliuliu2050/article/details/52875881
模块化方法 https://blog.csdn.net/Real_Bird/article/details/54869066
前端的设计模式 https://www.cnblogs.com/zhouyangla/p/6936455.html
还是前端的设计模式 https://www.cnblogs.com/iovec/p/7840228.html
DOM https://blog.csdn.net/shi199434/article/details/78947762


## 一份AJAX请求的样例

```
function login() {
    var jsonData = {
            "name":$("#name").val(),
            "email":$("#email").val(),
            "campus":$("#campus").val(),
            "deviceVersion":$("#deviceVersion").val(),
            "systemVersion":$("#systemVersion").val(),
            "description":$("#description").val(),
            "file":$("#file").val()
    };
    $.ajax({
            type: "POST",
            url: "http://127.0.0.1:3000/customer/appointment",
            contentType: "application/json",
            data: JSON.stringify(jsonData),
            dataType: "text",
            xhrFields: {
                    withCredentials: true
            },
            success: function(msg) {
                    $("#msg").text(msg);
            },
            error: function() {
                    $("#msg").text("error");
            }
    });
}
```


