# Dependency Injection
- It is a "Design Pattern".
- It main task is inject "one object into another object".
- It is used to achive "lossly coupling" in java.
- We can achive depencency injection by 2 ways

## 1.Setter Injection
-  Dependencies are provided through public setter methods. This allows for optional dependencies and can be useful when a dependency might change during the object's lifetime, although it can lead to objects being in an incomplete state if not all setters are called.

## 2.Constructor Injection
- Dependencies are provided as arguments to the class's constructor. This is generally the preferred method as it ensures that the object is in a valid state immediately after creation and makes dependencies explicit.
Java

