---
title: jd面试问题
tags: jd
categories: 
  - java

thumbnail: /gallery/green-water2.jpg

---
<!-- more -->

1 项目经验。对自己做过的项目以及职责进行详细介绍
2 数据结构，包括List，Map ，set 等
3 线程方面
4 数据库方面（此处回答的不好，面试前准备的较为仓促，几个比较基础的问题回答的不太肯定）
5 框架方面，spring以及struts处理流程，以及IOC AOP
6 java基础，部分关键字的作用，以及几个基本类型的算术题
7 JVM 内存模型，垃圾回收算法等
8 系统优化，如何优化一个项目，从哪些方面入手
9 设计模式

## Hibernate面试问题

## Hibernate面试问题答

### 1. 现在为什么很多开发者选择SpringMVC？SpringMVC比Struts 2好吗？

1. 机制：spring mvc的入口是servlet，而struts2是filter（这里要指出，filter和servlet是不同的。
2. 性能：spring会稍微比struts快。spring mvc是基于方法的设计，而sturts是基于类。
3. 参数传递：struts是在接受参数的时候，可以用属性来接受参数，这就说明参数是让多个方法共享的。
4. 设计思想上：struts更加符合oop的编程思想， spring就比较谨慎，在servlet上扩展。
5. intercepter的实现机制：struts有以自己的interceptor机制，spring mvc用的是独立的AOP方式。
6. 另外，spring mvc的验证也是一个亮点，支持JSR303，处理ajax的请求更是方便，只需一个注解@ResponseBody ，然后直接返回响应文本即可。
7. struts2采用的传统的配置文件的方式，并没有使用传说中的0配置；spring mvc可以认为已经100%零配置了（除了配置spring mvc-servlet.xml外）。

### 2. struts2拦截器与spring 的AOP有什么区别？

拦截器是AOP的一种实现，struts2 拦截器采用xwork2的interceptor！而spring的AOP基于IoC基础,其底层采用动态代理与CGLIB代理两种方式结合的实现方式。


### 3. HashMap的原理, 以及HashMap如何扩充bucket的大小

原理答上来了，如何扩容瞎答的，之前不知道扩容之后已经哈希的MapEntry如何处理，当时就说扩容后已经哈希的全部再计算并分配到新的桶里。

### 4. 是否对多线程有了解 



### 5. 项目中的Queue，单机容量达到上限如何集群扩展 

参考Hadoop的架构，把Queue分散到不同的slave server中，并用一个”负载均衡服务器” master做反向代理，master存有job到slaves的映射表，接收broswer的Job请求，把Job分派给不同的slave server。

### 6. 知道哪些负载均衡算法 



### 7. Myisam, Innodb区别 

1、Innodb支持事务 2、Myisam支持表锁，Innodb支持行锁 3、Myisam数据索引一起存储，Innodb数据索引分开存储

### 8. Mysql索引的分类(Btree, hash)，各自使用什么情况


### 9. Btree的查找原理： 


### 10. Spring的原理(AOP IOC), AOP的原理



### 11.  cglib是动态代理吗？简要叙述cglib的原理



### 12. cglib和jdk代理的区别？



### 13. 简述三次握手，如果c端发起握手请求，s端无法立刻建立连接应该回应什么？



### 14. 求1!+(1!+3!)+(1!+3!+5!)+(1!+3!+5!+7!)+…..的和



### 15. 斐波那契数列求和。

```java
public int fib(int n){
        if(n <=1){
            return 1;
        }else{
            return fib(n-1)+fib(n-2);
        }
    }
```

### 16. 说出Servlet的生命周期

Servlet被服务器实例化后，容器运行其init方法，请求到达时运行其service方法，service方法自动派遣运行与请求对应的doXXX方法（doGet，doPost）等，当服务器决定将实例销毁的时候调用其destroy方法。


### 17. ArrayList,Vector, LinkedList的存储性能和特性

