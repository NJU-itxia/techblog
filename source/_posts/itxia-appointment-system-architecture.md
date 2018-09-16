---
title: IT侠预约系统整体说明
date: 2018-09-12 15:47:59
tags:
categories:
- 项目文档
---

> IT侠预约系统设计方案，整体结构的说明文档~

<!--more-->

## 项目路径

### 前端

https://github.com/NJU-itxia/itxia-vue.git 

### 后端-node层

https://github.com/NJU-itxia/back-end-controller.git

### 后端-java server

https://github.com/NJU-itxia/back-end-java-server.git

## 整体结构

{% asset_img all.jpg 预约系统整体结构图 %}

### 流程

用户通过浏览器访问网站。前端提供页面，并通过ajax向node中间层请求服务，node中间层检查用户的权限后，根据不同后端服务器实现的不同的服务，将请求转发至对应的后端，获取到结果后向前端返回json数据，前端对返回的数据进行渲染后呈现给用户。

### 前端

- 使用vue开发
- 使用bootstrap组件做响应式设计
- 使用ajax调用后端提供的服务

### 后端

- 后端由node层统一负责与前端的通信以及权限验证
- java server负责预约用户、管理员后台等相关功能
- python server负责邮件服务、短信服务以及文件服务等（暂定）

### 数据服务

数据服务仍在计划中，可能会使用Jpa完成IT侠相关数据的服务，使用thrift或grpc提供给后端各个服务调用的接口。