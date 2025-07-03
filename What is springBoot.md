# Spring Boot
- Spring Boot is open source java based framework.
- Spring Boot based on Spring framework.
- Spring Boot providing auto-configuration, starter dependencies and embedded servers(like Tomcat), so application can run with just a single class and minimal setup.
- It is used to create a standalone spring-based application.

![Image](https://github.com/user-attachments/assets/e9c868c6-d038-413d-80a9-6980c03ff89c)

### Features of Spring Boot
- Spring Boot offers a rich set of features that make it ideal for modern java development.

##### Auto-Configuration 
- Automatically configures your application based on the libraries present on the classpath.(Auto-Configuration" means Spring Boot samajh jata hai ki aapko kis cheez ki need hai based on dependencies, aur uske liye automatic setup kar deta hai — aapko kuch nahi karna padta.)
- (Aapko manually XML ya Java configuration likhne ki zarurat nahi padti.)

##### Starter Dependencies  
- A collection of commonly used libraries bundled together to reduce dependency management.(Spring Boot ne commonly used tools ka ek combo bana diya hai, taaki aapko baar-baar manually dependencies manage na karni padhein.)

                            <dependency>
                                     <groupId>org.springframework.boot</groupId>
                                       <artifactId>spring-boot-starter-web</artifactId>
                            </dependency>

#### Embedded Web Server
- Built-in servers like Tomcat, jetty remove the need for WAR deployment.
- (Embedded Web Server ka matlab hai ki Spring Boot application ke andar hi ek web server (jaise Tomcat) already built-in hota hai. Aapko .war file nhi bnani padti or Tomcat/Jetty ko manually install karke usme .war file deploy nhi karni padti.)

#### No XML Configuration Required 
- All Configuration are handled via java-based anootations and application.properties.