ArrayList和Vector都是使用数组方式存储数据，此数组元素数大于实际存储的数据以便增加和插入元素，它们都允许直接按序号索引元素，但是插入元素要涉及数组元素移动等内存操作，所以索引数据快而插入数据慢，Vector由于使用了synchronized方法（线程安全），通常性能上较ArrayList差，而LinkedList使用双向链表实现存储，按序号索引数据需要进行前向或后向遍历，但是插入数据时只需要记录本项的前后项即可，所以插入速度较快。

### 18. 写一个Singleton出来

Hibernate合并可以用来更新现有的值，但是这种方法从传递的实体对象中创建一个副本并返回它。返回的对象是持久化上下文的一部分，并对任何更改进行跟踪，传递的对象不被跟踪。 示例程序，阅读Hibernate合并 。


### 19. 请说出你所知道的线程同步的方法。


### 20. 多线程有几种实现方法,都是什么?同步有几种实现方法,都是什么? 


### 21. 写出两种实现方法：1-2+3-4.。。。。。+m



### 22. sql题查询本区域内大于平均销售额的订单 


### 23. 最近做的项目及用到的技术，有没新技术以及项目感想那些


### 24. 说说我接触到的设计模式，举两个自己认为理解最好的设计模式说说



### 25.

[java基础] 
1，运行时异常和一般异常的区别？ 
2，如何定位内存溢出和死锁？ 
3，Java集合是考察Java基础的重中之重，一定要熟悉，需要知道java集合中的继承关系，和各个集合用的数据结构，相互之间的区别 
4，hashmap和hashTable的区别？ 
5，hashMap的底层实现原理？底层用的数据结构？【hashmap是集合中的重点，特别重要，希望读者能有时间看一下hashMap的底层实现，添加删除元素等等，因为这个类的设计思想在Java体系应用很广，基本每个公司都问】 
6，Sychronize 和 volitile的区别？ 
7，悲观锁、乐观锁、重入锁、偏向锁的含义。 
8，Java中实现多线程的方式，常用的是哪种？ 
9，线程池有什么用？ 
Java基础部分还是读者多刷刷题吧，这个太多，我就不一一列举了。一般不会太难。

【spring】：spring的东西很多，但是可以考察的并不多。 
1，spring ioc 
2，spring di 
3，spring aop 
4，Spring aop的底层实现原理【动态代理模式】 
5，Java中实现动态代理的两种方式？有什么区别？ 
6，aop的应用场景

【hibernate】 
1，hibernate事物的隔离级别 
2，hibernate的事物传播特性 
3，hibernate中对象有哪几种状态？如何相互转化？

【struts2】 
1，struts2的启动过程？ 
2，struts2的处理请求过程？ 
这里希望读者不要去背那个struts2首页的那张图，尽量能从代码的角度去说。例如启动过程：寻找web.xml -> 配置拦截器 –>拦截器中的实现类 ->调用init方法 –>加载struts2的配置文件。这样说下去比较好

【springMVC】 
1，springMVC和struts2的主要 区别是什么？ 
2，什么是restFul风格？

【mysql】 
1，主要考索引！主要考索引！主要考索引！ 
2，mysql的存贮引擎主要有哪几种？应用场景？ 
3，mysql如何优化？【*】 
4，写两条语句，模拟死锁出现的情况 
5，内连接、左右链接的区别 
6，常用的sql一定要会写。

【redis】 
1，redis的数据结构有哪几种？ 
2，redis数据在集群种如何存贮？【hashmap】 
3，redis的key设计上应该注意哪些？ 
4，redis的持久化模式？常用的是哪个？ 
5，redis事物。 
6，redis是否可以作为注册中心。

【MongoDB】 
1，redis和MongoDB的区别？ 
2，redis和MongoDB分别适用于什么业务场景？ 
【这里建议读者自己安装一下MongoDB的redis的集群，加深理解】

