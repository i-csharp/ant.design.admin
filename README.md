# 基于Ant.Design的后台权限管理
## 简介
基于Spring Boot,SpringMvc,Spring Data Rest,Ant.design的后台权限管理
通过node的代理和reset风格的接口实现前后端分离

## 技术和功能
- React
- dva
- 用户管理
- 资源管理
- 角色管理
## 前端
 前端登陆界面参照 Ant-Admin https://github.com/zuiidea/antd-admin
 前端通过访问后台的接口解析数据呈现到页面上，个人觉得redux甚是麻烦，所以没用redux控制state
## 后端
 - 权限设计  
    权限表有四张：用户表，资源表，权限表，角色表 
    关联关系表有三张：用户表-角色表（多对多） 角色表-权限表（多对多） 权限表-资源表（多对一）
    根据REST的风格，POST、DELETE、PUT、GET四种请求，所对应的是对资源的增删改查，体现在数据库里面
    就是 权限-资源 多对一的关系  
    校验过程：用户先请求一个Token，之后的请求都要附带Token信息，
    如果Token没有过期，则判断用户的角色是否对资源有对应的操作
 
后端权限表设计参照 https://cnodejs.org/topic/551802d3687c387d2f5b2906

所有的操作要获取Token才可以操作，

## 效果图
![Alt text](https://github.com/zxcvbnmzsedr/ant.design.admin/blob/master/view/login.png?raw=true)
![Alt text](https://github.com/zxcvbnmzsedr/ant.design.admin/blob/master/view/users.png?raw=true)
![Alt text](https://github.com/zxcvbnmzsedr/ant.design.admin/blob/master/view/source.png?raw=true)
![Alt text](https://github.com/zxcvbnmzsedr/ant.design.admin/blob/master/view/role.png?raw=true)