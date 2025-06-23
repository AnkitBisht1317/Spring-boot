# Spring Container 
- The core part of the spring framework is the container.
- It is mainly responsible for creating and managing the lifecycle of java object, which are called Beans.
- In a regular java application we manually create object and connect them. but in spring this responsibility is given ti the IoC container - it creates object, connect them together, and manages their entire lifecycle.

### Type 
- Spring provide two main type of container

 #### 1. BeanFactory 
 - BeanFactory is the most basic type of container. it only creates beans when you request them.
 - it is old Container and we don't use that nowdays

#### 2. ApplicationContext 
- ApplicationContext is a more advanced container that build upon BeanFactory and provide many extra feature.
- It is morder Container and we use that container.

### Working of IoC Container
- The container reads configuration metadata (XML, Java annotations, or Java-based configuration) to understand how beans should be creates and wired together.
- It uses Dependency Injection (DI) to inject dependencies into beans at runtime.
- The container manages the entire lifecycle of beans, from instantiation to destruction.

![Image](https://github.com/user-attachments/assets/9adb7ad7-21a8-4c8c-840a-f37ccdb5cbc4)
