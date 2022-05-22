# Spring Boot前世今生

为了简化Spring应用的搭建和开发过程，Pivotal团队在Spring基础上开发了一套全新的开源框架，Spring Boot。该框架凭借着编码简单、配置简单、部署简单以及监控简单的特性逐渐成为Java EE开发者首选的开发框架。

# Spring MVC设计模式

springboot组装了spring和springmvc，SSM架构是指Spring，SpringMVC以及MyBatis。

<img src="Spring%20MVC.assets/image-20220506115935750.png" style="zoom:50%;" />



## 视图层



## 控制层

控制层：接收前端的请求，通过service的接口来控制业务流程。

视图层：前面展示数据的界面

## 业务层



**Service层**，将复杂的业务拆分成多个细粒度的DAO(DataAccessObjects)操作。

包含了serviceImpl（service接口的实现类），是提供给controller使用的，针对某些业务将dao层的对于某些表的增删改查进行组合。



## 持久层

mybatisplus

**mapper，** 相当于DAO层，位于业务逻辑和持久化数据之间实现对持久化数据的访问。通俗来讲就是将数据库操作都封装起来。

优点：1、隔离了数据访问代码和业务逻辑代码。业务逻辑代码直接调用DAO方法即可，完全感觉不到数据库表的存在。**数据访问层代码变化不影响业务逻辑代码。**

2、隔离了不同数据库实现，如果底层数据库变化，只要增加新的DAO接口的实现类即可，原有MySQL实现不用修改。



## 异常处理exception

## 数据传输对象dto

## 工具类

## 配置文件

## JWT

json web token，主要用来对用户的身份进行认证。当服务器接收了用户的登录请求并认证后，生成一个token，发回给用户；每次用户与服务器进行通信时，都要携带这个token，使得服务器可以验证当前用户的身份。

结构：header、payload、signature三部分组成。header部分是用来描述JWT的，主要是用来标识这是一个JWT结构。payload用来存放实际需要传递的有关身份识别的数据。signature是对前两部分的数字签名，主要是用来防止用户更改前两部分。

Authorization（授权）：使用JWT



## SQL执行

先连接sql，然后分析sql语句，再进行sql优化，然后执行sql语句，如果sql要操作的数据不在缓存池里，就先从磁盘找到数据，然后加载到缓存池，然后写undo日志、binlog和redo日志，然后开始执行sql语句，最后随机把缓存池里的最新数据写回到磁盘。

<img src="Spring%20MVC.assets/image-20220507125054436.png" alt="image-20220507125054436" style="zoom:40%;" />





