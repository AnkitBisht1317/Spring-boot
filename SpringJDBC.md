# Spring JDBC 
- We can connect spring application with database using JDBC and for this spring framework provides one module "Spring JDBC Modules"

![Image](https://github.com/user-attachments/assets/1b064936-b969-4ec1-bffa-bba936a363db)

### How spring JDBC Works
- spring JDBC works by injecting a DataSource bean into the data access object layer
- The JdbcTemplate is configured using this DataSource, and then it is used to perform database operation.

###  Key Components of Spring JDBC
- The central class in Spring JDBC is JdbcTemplate. It handles the creation and release of database resources such as Connection, PreparedStatement, and ResultSet.
- This class provides several methods to perform CRUD (Create, Read, Update, Delete) operations and helps in executing SQL queries, stored procedures, and updates.
- Spring’s JdbcTemplate provides various useful methods such as queryForObject() for fetching a single value, query() for retrieving multiple rows, update() for insert, update, and delete operations, and batchUpdate() for executing a batch of SQL statements efficiently.



#### student.java
```java
package com.example.model;

public class Student {
    private int id;
    private String name;
    private int age;

    // Getters & Setters
    public int getId() { return id; }
    public void setId(int id) { this.id = id; }
    
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}
```

#### studentDao.java
```java
package com.example.dao;

import com.example.model.Student;
import org.springframework.jdbc.core.JdbcTemplate;
import org.springframework.jdbc.core.RowMapper;

import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.List;

public class StudentDao {
    private JdbcTemplate jdbcTemplate;

    public void setJdbcTemplate(JdbcTemplate jdbcTemplate) {
        this.jdbcTemplate = jdbcTemplate;
    }

    public int save(Student s) {
        String sql = "INSERT INTO student(id, name, age) VALUES(?, ?, ?)";
        return jdbcTemplate.update(sql, s.getId(), s.getName(), s.getAge());
    }

    public int update(Student s) {
        String sql = "UPDATE student SET name=?, age=? WHERE id=?";
        return jdbcTemplate.update(sql, s.getName(), s.getAge(), s.getId());
    }

    public int delete(int id) {
        String sql = "DELETE FROM student WHERE id=?";
        return jdbcTemplate.update(sql, id);
    }

    public List<Student> getAll() {
        return jdbcTemplate.query("SELECT * FROM student", new RowMapper<Student>() {
            public Student mapRow(ResultSet rs, int rowNum) throws SQLException {
                Student s = new Student();
                s.setId(rs.getInt(1));
                s.setName(rs.getString(2));
                s.setAge(rs.getInt(3));
                return s;
            }
        });
    }
}
```
#### AppConfig.java
```java
package com.example.config;

import com.example.dao.StudentDao;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.jdbc.core.JdbcTemplate;

import javax.sql.DataSource;
import org.springframework.jdbc.datasource.DriverManagerDataSource;

@Configuration
public class AppConfig {
    @Bean
    public DataSource dataSource() {
        DriverManagerDataSource ds = new DriverManagerDataSource();
        ds.setDriverClassName("org.h2.Driver");
        ds.setUrl("jdbc:h2:mem:testdb;DB_CLOSE_DELAY=-1");
        ds.setUsername("sa");
        ds.setPassword("");
        return ds;
    }

    @Bean
    public JdbcTemplate jdbcTemplate() {
        return new JdbcTemplate(dataSource());
    }

    @Bean
    public StudentDao studentDao() {
        StudentDao dao = new StudentDao();
        dao.setJdbcTemplate(jdbcTemplate());
        return dao;
    }
}
```

Main.java
```java
package com.example;

import com.example.config.AppConfig;
import com.example.dao.StudentDao;
import com.example.model.Student;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

import javax.sql.DataSource;
import java.sql.Connection;
import java.sql.Statement;

public class MainApp {
    public static void main(String[] args) throws Exception {
        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);
        StudentDao dao = context.getBean(StudentDao.class);

        // Create table manually since H2 is in-memory
        DataSource ds = context.getBean(DataSource.class);
        try (Connection conn = ds.getConnection(); Statement stmt = conn.createStatement()) {
            stmt.execute("CREATE TABLE student (id INT PRIMARY KEY, name VARCHAR(100), age INT)");
        }

        // Insert
        Student s1 = new Student(); s1.setId(1); s1.setName("Ankit"); s1.setAge(23);
        dao.save(s1);

        // Update
        s1.setName("Ankit Sir"); s1.setAge(24);
        dao.update(s1);

        // Read
        System.out.println("All students:");
        dao.getAll().forEach(st -> System.out.println(st.getId() + " " + st.getName() + " " + st.getAge()));

        // Delete
        dao.delete(1);

        context.close();
    }
}
```
