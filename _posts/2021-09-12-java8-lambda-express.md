---
title:  "Java Lambda expression"
excerpt: ""

categories:
  - Java
tags:
  - [Java8, Lambda]
toc: true
classes: wide
toc_sticky: false
 
date: 2021-09-12
last_modified_at: 2021-09-12



---





## 람다식(Lambda expression)

- 자바가 1996년 등장한 이후로 두번의 큰 변화가 있었는데, 한번은 JDK1.5에서 generics가 추가된 것과 또 다른 한번은 JDK1.8에 추가 된 lamda expression이다.
- 람다식의 도입으로 자바는 개체지향언어인 동시에 함수형 언어가 되었다.



#### 람다식이란?

- 메서드를 하나의 '식(expression)'으로 표현한 것이다.
- 메서드를 람다식으로 표현하면 메서드의 이름과 반환값이 없어지므로, '익명 함수'라고도 한다.



#### 람다식 작성하기

- 메서드에서 이름과 반환타입을 제거하고 매개변수 선언부와 몸통{} 사이에 '->'를 추가한다.

  ```java
  반환타입 메서드이름 (매개변수 선언) { 
  	문장들
  }
  
  ⬇️
  
  (매개변수 선언) -> {
    문장들
  }
  ```

- 예)

  ```java
  int max(int a, int b) {
  	return a > b ? a : b;
  }
  
  (int a, int b) -> {
    return a > b ? a : b;
  }
  ```

  ```java
  (int a, int b) -> { return a > b ? a : b; }
  
  (int a, int b) -> a > b ? a : b
    
  (a, b) -> a > b ? a : b
  ```

  ```java
  int roll() { 
  	return (int)(Math.random()*6);
  }
  
  () -> (int)(Math.random()*6)
  
  ```

  - 반환값이 있는 메서드의 경우, return문 대신 '식(expression)'으로 대신 가능
  - 람다식에 선언된 매개변수의 타입은 추론이 가능한 경우는 생략 가능



#### 함수형 인터페이스(Functional Interface)

- 위에서는 람다식이 메서드와 동등한 거서럼 설명했지만, 사실 람다식은 익명 클래스의 객체와 동등하다.

  ```java
  // max()라는 메서드가 정의 된 MyFunction Interface
  interface MyFunction {
    public abstract int max(int a, int b);
  }
  
  
  // MyFunction Interface를 구현한 익명 클래스의 객체
  MyFunction f = new MyFuncion() { 
  											public int max(int a, int b) {
                          return a > b ? a : b;
                        }
  }
  
  // 익명 객체의 메서드를 호출
  int bit = f.max(5, 3);
  
  // 익명 클래스의 객체를 람다식으로 대체
  Myfunction f = (int a, int b) -> a > b ? a : b;
  ```

  - MyFuncion 인터페이스를 구현 한 익명 객체를 람다식으로 대체할 수 있는 이유는, 람다식도 실제로는 익명 객체이고 해당 인터페이스를 구현한 익명 객체의 메서드 max()와 람다식의 매개변수 타입과 개수, 반환값이 일치하기 때문

- 람다식을 다루기 위한 인터페이스를 '함수형 인터페이스'라고 한다.

  ```java
  @FunctionalInterface
  interface MyFunction {
  		// 함수형 인터페이스 MyFunction 정의
  		public abstract int max(int a, int b);
  }
  ```

  > @FunctionalInterface를 붙이면 컴파일러가 함수형 인터페이스를 올바르게 정의하였는지 확인해준다.

- 람다식을 이용한 인터페이스의 메서드 예시

  ```java
  List<String list = Arrays.asList("abc", "aaa", "bbb", "ddd");
  
  // 메서드 구현
  Collections.sort(list, new Comparator<String>() {
    public int compare(String s1, String s2) {
      return s2.compareTo(s1);
    }
  });
  
  // 람다식 메서드 구현
  Collections.sort(list, (s1, s2) -> s2.compareTo(s1));
  ```

  

