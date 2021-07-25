# Adding Spring Security to new Spring Boot project

## spring-boot-starter-security

### HomeResource.java 추가

```java
@RestController     
public class HomeResource {
    
    @GetMapping("/")
    public String home() {
        return ("<h1>Welcome</h1>");
    }
}
```

## Filters



## Spring Security default behavior

* Adds mandatory authentication for URLs
* Adds login form
* Handles login error
* Creates a user and sets a default password

```java
spring.security.user.name=goldog
spring.security.user.password=0514
```

