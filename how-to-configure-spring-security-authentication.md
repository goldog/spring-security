# How to configure Spring Security Authentication

## AuthenticationManager

![](.gitbook/assets/image%20%2815%29.png)

## AuthenticationManagerBuilder

![](.gitbook/assets/image%20%2821%29.png)

![](.gitbook/assets/image%20%2813%29.png)

![](.gitbook/assets/image%20%281%29.png)

### SecurityConfiguration.java 추가

```java
@EnableWebSecurity
public class SecurityConfiguration extends WebSecurityConfigurerAdapter{
    @Override
    protected void configure(AuthenticationManagerBuilder auth) throws Exception {
        auth.inMemoryAuthentication()
            .withUser("goldog")
            .password("abcd")
            .roles("USER");
    }

    @Bean
    public PasswordEncoder getPasswordEncoder() {
        return NoOpPasswordEncoder.getInstance();
    }
    
}

```



