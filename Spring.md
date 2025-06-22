#  Spring Framework 
- It is open source java framework.
- Spring framework is a toolkit for java that helps developers bulid applications more esaily and efficiently.
- When you bulid a java app, you usually need to create and connect object, work with database, manage user login and handle web request and responses.

### Advantage 
- Spring automatically creates and connects object for you.
- Spring encourages writing modular code.
- Things like logging, security and validation are handled automatically.
- Spring bulid websites and REST APIs easily.
- With Spring Security, you can easily add login, logout, password protection, etc.

## JAVABEAN CLASS 
- Java bean is a java class that is developed by following some standard. java bean does not contain any logic. it act helper class t carry data from one class to another or from one project to another.
- Class must be taken as public
- It is recommended to implement java.io.Serializable to send data over the network.
- All bean properties ( member variable) must be taken as private and non static.
- Every bean property should have one public setter method and one public getter method.
- A public no-argument constructor.

## POJO class(Plain Old Java Object) 
- A simple java class with filed and getter/setter, used for data representation without framework dependencies.
- Use in Spring
    - In Spring, POJO classes are often used as:
    - Model objects for data transfer
    - Request/Response objects in REST APIs
    - Entities in JPA/Hibernate