【dubbox】 
1，dubbox的调用原理？【那张图】 
2，注册中心挂掉，dubbo还是否可以正常调用？ 
3，dubbox调用失败如何处理？ 
4，dubbox和spring cloud的区别？

【zookeeper】 
1，zookeeper的选举机制？ 
2，zk的分布式一致性算法？ 
3，zk的会话保持是如何做到的 
4，zk的常用命令？ 
5，zk的原语api 
6，zk有哪些功能？可以做哪些事儿？ 
【如果你说你会zk，这些必须会，zk可以考察的内容很多，欢迎补充】

【算法】 
1，String操作 
2，二叉树的几种便利方式【节点和路径】 
3，快速排序，冒泡排序 
4，算法的时间复杂度和空间复杂度的计算 
5，不会算法题，赶紧去刷LeetCode 
6，算法题不仅仅要做出来，要考虑效率问题，首先考虑hash结构！

【设计模式】 
这部分的面试一般都会让你自己说你常用的设计模式，一般说三四个就可以了，两个是工厂模式、单例模式。 
其他建议的有：代理模式、责任链模式、享元模式等等

这部分重要的是不仅仅要会写这些设计模式，一定要能说出来这些设计模式的应用场景。

【jvm】 
1，jvm的内存模型？ 
2，运行时数据区的划分？ 
3，主要的垃圾回收算法？ 
4，jvm如何优化？【jstack】 
5，列举几种商用的jvm 
6，学习jvm有什么用？说说对你的帮助

【项目部分】 
项目部分是重中之重了，一般是二面的问题，或者一般一面也会问一些，最好能有一些高并发、高可用的项目。这儿的问题要根据项目来问，单一般不会脱离以下几个方面。

1，项目目前的tps有多少？ 
2，项目如何实现高可用和高并发的？【分不同层面去说：接入如何做的， 服务层是如何做的， 数据库层是如何做的？】
3，数据库做没做读写分离？垂直拆分？ 水平拆分？ 
4，项目中的缓存用在什么地方？ 如何用的？ 
5，如何保证数据一致性的？【一般都是最终一致性】。 
6，项目配置文件如何管理的？ 
7，目前架构中如果一个服务挂掉如何处理？ 
8，Tomcat优化项有哪些？ 
9，如何做的负载均衡？



### 26. 

1、Dubbo超时重试；Dubbo超时时间设置

Dubbo是阿里开源的分布式远程调用方案(RPC)，由于网络或服务端不可靠，会导致调用出现一种不确定的中间状态（超时）。为了避免超时导致客户端资源（线程）挂起耗尽，必须设置超时时间。

服务端（Provider）可以配置的消费（Consumer）端主要属性有timeout、retries、loadbalance、actives和cluster。服务端上应尽量多配置些消费端的属性，让服务端实现者一开始就思考服务端的服务特点与服务质量。配置之间存在着覆盖，具体规则如下： 
1. 方法级配置别优于接口级别，即小Scope优先 
2. 消费端配置优于服务端配置，服务端优于全局配置 
3. Dubbo Hard Code的配置值（默认）

根据规则2，纵使消费端配置优于服务端配置，但消费端配置超时时间不能随心所欲，需要根据业务实际情况来设定。如果超时时间设置得太短，复杂业务本来就需要很长时间完成，服务端无法在设定的超时时间内完成业务处理；如果超时时间设置太长，会由于服务端或者网络问题导致客户端资源大量线程挂起。

超时配置

Dubbo消费端 

全局超时配置
```xml
<dubbo:consumer timeout="5000" />
```

指定接口以及特定方法超时配置
```xml
<dubbo:reference interface="com.foo.BarService" timeout="2000">
    <dubbo:method name="sayHello" timeout="3000" />
</dubbo:reference>
```
Dubbo服务端 

全局超时配置
```xml
<dubbo:provider timeout="5000" />
```

指定接口以及特定方法超时配置
```xml
<dubbo:provider interface="com.foo.BarService" timeout="2000">
    <dubbo:method name="sayHello" timeout="3000" />
</dubbo:provider>
```

