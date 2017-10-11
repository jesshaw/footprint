---
title: Spring面试问题
tags: java,spring,interview,面试
categories: 
  - java

thumbnail: /gallery/blue-water5.jpg
---


Spring框架是最受欢迎的Java企业级web应用框架。*依赖注入*和*面象方面*是*Spring框架*的核心。
<!-- more -->

我最近提交了许多[Spring教程](https://www.journaldev.com/2888/spring-tutorial-spring-core-tutorial)，它将有助于帮你详细的解释Spring面试问题的核心概念。

## Spring面试问题列表

1. Spring框架是什么？
2. Spring框架有些什么重要的特性和优势？
3. 你对依赖注入的理解是什么？
4. Spring框架中怎么样实现依赖注入？
5. 使用Spring工具套件有什么好处？
6. 重要的Spring模块名称有哪些？
7. 你对面向切面编程的理解是什么？
8. AOP中的Aspect, Advice, Pointcut, JointPoint and Advice Arguments是什么？
9. Spring AOP 和AspectJ AOP有什么区别？
10. Spring IoC容器是什么？
11. Spring Bean是什么？
12. Spring Bean配置文件的重要性是什么？
13. 把一个类配置成Spring Bean有些什么不同方法？
14. Spring Bean有些什么不同作用域？
15. Spring Bean生命周期是什么？
16. 在Spring Bean中怎么获得ServletContext和ServletConfig对象
17. @Bean注解和@Autowired注解是什么？
18. Spring Bean自动装配有什么不同类型？
19. Spring Bean是线程安全的吗？
20. 在Spring MVC的Controller是什么？
21. 在Spring中 @Component, @Repository 和 @Service注解有什么区别？
22. DispatcherServlet 和 ContextLoaderListener是什么？
23. 在Spring中的ViewResolver是什么？
24. MultipartResolver是什么？什么时候使用？
25. Spring MVC框架怎样处理异常？
26. 在Java程序中怎样创建ApplicationContext？
27. 能有多个Spring配置文件吗？
28. ContextLoaderListener是什么？
29. 为了创建Spring MVC应用，至少需要配置什么？
30. 相对与MVC架构，你对Spring MVC框架的理解是怎样的？
31. Spring MVC应用怎样实现平地化？
32. 使用Spring怎样创建Restful Web服务并返回JSON？
33. 你使用过哪些重要的Spring注解？
34. 我们发送一个对象作为Controller操作方法的返回吗？
35. Spring MVC应用怎样上传文件？
36. Spring Web MVC架构怎样验证表单数据？
37. Spring MVC拦截器（Interceptor）是什么？怎样使用？
38. Spring JdbcTemplate类是什么？怎样使用？
39. Spring Web应用中怎样使用Tomcat JNDI数据资源？
40. 在Spring中怎样实现事务管理？
41. Spring DAO是什么？
42. 怎样集成Spring和Hibernate框架？
43. Spring Security是什么？
44. 怎样注入一个java.util.Properties到Spring Bean？
45. Spring框架使用哪些设计模式？
46. Spring框架有些什么最佳实践？


## Spring面试问题及答案

### 1. Spring框架是什么？

Spring是使用最为广泛的Java企业级框架。 Spring框架是“依赖注入”和“面向切面编程”。

Spring框架可以用于一般的java应用中。通过依赖注入的实现不同组件中的松耦合，使用Spring支持的面向切面编程我们可以像日志和认证那样跨截面执行任务。

我喜欢Spring是因它提供了许多特性和不同的功能模块，如Spring MVC和Spring JDBC。由于它是开源的，有许多在线资源和活跃的社区，使用Spring框架，在相同的时间内，工作起来更加的容易和有趣。

### 2. Spring框架有些什么重要的特性和优势？

Spring框架是基于“依赖注入”和“面向切面编程”两个设计概念建立。

Spring框架有如下特性：  
* 对开发来讲使用该框架有极少的开销，且它是一个轻量级的框架。  
* 依赖注入和控制反转编写的组件是相互独立的，Spring容器负责一起装配组件，帮助实现我们的工作。  
* Spring IoC容器管理Spring Bean的生命周期和规划具体的配置，如JNDI查找。 
* Spring MVC框架可以用于创建web应用，也可以创建返回XML或JSON的web服务。 
* 只需要非常少的配置便能支持事务管理，JDBC操作，文件上传，异常处理等。配置你可以使用注解或者配置文件实现。

使用Spring框架有如下优势：  
* 减少在应用中两个不同组件的直接依赖，一般来说Spring IoC容器负责初始化资源或beans并注入它们的依赖。  
* 在Spring框架中写单元测试更加容易。因为业务逻辑不直接依赖实际的资源实现类。可以容易的编写测试配置和注入测试目的模拟的beans。  
* 减少了重复代码的数量，如初始化对象，打开或关闭资源。我很喜欢JdbcTemplate类，是因为它帮助我们移除了所有来自JDBC编程的重复代码。  
* Spring框架被分成多个模块，它帮助我们保证我们的应用变得轻量级。例如若不需要Spring事件管理特性，则可以不添加它的依赖到项目中。  
* Spring框架支持大部分Java企业级特性，甚至更多。它总是与时俱进，如它有Android的Spring项目，帮助我们写出更好的native android的应用。这些使得Spring框架更完整，不需要因为新需求再引入不同的框架。

### 3. 你对依赖注入的理解是什么？

依赖注入设计模式允许我们移除硬编码依赖，确保应用松耦合，可扩展，可维护。把依赖解析从编译时移动运行时，我们就能够实现依赖注入模式。

使用依赖注入有这些好处：分享了关注点，减少了重复代码，组件可配置和更易单元测试。

### 4. Spring框架中怎么样实现依赖注入？

在Spring应用中我们可以基于“Spring XML”以及“注解”配置实现依赖注入。更好的理解，请阅读[Spring依赖注入实例](https://www.journaldev.com/2410/spring-dependency-injection)。

### 5. 使用Spring工具套件有什么好处？

安装扫描件到Eclipse将获得更多Spring工具套件的特性。无论如何，Eclipse中的Spring工具套件有诸如Maven支持，创建不同Spring项目类型的模板和更好Spring应用性能的tc服务。

我喜欢Spring工具套件，是因为在使用AOP切入点（pointcuts）和APO通知（advices）时，高亮显示了这些Spring组件。它清楚的显示了哪个方法将来自指定的切入点。因此相较与安装每一件小工具，在开发Spring应用时，我更喜欢使用Spring工具套件。

### 6. 重要的Spring模块名称有哪些？

Spring框架一些重要的模块如下：  
* Spring Context – 用于依赖注入。  
* Spring AOP –用于面向切面编程。  
* Spring DAO – 用于DAO模式的数据操作。  
* Spring JDBC – 用于JDBC和数据的支持。  
* Spring ORM – 用于ORM工具的支持，如Hibernate。
* Spring Web Module – 用于创建web应用。
* Spring MVC – 为创建web应用，web服务等的MVC实现。

### 7. 你对面向切面编程的理解是什么？

企业级应用有一些对不同类型的对象和应用模块的公用横向关注点是合适必要的。例始日志，事务管理，数据验证，身份认证等。
在面向切面编程中，应用模块是通过类实现的。如AOP应用模块是通过配置在不同类的方法上的模向关注点Aspects实现的。

AOP从类中分离了横向关注点任务的直接依赖，这在一般的面向对象编程中是不可做到的。例如，你可以把日志从类中分离，但这个类不午不将要调用这些方法记录日志数据（AOP就不需要）。

### 8. AOP中的Aspect, Advice, Pointcut, JointPoint and Advice Arguments是什么？

* Aspect  
将散落于各个商务物件之中的Cross-cutting concerns收集起来，设计各个独立可重用的物件，这些物件称之为Aspect，例如在动态代理中将日志的动作设计为一个LogHandler类别，LogHandler类别在AOP的术语就是Aspect的一个具体实例，在AOP中着重于Aspect的辨认，将之从商务流程中独立出来，在需要该服务的时候，缝合（Weave）至应用程式之上，不需要服务的时候，也可以马上从应用程式中脱离，应用程式中的可重用元件不用作任何的修改，例如在动态代理中的HelloSpeaker所代表的角色就是应用程式中可重用的元件，在它需要日志服务时并不用修改本身的程式码。 

另一方面，对于应用程式中可重用的元件来说，以AOP的设计方式，它不用知道处理提供服务的物件之存在，具体的说，与服务相关的API不会出现在可重用的应用程式元件之中，因而可提高这些元件的重用性，您可以将这些元件应用至其它的应用程式之中，而不会因为目前加入了某些服务而与目前的应用程式框架发生耦合。 

* Advice  
Aspect的具体实作称之为Advice，以日志的动作而言，Advice中会包括真正的日志程式码是如何实作的，像是动态代理中的LogHandler类别就是Advice的一个具体实例，Advice中包括了Cross-cutting concerns的行为或所要提供的服务。 

* Pointcut  
Pointcut是一个定义，藉由这个定义您可以指定某个Aspect在哪些Joinpoint时被应用至应用程式之上。 具体的说，您可以在某个定义档中撰写Pointcut，当中说明了哪些Aspect要应用至应用程式中的哪些Joinpoint。 

* Joinpoint  
Aspect在应用程式执行时加入商务流程的点或时机称之为Joinpoint，具体来说，就是Advice在应用程式中被呼叫执行的时机，这个时机可能是某个方法被呼叫之前或之后（或两者都有），或是某个例外发生的时候。 

* Advice Arguments  
We can pass arguments in the advice methods. We can use args() expression in the pointcut to be applied to any method that matches the argument pattern. If we use this, then we need to use the same name in the advice method from where argument type is determined.



### 9. Spring AOP 和AspectJ AOP有什么区别？
### 10. Spring IoC容器是什么？
### 11. Spring Bean是什么？
### 12. Spring Bean配置文件的重要性是什么？
### 13. 把一个类配置成Spring Bean有些什么不同方法？
### 14. Spring Bean有些什么不同作用域？
### 15. Spring Bean生命周期是什么？
### 16. 在Spring Bean中怎么获得ServletContext和ServletConfig对象
### 17. @Bean注解和@Autowired注解是什么？
### 18. Spring Bean自动装配有什么不同类型？
### 19. Spring Bean是线程安全的吗？
### 20. 在Spring MVC的Controller是什么？
### 21. 在Spring中 @Component, @Repository 和 @Service注解有什么区别？
### 22. DispatcherServlet 和 ContextLoaderListener是什么？
### 23. 在Spring中的ViewResolver是什么？
### 24. MultipartResolver是什么？什么时候使用？
### 25. Spring MVC框架怎样处理异常？
### 26. 在Java程序中怎样创建ApplicationContext？
### 27. 能有多个Spring配置文件吗？
### 28. ContextLoaderListener是什么？
### 29. 为了创建Spring MVC应用，至少需要配置什么？
### 30. 相对与MVC架构，你对Spring MVC框架的理解是怎样的？
### 31. Spring MVC应用怎样实现平地化？
### 32. 使用Spring怎样创建Restful Web服务并返回JSON？
### 33. 你使用过哪些重要的Spring注解？
### 34. 我们发送一个对象作为Controller操作方法的返回吗？
### 35. Spring MVC应用怎样上传文件？
### 36. Spring Web MVC架构怎样验证表单数据？
### 37. Spring MVC拦截器（Interceptor）是什么？怎样使用？
### 38. Spring JdbcTemplate类是什么？怎样使用？
### 39. Spring Web应用中怎样使用Tomcat JNDI数据资源？
### 40. 在Spring中怎样实现事务管理？
### 41. Spring DAO是什么？
### 42. 怎样集成Spring和Hibernate框架？
### 43. Spring Security是什么？
### 44. 怎样注入一个java.util.Properties到Spring Bean？
### 45. Spring框架使用哪些设计模式？
### 46. Spring框架有些什么最佳实践？

[原文](https://www.journaldev.com/2696/spring-interview-questions-and-answers)