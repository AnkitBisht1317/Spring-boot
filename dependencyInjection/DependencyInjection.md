# Dependency Injection
- It is a "Design Pattern".
- It main task is inject "one object into another object".
- It is used to achive "lossly coupling" in java.
- "ref" attribute ki help se ek object ko dusre me dalte hai
- We can achive depencency injection by 2 ways

## 1.Setter Injection
-  Dependencies are injected into a class through setter methods.
-  Setter method DI is more readable.
-  Setter method DI is more flexible
-  Setter method me applicationContext.xml file bean ke andar <property> tag ka use krte the or iske andar name or value attribute hote the

## 2.Constructor Injection
-  Dependencies are injected into a class through constructor.
-  Setter method DI is less readable.
-  Setter method DI is less flexible
- Constructor injection me applicationContext.xml file me bean ke andar <constructor> tag ke andar alue attribute hota hai wo bhi sequence se.
