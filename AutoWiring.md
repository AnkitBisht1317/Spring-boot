# Auto Wiring
- Auto Wiring in the Spring Freamework is a feature that allows Spring to automatically inject dependencies into bean ( automatically inject one object into another) without need to explicitly specify them in the XML or JAVA configuration.
- There are 2 method to achive auto wiring in spring boot.

### 1. Annotation - Based Autowiring (@Autowired)
- @Autowired is an annotation provided by Spring that allows automatic dependency injection.
- It tells Spring to automatically resolve and inject the collaborating bean into the target bean.

``` java
@Component
public class Student {

    @Autowired
    private Address address;

    public void display() {
        System.out.println("Address: " + address);
    }
}
```
### 2. XML Based Autowirig
- In XML-based autowiring, we define bean dependencies inside the XML configuration file using the autowire attribute.
- Spring automatically wires beans by type, name, or constructor, depending on the specified mode.
- byName	= Injects dependency by matching the property name with bean id.
```java
<bean id="address" class="in.aw.bean.Address" />
<bean id="student" class="in.aw.bean.Student" autowire="byName" />
```
- byType	= Injects dependency by matching the data type of property and bean.
```java
<bean id="address1" class="in.aw.bean.Address" />
<bean id="student" class="in.aw.bean.Student" autowire="byType" />
```
- constructor = 	Injects using the constructor if parameter types match the bean types.
```java
<bean id="address" class="in.aw.bean.Address" />
<bean id="student" class="in.aw.bean.Student" autowire="constructor" />

student.java
public Student(Address address) {
    this.address = address;
}

```
