# How Spring Security Authentication works

## Servlet Applications <a id="servlet-applications"></a>

> Spring Security integrates with the Servlet Container by using a standard Servlet . This means it works with any application that runs in a Servlet Container. More concretely, you do not need to use Spring in your Servlet-based application to take advantage of Spring Security. `Filter`

## Filters

![](.gitbook/assets/image%20%288%29.png)

![](.gitbook/assets/image%20%2816%29.png)

![](.gitbook/assets/image%20%2843%29.png)

{% embed url="https://atin.tistory.com/590" %}



## AuthenticationProvider

![](.gitbook/assets/image%20%2811%29.png)

![](.gitbook/assets/image%20%282%29.png)

![](.gitbook/assets/image%20%2814%29.png)

![](.gitbook/assets/image%20%2824%29.png)

![](.gitbook/assets/image%20%285%29.png)

## UserDetailService

![](.gitbook/assets/image.png)

![](.gitbook/assets/image%20%2812%29.png)

![](.gitbook/assets/image%20%2820%29.png)

## How it works

![](.gitbook/assets/image%20%2827%29.png)

![](.gitbook/assets/image%20%2823%29.png)

### SecurityContextHolder

> **SecurityContextHolder, SecurityContext and Authentication Objects**
>
> The most **fundamental** object is `SecurityContextHolder`. This is where we store details of the present security context of the application, which includes details of the principal currently using the application. By default the `SecurityContextHolder` uses a `ThreadLocal` to store these details, which means that the security context is always available to methods in the same thread of execution, even if the security context is not explicitly passed around as an argument to those methods. Using a `ThreadLocal` in this way is quite safe if care is taken to clear the thre

### Principal 가져오기

```java
Object principal = SecurityContextHolder.getContext().getAuthentication().getPrincipal();

if (principal instanceof UserDetails) {
    String username = ((UserDetails)principal).getUsername();
} else {
    String username = principal.toString();
}
```

## 참조

{% embed url="https://ncucu.me/103" %}

{% embed url="https://docs.spring.io/spring-security/site/docs/5.1.5.RELEASE/reference/htmlsingle/\#securitycontextholder-securitycontext-and-authentication-objects" %}

{% embed url="https://mangkyu.tistory.com/57" %}

[https://velog.io/@16616516/%EC%84%9C%EB%B8%94%EB%A6%BF-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88%EC%99%80-%EC%8A%A4%ED%94%84%EB%A7%81-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88](https://velog.io/@16616516/%EC%84%9C%EB%B8%94%EB%A6%BF-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88%EC%99%80-%EC%8A%A4%ED%94%84%EB%A7%81-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88)





