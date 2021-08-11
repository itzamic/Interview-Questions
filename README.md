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
> BeanFactory is an interface representing a container that provides and manages bean instances. The default implementation instantiates beans lazily when getBean() is called. 
> In contrast, ApplicationContext is an interface representing a container holding information, metadata and beans in the application. It also extends the BeanFactory interface, but the default implementation instantites beans eagerly when the application starts. However, this behavior can be overridern for individula beans
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
7. 
