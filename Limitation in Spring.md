

# Spring Framework me Tomcat ki jarurat kyun hoti hai?
- 1. Spring Framework ek standalone framework nahi hai
- Spring Framework khud se web server provide nahi karta.
- Ye sirf backend logic handle karta hai (like dependency injection, data access, etc.).

- 2. Web Project ko run karne ke liye Servlet Container chahiye
- Spring MVC web applications me controller, dispatcher servlet, etc. ka use hota hai.

- In sabko run karne ke liye ek servlet container chahiye hota hai — jaise:
- Apache Tomcat,Jetty,GlassFish

- 3. Tomcat WAR file ko deploy karta hai
- Spring Framework projects me hum project ko WAR (Web Archive) ke form me build karte hain.
- Fir is WAR file ko Tomcat server me deploy karte hain.
- Tabhi jaake aapka application browser me open hota hai.

- 4. Spring Boot me Tomcat embedded hota hai
- Agar aap Spring Boot use karo to Tomcat embedded hota hai.
- Aapko alag se WAR banake Tomcat me deploy karne ki jarurat nahi padti.
-Bas main() method se SpringApplication.run() likho, and project browser me chalega.

