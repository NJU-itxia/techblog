---
title: 前后端接口规格
date: 2018-09-08 15:10:21
tags:
categories:
- 项目文档
---

## 说明

- 下列为后端提供的REST接口，包含uri, 参数, 及返回值
- 使用ajax调用, 传递数据格式为json

<!--more-->

## 接口

### 用户登入

地址: `/customer/login`

参数
```
phone: string
```

返回
```
success: bool,
token: string?
```

---

### 用户提交预约维修

地址: `/customer/appointment`

参数: 
```
name: string,
email: string?,
campus: string,
deviceVersion: string,
systemVersion: string,
description: string,
file: string?
```

返回: 
```
success: bool
```

---

### 用户修改当前预约单

地址: `/customer/modifyAppointment`

参数: 
```
name: string,
email: string?,
campus: string,
deviceVersion: string,
systemVersion: string,
description: string,
file: string?
```

返回: 
```
success: bool
```

---

### 用户删除预约

地址: `/customer/deleteAppointment`

参数:

```
orderId: string
```

返回:

```
success: bool
```

---

### 用户登出

地址: `/customer/logout`

参数:

返回:

```
success: bool
```

---

### 用户获取当前预约

地址: `/customer/getCurrentAppointment`

参数:

返回:

```
success: bool,
appointment: Appointment
```

---

### 用户回复某个预约/为某个预约添加评论

地址: `/customer/reply`

参数:

```
appointmentId: number,
content: string
```

返回:

```
success: bool
```

---

### 用户获取历史预约

地址: `/customer/getAppointments`

参数:

返回:

```
success: bool,
appointments: [Appointment]

Appointment {
    id: string,
    name: string,
    email: string?,
    campus: string,
    deviceVersion: string,
    systemVersion: string,
    description: string,
    file: string?
}
```

实际效果举例：

```
{
    success: true,
    appointments: [
        {
            id: "asd-sda-sda",
            name: "小明",
            email: "12321232@qq.com",
            campus: "仙林",
            deviceVersion: "竟然是一部安卓机",
            systemVersion: "android7.1.1",
            description: "屏幕坏了，能帮忙换嘛",
            file: null
        },
        {
            id: "sasd-dhs-sda",
            name: "还是小明",
            email: "12321232@qq.com",
            campus: "鼓楼",
            deviceVersion: "我不知道啊",
            systemVersion: "win10",
            description: "充不进去电",
            file: null
        }
    ]
}
```

---

### 后台登陆

地址: `/admin/login`

参数:

```
username: string,
password: string
```

返回:

```
success: bool,
token: string
```

---

### 后台登出

地址: `/admin/logout`

参数:
```
token: string
```

返回:

```
success: bool
```

---

### 后台修改自己的密码

地址: `/admin/modifyPassword`

参数:
```
oldPassword: string,
newPassword: string
```

返回:
```
success: bool
```

---

### 后台查看预约

地址: `/admin/listAppointments`

参数:

```
campus: string?, //可以取"xianlin", "gulou", "all", 不传返回全部
status: string?, //可以取"finished", "unfinished", "all", 不传返回全部
```

返回:

```
success: bool,
appointments: [Appointment] //已在前面定义
```

---

### 后台接单

地址: `/admin/acceptAppointment`

参数:
```
appointmentId: string
```

返回:

```
success: bool
```

---

### 后台回复预约

地址: `/admin/reply`

参数:
```
appointmentId: string,
content: string,
```

返回:

```
success: bool
```

---

### 管理员添加后台账号

地址 `/admin/createMember`

参数:
```
username: string,
password: string,
location: string,
name: string
```

返回:
```
success: bool
```

---

### 管理员获取后台列表

地址: `/admin/listAllMembers`

参数:

返回:

```
success: bool
```

---

### 管理员修改后台密码

地址: `/admin/modifyMemberPassword`

参数:

```
memberId: string,
newPassword: string
```

返回:

```
success: bool
```