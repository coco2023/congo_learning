### 刚果商城
---

DDD相关文章

1. https://tech.meituan.com/2024/05/27/ddd-in-business.html
2. https://www.giscafer.com/blog/post-52
3. https://www.cnblogs.com/rickie/p/14993450.html
4. https://tech.meituan.com/2024/05/09/ddd-practice-trading-system.html   业务最为复杂的境外交易业务作为基础的主领域模型

---

学习记录

1. congomall-framework-all   基础组件 [[README](./congomall-framework-all)]
2. congomall-customer-user   用户服务 [[README](./congomall-customer-user)]
3. congomall-gateway  外部网关 [[README](./congomall-gateway)]	 

---

解决问题

1. 百万数据量导入&导出，如何保障内存安全和导出性能？
2. 线上应用运行触发 OOM（内存溢出或泄漏），如何第一时间通知到开发者？
3. 如何解决雪花算法在集群环境下，生成 ID 重复问题？
4. 按照时间字段分库分表，如何支持业务 ID 高效查询记录？
5. 订单业务根据买家 ID 进行分库分表，如何支持订单 ID 高效查询记录？
6. 如何将千万数据通过并发的形式高性能导入 ElasticSearch？
7. 如何结合复杂业务场景解决缓存穿透、缓存雪崩、缓存击穿、多级缓存？

--- 

