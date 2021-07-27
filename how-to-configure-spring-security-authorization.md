# Spring Security Authorization을 설정하는 방법

![](.gitbook/assets/image%20%2818%29.png)

![](.gitbook/assets/image%20%286%29.png)

### SecurityConfiguration.java 추가

```java
@Override
protected void configure(HttpSecurity http) throws Exception {
    http.authorizeRequests()
        .antMatchers("/admin").hasRole("ADMIN")
        .antMatchers("/user").hasAnyRole("USER", "ADMIN")
        .antMatchers("/").permitAll()
        .and().formLogin();
}
    
```

### HomeResource.java 추가

```java
@RestController     
public class HomeResource {
    
    @GetMapping("/")
    public String home() {
        return ("<h1>Welcome</h1>");
    }
    @GetMapping("/user")
    public String user() {
        return ("<h1>Welcome User</h1>");
    }
    
    @GetMapping("/admin")
    public String admin() {
        return ("<h1>Welcome Admin</h1>");
    }
}
```



