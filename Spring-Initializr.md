# Spring - Initializr
- Spring initializr is a web-based tool provided by spring team that allows developers to quickly generate a spring boot project structure with pre selected configurations.
- It give ready to use zip file with all required dependencies, directory structure and initial setup files.
- It support both maven and gradle project
- It automatically genrate pom.xml, build.gradle

## Key Input Fields in Spring Initializr
- Choose between Maven or Gradle.
- Maven is preferred for most enterprise projects.
- Gradle is known for faster builds and flexibility.
- Choose Java, Kotlin, or Groovy.
- Java is most commonly used.
- You can select the stable or snapshot version.
- Always choose the latest stable version for production.
- Group = Usually your company/organization domain in reverse (e.g., com.example)
- Artifact = 	The name of the application (used for JAR/WAR file)
- Name = Name of the application (often same as Artifact)
- Description = A short explanation of the application
- Package name = Full package name for generated classes (auto-generated from Group + Artifact)