2、[如何保障请求执行顺序](https://www.maxith.com/2017/11/29/java-thread-3/)

多线程并发的三个特性：原子性、可见性。

线程安全其实就是在多线程环境下：多个线程同时操作同一个对象时，不会产生数据不一致或者数据污染的情况。

1. 使用`synchronized`关键字。
2. 使用`Lock`锁。
3. 使用线程的`join()`方法。


3、[分布式事务](https://www.cnblogs.com/savorboard/p/distributed-system-transaction-consistency.html)与[分布式锁](http://www.hollischuang.com/archives/1716)

#### 分布式事物

分布式系统的特性

“CAP定律”中的“一致性”、“可用性”和“分区容错性”
BASE理论的核心思想就是：我们无法做到强一致，但每个应用都可以根据自身的业务特点，采用适当的方式来使系统达到最终一致性（Eventual consistency）。

分布式事务实现方式
两阶段提交（2PC），补偿事务（TCC），本地消息表，MQ（非事务消息），MQ（事务消息）


#### 分布式锁

基于数据库实现分布式锁，基于缓存（redis，memcached，tair）实现分布式锁，基于Zookeeper实现分布式锁。

使用Zookeeper实现分布式锁的优点

有效的解决单点问题，不可重入问题，非阻塞问题以及锁无法释放的问题。实现起来较为简单。

使用Zookeeper实现分布式锁的缺点

性能上不如使用缓存实现分布式锁。 需要对ZK的原理有所了解。


从理解的难易程度角度（从低到高）

数据库 > 缓存 > Zookeeper

从实现的复杂性角度（从低到高）

Zookeeper >= 缓存 > 数据库

从性能角度（从高到低）

缓存 > Zookeeper >= 数据库

从可靠性角度（从高到低）

Zookeeper > 缓存 > 数据库


4、分布式session设置

对于分布式使用Nginx+Tomcat实现负载均衡，最常用的均衡算法有IP_Hash、轮训、根据权重、随机等。不管对于哪一种负载均衡算法，由于Nginx对不同的请求分发到某一个Tomcat，Tomcat在运行的时候分别是不同的容器里，因此会出现session不同步或者丢失的问题。

实际上实现Session共享的方案很多，其中一种常用的就是使用Tomcat、Jetty等服务器提供的Session共享功能，将Session的内容统一存储在一个数据库（如MySQL）或缓存（如Redis）中。


5、执行某操作，前50次成功，第51次失败a全部回滚b前50次提交第51次抛异常，ab场景分别如何设置Spring（传播性）

6、[Zookeeper有哪些用途](https://www.jianshu.com/p/c7e8a370117d)

Zookeeper是一个用来管理大量的主机的分布式协调服务。
命名服务
配置管理
集群管理
节点领导者选举
锁定和同步服务
数据注册表

7、JVM内存模型


8、[数据库垂直和水平拆分](http://blog.csdn.net/jerome_s/article/details/52492616)

当我们使用读写分离、缓存后，数据库的压力还是很大的时候，这就需要使用到数据库拆分了。

垂直拆分是指按照业务将表进行分类，分布到不同的数据库上面

优点：
        1. 拆分后业务清晰，拆分规则明确。
        2. 系统之间整合或扩展容易。
        3. 数据维护简单。

缺点：
        1. 部分业务表无法join，只能通过接口方式解决，提高了系统复杂度。
        2. 受每种业务不同的限制存在单库性能瓶颈，不易数据扩展跟性能提高。
        3. 事务处理复杂。

水平拆分是按照某个字段的某种规则来分散到多个库之中，每个表中包含一部分数据。主要有分表，分库两种模式

优点：
        1. 不存在单库大数据，高并发的性能瓶颈。
        2. 对应用透明，应用端改造较少。     
        3. 按照合理拆分规则拆分，join操作基本避免跨库。
        4. 提高了系统的稳定性跟负载能力。

缺点：
        1. 拆分规则难以抽象。
        2. 分片事务一致性难以解决。
        3. 数据多次扩展难度跟维护量极大。
        4. 跨库join性能较差。

两张方式共同缺点
 
        1. 引入分布式事务的问题。
        2. 跨节点Join 的问题。
        3. 跨节点合并排序分页问题。

切分方案
    
        范围、枚举、时间、取模、哈希、指定等

9、MyBatis如何分页；如何设置缓存；MySQL分页

10、熟悉IO么？与NIO的区别，阻塞与非阻塞的区别

11、分布式session一致性

12、分布式接口的幂等性设计「不能重复扣款」




1、set集合从原理上如何保证不重复

1）在往set中添加元素时，如果指定元素不存在，则添加成功。也就是说，如果set中不存在(e==null ? e1==null : e.queals(e1))的元素e1,则e1能添加到set中。

2）具体来讲：当向HashSet中添加元素的时候，首先计算元素的hashcode值，然后用这个（元素的hashcode）%（HashMap集合的大小）+1计算出这个元素的存储位置，如果这个位置为空，就将元素添加进去；如果不为空，则用equals方法比较元素是否相等，相等就不添加，否则找一个空位添加。

 

2、HashMap和HashTable的主要区别是什么？，两者底层实现的数据结构是什么？


3、HashMap何时扩容，扩容的算法是什么？

HashMap何时扩容：

当向容器添加元素的时候，会判断当前容器的元素个数，如果大于等于阈值---即当前数组的长度乘以加载因子的值的时候，就要自动扩容

扩容的算法是什么：

扩容(resize)就是重新计算容量，向HashMap对象里不停的添加元素，而HashMap对象内部的数组无法装载更多的元素时，对象就需要扩大数组的长度，以便能装入更多的元素。当然Java里的数组是无法自动扩容的，方法是使用一个新的数组代替已有的容量小的数组

 

4、Java的虚拟机JVM的两个内存：栈内存和对内存的区别是什么？


5、Java中对异常时如何进行分类的？

异常整体分类：

1）Java异常结构中定义有Throwable类。 Exception和Error为其子类。

2）其中Exception表示由于网络故障、文件损坏、设备错误、用户输入非法情况导致的异常；

3）而Error标识Java运行时环境出现的错误，例如：JVM内存耗尽。

 

6、数据库设计中常讲的三范式是指什么？


7、Java中的线程池共有几种？

Java四种线程池

第一种：newCachedThreadPool

　　创建一个可根据需要创建新线程的线程池，但是在以前构造的线程可用时将重用它们。

第二种：newFixedThreadPool

　　创建一个指定工作线程数量的线程池

第三种：newScheduledThreadPool

创建一个线程池，它可安排在给定延迟后运行命令或者定期地执行。

第四种：newSingleThreadExecutor

　　创建一个使用单个 worker 线程的 Executor，以无界队列方式来运行该线程。

 

8、volatile和synchronized区别

volatile和synchronized简介：

在Java中,为了保证多线程读写数据时保证数据的一致性,可以采用两种方式：

　 1）使用synchronized关键字

　 2）使用volatile关键字：用一句话概括volatile,它能够使变量在值发生改变时能尽快地让其他线程知道。

两者的区别：

1）volatile本质是在告诉jvm当前变量在寄存器中的值是不确定的,需要从主存中读取,synchronized则是锁定当前变量,只有当前线程可以访问该变量,其他线程被阻塞住.

2）volatile仅能使用在变量级别,synchronized则可以使用在变量,方法.

3）volatile仅能实现变量的修改可见性,而synchronized则可以保证变量的修改可见性和原子性.

4）volatile不会造成线程的阻塞,而synchronized可能会造成线程的阻塞.

 

9、Spring的特性

1.方便解耦，简化开发

通过Spring提供的IoC容器，我们可以将对象之间的依赖关系交由Spring进行控制，避免硬编码所造成的过度程序耦合。

2.AOP编程的支持

通过Spring提供的AOP功能，方便进行面向切面的编程。

3.声明事物的支持

在Spring中，我们可以从单调烦闷的事务管理代码中解脱出来，通过声明式方式灵活地进行事务的管理，提高开发效率和质量。

4.方便程序的测试

可以用非容器依赖的编程方式进行几乎所有的测试工作。例如：Spring对Junit4支持，可以通过注解方便的测试Spring程序。

5.方便集成各种优秀框架

Spring不排斥各种优秀的开源框架，相反，Spring可以降低各种框架的使用难度，Spring提供了对各种优秀框架（如Struts,Hibernate、Hessian、Quartz）等的直接支持。

6.降低Java EE API的使用难度

Spring对很多难用的Java EE API（如JDBC，JavaMail，远程调用等）提供了一个薄薄的封装层，通过Spring的简易封装，这些Java EE API的使用难度大为降低。

 

10、spring aop的应用场景：

AOP用来封装横切关注点，具体可以在下面的场景中使用

Authentication 权限

Caching 缓存

Context passing 内容传递

Error handling 错误处理

Lazy loading 懒加载

Debugging 调试

logging, tracing, profiling and monitoring 记录跟踪 优化 校准

Performance optimization 性能优化

Persistence 持久化

Resource pooling 资源池

Synchronization 同步

Transactions 事务

 

11、Mybaits中#和$区别

1）${}是Properties文件中的变量占位符，它可以用于标签属性值和sql内部，属于静态文本替换，比如${driver}会被静态替换为com.mysql.jdbc.Driver。

2）#{}是sql的参数占位符，Mybatis会将sql中的#{}替换为?号，在sql执行前会使用PreparedStatement的参数设置方法，按序给sql的?号占位符设置参数值，比如ps.setInt(0, parameterValue)，#{item.name}的取值方式为使用反射从参数对象中获取item对象的name属性值，相当于param.getItem().getName()。

 

12、排序都有哪几种方法？请列举。用JAVA 实现一个快速排序。

排序的方法有：

插入排序（直接插入排序、希尔排序），交换排序（冒泡排序、快速排序），选择排序（直接选择排序、堆排序），归并排序，分配排序（箱排序、基数排序）；

快速排序的伪代码：

//使用快速排序方法对a[ 0 :n- 1 ]排序

从a[ 0 :n- 1 ]中选择一个元素作为middle，该元素为支点；

把余下的元素分割为两段left 和right，使得left 中的元素都小于等于支点，

而right 中的元素都大于等于支点；

递归地使用快速排序方法对left 进行排序；

递归地使用快速排序方法对right 进行排序；

所得结果为left + middle + right。

 

为了更好的让大家应对笔试，除了以上精选笔试题外，还准备了历年来几百道笔试题，包括：（java，spring、数据结构和算法、mybatis、redis、serlvet、jsp等），供大家学习。



1、说一下java类集
2、字符串哈西相等，equals相等吗？反过来呢？
3、Spring的工作原理，控制控制反转是怎么实现的，自己写过滤器过滤编码怎么实现
4、框架的源码有没有看过
5、动态代理是怎么实现的
6、action是单实例还是多实例
1) Struts2 会对每一个请求,产生一个Action的实例来处理.
2) Spring的Ioc容器管理的bean默认是单实例的.
Struts2与Spring整合后, 由spring来管理Struts2的Action,  bean默认是单实例有情况下,会有如下问题:


1) Action是单例,其中的FieldError,actionerror中的错误信息 会累加, 即使再次输入了正确的信息,也过不了验证.


2) Struts2的Action是有状态的,他有自己的成员属性, 所以在多线程下,会有问题.
如何解决?
方案一: 就是不用单例, spring中bean的作用域设为prototype,每个请求对应一个实例.


