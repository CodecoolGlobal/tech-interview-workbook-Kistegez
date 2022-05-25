# Enterprise module (Java branch)

### Java Enterprise and Spring

#### What are the possible uses of reflection?

    Java Reflection can be used to map properties in JSON files to getter / setter methods in Java objects, like Jackson, GSON, Boon etc. does.
    Or, Reflection can be used to map the column names of a JDBC ResultSet to getter / setter methods in a Java object.

#### What is Spring?

    The Spring Framework provides a comprehensive programming and configuration model for modern Java-based enterprise applications - on any kind of deployment platform.
    A key element of Spring is infrastructural support at the application level: Spring focuses on the "plumbing" of enterprise applications so that teams can focus on application-level business logic,
    without unnecessary ties to specific deployment environments.

#### What is Spring Boot?

    Spring Boot makes it easy to create stand-alone, production-grade Spring based Applications that you can "just run".
    We take an opinionated view of the Spring platform and third-party libraries so you can get started with minimum fuss.
    Most Spring Boot applications need minimal Spring configuration.

#### What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.

    Java SE:
    When most people think of the Java programming language, they think of the Java SE API. Java SE's API provides the core functionality of the Java programming language.
    It defines everything from the basic types and objects of the Java programming language to high-level classes that are used for networking, security, database access, graphical user interface (GUI) development, and XML parsing.
    In addition to the core API, the Java SE platform consists of a virtual machine, development tools, deployment technologies, and other class libraries and toolkits commonly used in Java technology applications.
    
    Java EE:
    The Java EE platform is built on top of the Java SE platform. The Java EE platform provides an API and runtime environment for developing and running large-scale, multi-tiered, scalable, reliable, and secure network applications.

#### What are the advantages of the Spring Framework? Focus on the Core part.

    Dependency Injection (DI)
    Support for Aspect-Oriented Programming
    Data Access Framework
    Transaction Management Framework
    Spring MVC Framework
    Spring Web Service
    Spring Test Frameworks
    Core Container
    Data Access/Integration

#### What is a servlet? What is the purpose of DispatcherServlet in Spring?

    Servlet technology is used to create a web application (resides at server side and generates a dynamic web page).
    Servlet technology is robust and scalable because of java language. Before Servlet, CGI (Common Gateway Interface) scripting language was common as a server-side programming language.
    However, there were many disadvantages to this technology.
    There are many interfaces and classes in the Servlet API such as Servlet, GenericServlet, HttpServlet, ServletRequest, ServletResponse, etc.
    
    Servlet can be described in many ways, depending on the context.
    Servlet is a technology which is used to create a web application.
    Servlet is an API that provides many interfaces and classes including documentation.
    Servlet is an interface that must be implemented for creating any Servlet.
    Servlet is a class that extends the capabilities of the servers and responds to the incoming requests. It can respond to any requests.
    Servlet is a web component that is deployed on the server to create a dynamic web page.

#### When do you use RestControllers, when just simple Controllers?

    RestController when creating a RESTful web service because it combines Controller and ResponseBody annotations

#### What is Spring Application Context?

    One of the main features of the Spring framework is the IoC (Inversion of Control) container. The Spring IoC container is responsible for managing the objects of an application. It uses dependency injection to achieve inversion of control.
    The interfaces BeanFactory and ApplicationContext represent the Spring IoC container. Here, BeanFactory is the root interface for accessing the Spring container. It provides basic functionalities for managing beans.
    On the other hand, the ApplicationContext is a sub-interface of the BeanFactory. Therefore, it offers all the functionalities of BeanFactory.
    Furthermore, it provides more enterprise-specific functionalities. The important features of ApplicationContext are resolving messages, supporting internationalization, publishing events, and application-layer specific contexts.
    This is why we use it as the default Spring container.

#### What are the main ways to define a bean in the Application Context?

    Bean - an object that the Spring container instantiates, assembles, and manages.
    with @Bean annotation, Spring based annotation like @Controller, @Service, @Autowired, @Repository
    
    XML-based configuration
    
    ```xml
    <bean id="accountService" class="com.baeldung.applicationcontext.AccountService">
        <constructor-arg name="accountRepository" ref="accountRepository" />
      </bean>
    ```

#### Difference between .jar and .war files.

    Main difference is their purpose and the way they function. JAR files allow us to package multiple files in order to use it as a library, plugin, or any kind of application.
    On the other hand, WAR files are used only for web applications.

    The structure of the archives is also different. We can create a JAR with any desired structure. In contrast, WAR has a predefined structure with WEB-INF and META-INF directories.
    
    Finally, we can run a JAR from the command line if we build it as an executable JAR without using additional software. Or, we can use it as a library. In contrast, we need a server to execute a WAR.

#### What are the major differences between Maven, Ant and Gradle?

    ANT - (Another Neat Tool) is a library for automating build processes but everything needs to write manually, because of this it is very flexible

    Maven - relies on conventions and provides predefined commands as a result the project structure predefined maven also has dependency management, also supports a wide range of plugins
    
    Gradle - combines the concepts of ANT and Maven, oppose the other two gradle doesn't use xml for configuration instead DSL (Domain-specific language) based on either Groovy or Kotlin.
    Shorter config files with less clatter but can be hard to understand for beginners

#### What is Maven used for?
#### What does a pom.xml file contains in Maven?

    build processes, project dependencies

### Object Relational Mapping, JPA

#### What is an ORM? What are the benefits, when to use?

    Object-relational mapping (ORM) is a technique that creates a layer between the language and the database, helping programmers work with data without the OOP paradigm.

    Benefits - reduced development time since there is no need to write whole SQL queries
    code reuse
    reduce testing since the code generated by the ORM is well tested

#### What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.
#### What is Hibernate? What are the advantages, limitations?
#### Name 3 different annotations used in JPA, what can they do for you?
#### What is object-relational impedance mismatch?
#### What is a JpaRepository? What are the 2 main methods to define queries in them?
#### Why is the Set preferred over List when we want to store OneToMany relations?
#### What kind of inheritance strategies are available? Which annotations are used to solve this?
