---
title:  "Legacy Spring Framework 전환"
excerpt: ""

categories:
  - Spring 
tags:
  - [Spring]
toc: true
classes: wide
toc_sticky: false
 
date: 2023-07-23
last_modified_at: 2023-07-23





---

# Legacy Spring Framework 전환 시 확인해야 할 것들

1. @PostConstruct

   - ```java
     @Controller
     public class UserConfigController { 
     	private UserConfigService userConfigService; 
     }
     
     @PostConstruct
     @RequestMapping(value = "/user/mapping/reset")
     public void init {
       userConfigService.init();
     }
     ```

     위와 같은 예시 코드가 있다고 할 때 아래와 같은 코드를 작성하면 대부분의 경우에 동일한 동작을 보장할 수 있다. 

     ```java
     @RestController
     @RequestMapping("/user/mapping")
     public class UserConfigController {
         private final UserConfigService userConfigService;
     
         public UserConfigController(UserConfigService userConfigService) {
             this.userConfigService = userConfigService;
         }
     
         @PostMapping("/reset")
         public void init() {
             userConfigService.init();
         }
     }
     
     ```

     - Controller -> RestController 
       - RestController는 Controller와 ResponseBody를 합친 것으로, 모든 핸들러 메서드의 응답이 자동으로 HTTP 응답으로 변환된다.
       - RequestMapping을 통해 공통경로 사용 
       - PostConstruct를 삭제하여 생성자 주입을 통해 UserConfigService를 주입하도록 변경
         - 의존성 주입이 명시적으로 이루어짐 
       - RequestMapping -> PostMapping
     - PostConstruct는 빈이 초기화된 후 호출되는 메서드를 지정하는데 사용된다. Spring Boot에서는 생성자 주입을 통해 의존성 주입을 진행하는 것이 일반적이므로, 초기화 로직은 생성자에서 호출하거나 별도 초기화 메서드를 통해 처리하는 것이 좋다.
     - PostConstruct는 Spring의 Core와 Web 모듈에서 제공되는 어노테이션이므로 사실 그냥 사용해도 된다. 패키지만 바꿔주면 된다.
       - JAVA EE 8 이전 버전에서는 jakarta.annotation.PostConstruct
       - Jarkarta EE 8 이후 버전에서는 javax.annotation.PostConstruct
       - Java 17 버전 이후에서는 Java SE 모듈에 javax.annotation 패키지가 포함되지 않으므로 jakarta.annotation.PostConstruct로 그냥 쓰면 된다.