方案二: spring中bean的作用域设为session ,每个session对应一个实例,解决了多线程问题.(如何设置作用域请看: 4 spring中bean的作用域 )


再写一个拦截器, 清空 FieldError与actionerror


7、怎么配置bean
8、修改单实例多实例
9、java的设计模式
10、事务的控制
11、赃读
脏读又称无效数据的读出，是指在数据库访问中，事务T1将某一值修改，然后事务T2读取该值，此后T1因为某种原因撤销对该值的修改，这就导致了T2所读取到的数据是无效的。
脏读就是指当一个事务正在访问数据，并且对数据进行了修改，而这种修改还没有提交到数据库中，这时，另外一个事务也访问这个数据，然后使用了这个数据。因为这个数据是还没有提交的数据，那么另外一个事务读到的这个数据是脏数据，依据脏数据所做的操作可能是不正确的。
12、事务的传播属性
REQUIRED：业务方法需要在一个事务中运行。如果方法运行时，已经处在一个事务中，那么加入到该事务，否则为自己创建一个新的事务。(默认是这种事务行为)
NOT_SUPPORTED：声明方法不需要事务。如果方法没有关联到一个事务，容器不会为它开启事务。如果方法在一个事务中（另一个bean）被调用，该事务会被挂起，在方法调用结束后，原先的事务便会恢复执行。
REQUIRESNEW：属性表明不管是否存在事务，业务方法总会为自己发起一个新的事务。如果方法已经运行在一个事务中，则原有事务会被挂起，新的事务会被创建，直到方法执行结束，新事务才算结束，原先的事务才会恢复执行。
MANDATORY：该属性指定业务方法只能在一个已经存在的事务中执行，业务方法不能发起自己的事务。如果业务方法在没有事务的环境下调用，容器就会抛出例外。


