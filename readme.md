# What is spring? 

Application comprises of many components, each responsible for their own operation
and coordinating with other components to get the job done 

Spring offers a container referred to as spring application context 
that creates a manages application componoent

The beans or components are wired together inside the application context. The act of wiring the beans together is called dependency injection. 
Rather than have the components create and manage the life cycle of other beans that they depend on, they depend on the application context which in this case is the spring application context to maintain it. 

Previou way to guide the spirng application context to wire beans together was with the use of XML files. Nowadays, java based configuration are more common 

@Configuration annotation indicates to spring that this is a configuration class that will provide beans to the Spring application context. 
The configurations method are annotated with @Beans indicating that the object they return should be added in the application context 

Explicit confiuration with either XML or java is necessary only if Spring is unable to automatically configure the components 

Autowiring and component scanning, spring can automatically discover components from the application's classpath and create them as beans in the spring application context. with autowiring, spring injects the components with other beans that they depend on. 

A configuration class annotated using @configuration  defines beans for the spring application context. These classes are used to configure and instantiate the application's components and resources. 

The @springbootapplication is a composite annotation that combines the following three annotations
1. @SpringBootConfiguration
2. @EnableAutoConfiguration
3. @ComponentScan

The run method in the main class initiated the bootstrapping of the application, creating the spring application context. 

**Failed to configure a DataSource: 'url' attribute is not specified and no embedded datasource could be configured.**
This error happened in my case because I have added JPA as a dependency and since spring boot has a auto configuration mode which tries to configure the JPA class and since I have not configured it correctly I get the error. The fix is to either remove JPA as a dependency for now or configure the JPA in application.properties

Although @SpringBootTest is tasked with
loading the Spring application context for the test, it won’t have anything to do if
there aren’t any test methods.

At the center of the MVC is the concept of controller, a class that handles request and responds accordingly. they are also reponsible for populating model data and passing request on to a view to produce HTML that's been returned to the browser. 

The primary purpose of the @Controller in any controller package is to identify the class as a component for component scanning, the spring's component scanning automatically discovers it and creates an instance  of the class that has the @Controller annotation as a bean in the spring application context.

### What does @ModelAttribute and @SessionAttribute do in Spring
The **@ModelAttribute** annotation is used to bind a method parameter or method return value to a named model and then expose that model to the view.
Any method that is annotated with the @ModelAttribute is called before the @RequestMapping to ensure that the model is populated with necessary data 

**@ModelAttribute** can be used as a method annotation or as request parameter. When they are used as method annotation then they are executed before the request mapping

**@ModelAttribute** can also be used as request parameter, in this case the request body sent by the user to the request method is populated with the value.


### What is the Converter class in java and how to use it in Spring