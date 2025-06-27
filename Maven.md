# MAVEN 
- Maven is a bulid automation tool primarily used for java projects. It addresses two main aspects of building software: Dependency management and project build life cycle managment(validate, complie, test, package, install, deploy).
- It simplifies the bulid process by managing dependencies, compiling source code, pacckaging it into a deliverable(Such as JAR file),and deploying it to a repository.
- Maven is based on the concept of the project object model(POM) which is a central piece of information that manages a project's bulid, reporting, and documentation.

## MAVEN Bulid Life Cycle
- the maven bulid lifecycle is a sequence that define the order in which tasks are executed during the bulid process pf a maven project.
 ##### i). Validate
 - Validates the project is correct and all necessary information is available.

 ##### ii). Compile
  - Compiles the source code of the project.

 ##### iii). Test
 - Runs the tests using a sutable unit testing framework(like Junit).

 ##### iv). Package
 - Packages the compiled code into a distributable format, such as a JAR file Or WAR file.

 ##### v). Verify
 - Runs any check to verify the packages is vaild and meets quality criteria.

 ##### vi). Install
 - Installs the packages into the local repository, for use as a dependency in other project locally.

 ##### vii). Deploy
 - Copies the final packages to the remote repository for sharing with other developers and projects.