SUPPORTS：这一事务属性表明，如果业务方法在某个事务范围内被调用，则方法成为该事务的一部分。如果业务方法在事务范围外被调用，则方法在没有事务的环境下执行。
Never：指定业务方法绝对不能在事务范围内执行。如果业务方法在某个事务中执行，容器会抛出例外，只有业务方法没有关联到任何事务，才能正常执行。
NESTED：如果一个活动的事务存在，则运行在一个嵌套的事务中. 如果没有活动事务, 则按REQUIRED属性执行.它使用了一个单独的事务， 这个事务拥有多个可以回滚的保存点。内部事务的回滚不会对外部事务造成影响。它只对DataSourceTransactionManager事务管理器起效
 
数据库系统提供了四种事务隔离级
(两个或者多外并发事务当中)
脏读：一个事务读取到另一事务未提交的更新新据。
不可重复读：在同一事务中，多次读取同一数据返回的结果有所不同。换句话说就是，后续读取可以读到另一事务已提交的更新数据。相反，“可重复读”在同一事务中多次读取数据时，能够保证所读数据一样，也就是，后续读取不能读到另一事务已提交的更新数据。
幻读：一个事务读取到另一事务已提交的insert数据
13、购物车是怎么实现的
14、GMS
15、统计一天的订单量
16、IN HAVING  exsit
17、有没有用过定时任务
18、JVM的内存管理，
19、堆内存、栈内存溢出
20、说一下缓存
21、统计所有重名用户
select name,count(*) from tab group by name having count(*)>1;








1.如何调用别人写的接口？自己写的接口，如何让别人调用
2.中间间
3.List、set、Map的底层实现原理


京东面试题
1.简单的懒汉式在多线程环境下不是线程安全的。有人提出在getInstance()方法上同步锁，但是锁住一整个方法可能粒度过大，不利于效率。
单例模式的饿汉式，在定义自身类型的成员变量时就将其实例化，使得在Singleton单例类被系统（姑且这么说）加载时就已经被实例化出一个单例对象，从而一劳永逸地避免了线程安全的问题。



## 引用
1. [原文](https://www.journaldev.com/3633/hibernate-interview-questions-and-answers?utm_source=website&utm_medium=menubar&utm_campaign=Top-Menu-Bar)
