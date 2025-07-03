# Spring-Boot-Architecture
- Spring Boot is a module of the Spring Framework. It is used to create stand-alone, production-grade Spring Based Applications with minimum efforts. It is developed on top of the core Spring Framework.
- Spring Boot follows a layered architecture in which each layer communicates with the layer directly below or above (hierarchical structure) it.

![Image](https://github.com/user-attachments/assets/4c2b648f-1728-4347-b25d-5bda7b99e0a8)

## Core Layers of Spring Boot Architecture
- Spring Boot follows a layered architecture, mainly divided into the following layers:

### Presentation Layer 
- This is the topmost layer, responsible for handling HTTP request and response.
- It sent this request to controller and then controller give this request to server if required.

### Service Layer
- The service layer contain bussiness logic it act as a bridge between the controller and daatabase.
- the service layer make sure that the app follow all the business rule and steps properly.

### Data Access Layer
- This layer handle all operations related to the database such as saving, retriving, updating and deleting data, Spring boot use JDBC templates to interact with database

### Model Layer
- The model layer consist of POJO class annotated with JPA anootation

## Example
- The client makes the HTTP requests (PUT or GET).
- The request goes to the controller, and the controller maps that request and handles it. After that, it calls the service logic if required.
- In the service layer, all the business logic performs. It performs the logic on the data that is mapped to JPA with model classes.
- A JSP page is returned to the user if no error occurred.