官网地址：[magestack.cn](https://magestack.cn)

体验地址：[cmall.magestack.cn](http://cmall.magestack.cn)

![](https://images-machen.oss-cn-beijing.aliyuncs.com/1673165270664-5d0c4381-96ef-427b-a58d-9b21140eabe0-20230306173625527.png)

### 📚 能学到什么

---

这个系统没有很完整的商城业务，但是提供了偏架构层面有用的工具和参考，能帮助大家在实际项目中更好地解决问题。

- 基于 DDD 领域驱动模型设计实现的商品、购物车、订单、用户、消息以及支付服务。

- 掌握分布式锁、分布式事务、分布式搜索、分布式缓存、分布式限流以及分库分表等核心技术。
- 完成基础组件抽象，规约、缓存、幂等、分布式 ID、数据持久层、脱敏以及日志等底层组件库。
- 基于 Agent 开发字节码流量监控，监控项目接口 QPS、响应时间和异常请求等核心指标。
- 掌握常用设计模式实战场景，策略、责任链、装饰器、观察者以及适配器等设计模式。

### 🔨 如何开始

---

刚果商城核心有两块，分别是商城业务和基础架构，通过认真学习分别可以收获以下两种能力提升。

- 商城业务：通过学习刚果商城中复杂业务处理场景，增加自己的复杂业务处理能力。

- 基础架构：尝试跟着基础架构部分自己把轮子都造一遍，以此提高自己方案设计和公共代码开发能力。

1）商城核心业务

目前 [前端页面](http://cmall.magestack.cn) 正在开发中，暂时没有开源出来，所以大家需要通过接口请求访问。接口如何访问详细看下文。

1. [初始化数据库](https://magestack.cn/preparation/init-datasource.html)，比如商品库、订单库、用户库、支付库、购物车库等；
2. [通过 Docker 安装项目中依赖的中间件](https://magestack.cn/preparation/environment/mysql_5.7_install.html)，比如 Nacos2、MySQL、Seata、RocketMQ 等；
3. 学习接口调用流程，项目接口目前全量放入 Apifox 软件中，可通过在线访问；
4. [查看不同微服务之间的依赖关系](https://magestack.cn/fast-start/user.html)，并根据文档中的描述进行修改指定参数；
5. 找到自己感兴趣的模块功能 Debug 源代码，参考代码设计。

<img width="817" alt="image" src="https://user-images.githubusercontent.com/77398366/229265338-dc16abdb-665a-49a7-a42a-653fbe3e5060.png">

2）基础架构

基础架构相关的代码都在 `congomall-framework-all` 模块中，可以通过官网查看如何实现，或者通过 [视频教学](https://magestack.cn/preparation/video.html) 来学习如何开发基础架构代码。

<img width="1090" alt="image" src="https://user-images.githubusercontent.com/77398366/229265310-7fa8b406-b621-4334-91d6-911c0b95dce3.png">

### 👍 服务列表

---

刚果商城项目是马哥从零到一写出来的，当前已开发模块如下所述，没有完成的请耐心等待。

|    | 模块名称                    | 服务名称               | 访问地址                                          |
|----|-------------------------|--------------------|-----------------------------------------------|
| 1  | congomall-message       | 消息发送 eg：邮件、公众号、短信等 | [http://localhost:8001](http://localhost:8001) |
| 2  | congomall-customer-user | 用户服务               | [http://localhost:8002](http://localhost:8002) |
| 3  | congomall-gateway       | 外部网关               | [http://localhost:8003](http://localhost:8003) |
| 4  | congomall-product       | 商品服务               | [http://localhost:8004](http://localhost:8004) |
| 5  | congomall-product-job   | 商品 Job 服务          | [http://localhost:9001](http://localhost:9001) |
| 6  | congomall-cart          | 购物车服务              | [http://localhost:8005](http://localhost:8005) |
| 7  | congomall-order         | 订单服务               | [http://localhost:8006](http://localhost:8006) |
| 8  | congomall-pay           | 支付服务               | [http://localhost:8007](http://localhost:8007) |
| 9  | congomall-basic-data    | 基础数据服务             | [http://localhost:8008](http://localhost:8008) |
| 10 | congomall-bff           | 商城聚合层（BFF）            | [http://localhost:8009](http://localhost:8009) |

### 🚅 接口请求

---

目前刚果商城已开发的接口已汇总至下述接口文档中，本地启动对应项目，通过接口文档访问查看效果。

[https://www.apifox.cn/web/project/1038592/apis/api-50106328-run](https://www.apifox.cn/web/project/1038592/apis/api-50106328-run)

如果需要通过 Apifox 直接调用，需要安装对应浏览器内网插件，这里把插件安装包装上，跟着教程安装即可使用。

安装文档：[https://www.apifox.cn/help/app/web/browser-extension](https://www.apifox.cn/help/app/web/browser-extension)

![](https://images-machen.oss-cn-beijing.aliyuncs.com/1673619450701-2c7d5fe3-bf39-4c79-84e8-2ae4f0211a79.png)

### 🛡 模块介绍

---

刚果商城后端系统模块介绍如下所示。

```txt
├── congomall-basic-data  || -- # 基础数据服务
│   ├── congomall-basic-data-application
│   ├── congomall-basic-data-domain
│   ├── congomall-basic-data-infrastructure
│   ├── congomall-basic-data-interface
├── congomall-bff  || -- # 商城 BFF 聚合层
│   ├── congomall-bff-biz
│   ├── congomall-bff-remote
│   ├── congomall-bff-web
├── congomall-cart  || -- # 购物车服务
│   ├── congomall-cart-application
│   ├── congomall-cart-domain
│   ├── congomall-cart-infrastructure
│   ├── congomall-cart-interface
├── congomall-coupon  || -- # 优惠券服务
├── congomall-customer-user  || -- # C端用户服务
│   ├── congomall-customer-user-application
│   ├── congomall-customer-user-domain
│   ├── congomall-customer-user-infrastructure
│   ├── congomall-customer-user-interface
│   ├── congomall-customer-user-mock
├── congomall-framework-all  || -- # 基础组件
│   ├── congomall-base-spring-boot-starter  || -- # 顶层抽象基础组件
│   ├── congomall-cache-spring-boot-starter  || -- # 缓存组件
│   ├── congomall-common-spring-boot-starter  || -- # 公共工具包组件
│   ├── congomall-convention-spring-boot-starter  || -- # 项目规约组件
│   ├── congomall-database-spring-boot-starter  || -- # 数据库持久层组件
│   ├── congomall-ddd-framework-core  || -- # DDD抽象接口组件
│   ├── congomall-designpattern-spring-boot-starter  || -- # 设计模式抽象组件
│   ├── congomall-distributedid-spring-boot-starter  || -- # 分布式ID组件
│   ├── congomall-flow-monitor-agent  || -- # 微服务流量监控组件
│   ├── congomall-httputil-spring-boot-starter  || -- # Http网络调用组件
│   ├── congomall-idempotent-spring-boot-starter  || -- # 分布式幂等组件
│   ├── congomall-log-spring-boot-starter  || -- # 日志打印组件
│   ├── congomall-minio-spring-boot-starter  || -- # 文件存储组件
│   ├── congomall-openfeign-spring-boot-starter  || -- # 微服务调用组件
│   ├── congomall-rocketmq-spring-boot-starter  || -- # 分布式消息队列组件
│   ├── congomall-sensitive-spring-boot-starter  || -- # 前端返回数据脱敏组件
│   ├── congomall-swagger-spring-boot-starter  || -- # 文档API组件
│   ├── congomall-web-spring-boot-starter  || -- # Web组件
│   ├── congomall-xxljob-spring-boot-starter  || -- # 定时任务组件
├── congomall-gateway  || -- # 网关服务
├── congomall-message  || -- # 消息服务
│   ├── congomall-message-application
│   ├── congomall-message-domain
│   ├── congomall-message-infrastructure
│   ├── congomall-message-interface
├── congomall-order  || -- # 订单服务
│   ├── congomall-order-application
│   ├── congomall-order-domain
│   ├── congomall-order-infrastructure
│   ├── congomall-order-interface
├── congomall-pay  || -- # 支付服务
│   ├── congomall-pay-application
│   ├── congomall-pay-domain
│   ├── congomall-pay-infrastructure
│   ├── congomall-pay-interface
├── congomall-product  || -- # 商品服务
│   ├── congomall-product-application
│   ├── congomall-product-domain
│   ├── congomall-product-infrastructure
│   ├── congomall-product-interface
│   ├── congomall-product-job
├── congomall-test-all  || -- # 测试用例
│   ├── congomall-flow-monitor-agent-test
│   ├── congomall-h2-test
│   ├── congomall-oom-test
│   ├── congomall-smooth-sharding-test
│   ├── congomall-yaml-test
├── dev-support  || -- # 开发工具包
```

### 📈 技术选型

---

当前暂时先梳理后端技术，前端开发后再行梳理。

|    | 技术                  | 名称                 | 官网                                                                                                 |
|----|---------------------|--------------------|----------------------------------------------------------------------------------------------------|
| 1  | Spring Boot         | 基础框架               | [https://spring.io/projects/spring-boot](https://spring.io/projects/spring-boot)                   |
| 2  | MyBatis-Plus        | 持久层框架              | [https://baomidou.com](https://baomidou.com)                                                       |
| 3  | HikariCP            | 数据库连接池             | [https://github.com/brettwooldridge/HikariCP](https://github.com/brettwooldridge/HikariCP)         |
| 4  | Redis               | 分布式缓存数据库           | [https://redis.io](https://redis.io)                                                               |
| 5  | RocketMQ            | 消息队列               | [https://rocketmq.apache.org](https://rocketmq.apache.org)                                         |
| 6  | ShardingSphere      | 数据库生态系统            | [https://shardingsphere.apache.org](https://shardingsphere.apache.org)                             |
| 7  | SpringCloud Alibaba | 分布式框架              | [https://github.com/alibaba/spring-cloud-alibaba](https://github.com/alibaba/spring-cloud-alibaba) |
| 8  | SpringCloud Gateway | 网关框架               | [https://spring.io/projects/spring-cloud-gateway](https://spring.io/projects/spring-cloud-gateway) |
| 9  | Seata               | 分布式事务框架            | [http://seata.io/zh-cn/index.html](http://seata.io/zh-cn/index.html)                               |
| 10 | Canal               | MySQL 订阅 BinLog 组件 | [https://github.com/alibaba/canal](https://github.com/alibaba/canal)                               |
| 11 | MinIO               | 文件存储框架             | [https://min.io](https://min.io)                                                                   |
| 12 | Swagger3            | 项目 API 文档框架        | [http://swagger.io](http://swagger.io)                                                             |
| 13 | Knife4j             | Swagger 增强框架       | [https://doc.xiaominfo.com](https://doc.xiaominfo.com/)                                            |
| 14 | Maven               | 项目构建管理             | [http://maven.apache.org](http://maven.apache.org)                                                 |
| 15 | Redisson            | Redis Java 客户端     | [https://redisson.org](https://redisson.org/)                                                      |
| 16 | Sentinel            | 流控防护框架             | [https://github.com/alibaba/Sentinel](https://github.com/alibaba/Sentinel)                         |
| 17 | Hippo4j             | 动态线程池框架            | [https://hippo4j.cn](https://hippo4j.cn)                                                           |
| 18 | XXL-Job             | 分布式定时任务框架          | [http://www.xuxueli.com/xxl-job](http://www.xuxueli.com/xxl-job)                                   |
| 19 | SkyWalking          | 分布式链路追踪框架          | [https://skywalking.apache.org](https://skywalking.apache.org/)                                    |
| 20 | JetCache            | Java 缓存框架          | [https://github.com/alibaba/jetcache](https://github.com/alibaba/jetcache)                                    |
