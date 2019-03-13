# letao_mall
使用dubbo+springboot改造的乐淘商城（原淘淘商城）
乐淘项目类似于JD的全品类B2C电商项目,选择该项目的主要原因是电商项目具有高并发,数据量大,技术新,技术范围广等特点,
此项目,基于SOA的架构来实现。采用dubbo+zookeeper实现表现层和服务层之间的RPC通信,数据库使用的是Mysql。
使用了SpringBoot快速开发项目,使用了rabbitmq消息中间件进行异步通信和解耦等,项目分为前台后台，前台门户系统提供活动商品展示，
商品分类,商品搜索，购物车，订单，支付，个人中心等模块，后台管理系统提供管理的商品,内容管理，订单管理等模块
前端技术：

- **基础的HTML、CSS、JavaScript（基于ES6标准**）
- **JQuery**
后端技术：

- 基础的SpringMVC、Spring 5.0和MyBatis3
- Spring Boot 2.0.1版本
- dubbo
- zookeeper
- Redis-4.0
- RabbitMQ-3.4
- slor
- nginx-1.10.2：
- FastDFS - 5.0.8
- MyCat
- Thymeleaf
- JavaMail
## 设计模式:

(1) MVC模式,利用SpringMVC框架可以很多的实现MVC模式,请求经过Controller,在获取或者修改相关的模型数据,

选择视图展示.

 **Model（模型**）：数据模型，提供要展示的数据，因此包含数据和行为，可以认为是领域模型或JavaBean组件（包含数据和行为），不过现在一般都分离开来：Value Object（数据） 和 服务层（行为）。也就是模型提供了模型数据查询和模型数据的状态更新等功能，包括数据和业务。

**View（视图）：**负责进行模型的展示，一般就是我们见到的用户界面，客户想看到的东西。

**Controller（控制器）：**接收用户请求，委托给模型进行处理（状态改变），处理完毕后把返回的模型数据返回给视图，由视图负责展示。 也就是说控制器做了个调度员的工作。

(2) DAO模式,在项目开发中主要用在数据层，封装数据的访问操作，为业务层提供数据服务。

 

(3) IoC模式,在项目开发中业务层有大量对象，他们之间存在依赖关系，可以使用IoC模式减少他们之间的代码耦合，提高系统的可扩展性。实际项目中使用的Spring框架来实现业务组件的装配。

 

(4) Observer模式，消息中间件应用到了观察者模式。当商品的属性修改,进行异步通知订阅使用模板引擎生成静态页面,为Solr索引库自动的创建索引

 

(5) singleton单例模式和Factory工厂模式结合使用在项目中无需使用者了解过多的细节就可获取有关的对象实例。通过SessionFactory来获取Session。

 

(6) bridge模式，在项目中使用JDBC驱动访问数据库。

