# Interview-Questions
This is a repository with what I believe are good interview questions regarding Java, Spring, SQL, Design Patterns, Refactorings etc

## Spring

### Spring Core
1. What are the benefits of using Spring
> Lightweigth - There is a slight overhead of using the framework in development
> Inversion of Control (IoC) - Spring container takes care of wiring dependencies of various objects instead of creating or looking for dependent objects.
> Aspect-Oriented Programming (AOP) - Spring supports AOP to seperate business logic from system services.
> IoC container - manages Spring Bean life cycle and project-specific configurations
> MVC framework - used to create web applications or RESTful web services, capable of returning XML/JSON responses.
> Transaction management - reduces the ammount of boilerplate code in JDBC operations, file uploading, etc. either by using Java annotations or by Spring Bean XML configuration file
> Exception Handling - Spring provides a convenient API for translating technology-specific exceptions into unchecked exceptions.
2. What is Dependency Injection
> Dependency Injection, an aspect of Inversion of Control (IoC), is a general concept stating that we do not create our objects manually but instead describe how they should be created. Then an IoC container will instantiate required classes if needed.
3. What is the difference between BeanFactory and ApplicationContext
> BeanFactory is an interface representing a container that provides and manages bean instances. The default implementation instantiates beans lazily when getBean() is called. Also, doesn't support i18n and annotation based depedency
> In contrast, ApplicationContext is an interface representing a container holding information, metadata and beans in the application. It also extends the BeanFactory interface, but the default implementation instantites beans eagerly when the application starts. However, this behavior can be overridern for individula beans
> 
4. How to define the scope of a Bean
> In order to set Spring Bean's scope, we can use @Scope annotation or "scope" attribute in XML configuration files. Note that there are five supported scopes
> 1. Singleton (default)
>> Scopes a single bean definition to a signle object instance per Spring IoC container
> 2. Prototype
>> Scopes a single bean definition to any number of object instances.
> 3. Request
>> Scopes a single bean definition to the lifecycle of a single HTTP request; that is, each HTTP request has its own instance of a bean created off the back of a single bean definition. Only valid in the context of a web-aware Spring ApplicationContext.
> 4. Session
>> Scopes a single bean definition to the lifecycle of an HTTP session. Only valid in the context of web-aware Spring ApplicationContext.
> 5. Global-session
>> Scopes a single bean definition to the lifecycle of a global HTTP session. Typically only valid when used in a portlet context. Only valid in the context of a web-aware Spring ApplicationContext.
5. Are Singleton Beans Thread-Safe?
> No, singleton beans are not thread-safe, as thread safety is about execution, whereas the singleton is a design pattern focusing on creation. Thread safety depends on the bean implementation itself.
6. What is Spring boot?
> Spring Boot is a project that provides a pre-configured set of frameworks to reduce boilerplate configuration. This way, we can have a Spring application up and running with the smallest ammount of code.

### Spring Web MVC
1. What is a Controller in Spring MVC?
> Simple put, all the requests processed by the DispatcherServlet are directed to classes annotated with @Controller. Each controller class maps one or more requests to methods that process and execute the requests with provided inputs.
2. How does the @RequestMapping annotation work?
> The @RequestMapping annotation is used to map web requests to Spring Controller methods. In addition to simple use cases, we can use it for mapping of HTTP headers, binding parts of the URI with @PathVariable, and working with URI parameters and the @RequestParam annotation.

### Spring Data Acess
1. What is Spring JdbcTemplate class and how to use it?
> The Spring JDBC template is the primary API through which we can access database operations logic that we're interested in:
> 1. Creation and closing the connections
> 2. Executing statements and stored procedure calls
> 3. Iterating over the ResultSet and returning results
2. How to Enable Transactions in Spring and what are their benefits?
> There are two distinct ways to configure Transactions -- with annotations or by using Aspect-Oriented Programming (AOP) -- each with their advantages.
> 1. Provide a consistent programming model across different transaction APIs such as JTA, JDBC, Hibernate, JPA and JDO
> 2. Support declarative transaction management
> 3. Provide a simpler API for programmatic transaction management that some complex transaction APIs such as JTA
> 4. Integrate very well with Spring's various data access abstractions.
3. What is Spring DAO?
> Spring Data Object is Spring's support provided to work with data access technologies like JDBC, Hibernate and JPA in a consistent and easy way.

### Spring Aspect-Oriented Programming
1. What is AOP?
> Aspects enable the modularization of cross-cutting concerns sush as transaction management that span multiple types and objects by adding extra behavior to already existing code without modifying affected classes
2. What are Aspect, Advice, Pointcut, JoinPoint in AOP?
> 1. Aspect
>> A class that implements cross-cutting concerns, such as transaction management.
> 2. Advice
>> The methods that get executed when a specific JoinPoint with matching PointCut is reached in the application
> 3. PointCut
>> A set of regular expressions that are matched with JoinPoint to determine whether Advice needs to be executed or not
> 4. JoinPoint
>> A point during the execution of a program, such as the execution of a method or the handling of an exception

### Spring 5
1. What is Reactive Programming?
> Reactive programming is about non-blocking, event-driven applications that scale with a small number of threads, with back pressure being a key ingredient that aims to ensure producers don't overwhelm consumers
>> #### The befenits of reactive Programming
>> 1. Increased utilization of computing resources on multicore and mutli-CPU hardware
>> 2. Increased performance by reducing serialization
> Reactive programming is generally event-driven, in contrast to reactive systems, which are message-driven. So, using reactive programmming does not mean we are buildling a reactive system, which is an architectural style.
> However, reactive programming may be used as a means to implement reactive systems if we follow the Reactive manifesto, which is quite vital to understand.
> Based on this, reactive systems have four important characteristics:
> 1. Responsive
>> The system should respond in a timely manner.
> 2. Resilient
>> In case the system faces any failure, it should stay responsive.
> 3. Elastic 
>> Reactive systems can react to changes and stay responsive under varying workload
> 4. Message-driven
>> Reactive Systems need  to establish a boundary between components by relying on asynchronous message passing.
