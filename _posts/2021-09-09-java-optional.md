---
title:  "Java Optional"
excerpt: ""

categories:
  - Java
tags:
  - [Java8, Optional]
toc: true
classes: wide
toc_sticky: false
 
date: 2021-09-09
last_modified_at: 2021-09-09


---



## Optional

**NullPointerException** 

- *null을 리턴하거나 null 체크를 하지 않아서*

- 메소드에서 작업 중 특별한 상황에서 값을 제대로 리턴할 수 없는 경우 선택할 수 있는 방법

  - 예외를 던진다. (비용이 비싸다, 스택트레이스를 찍어두니까.)
- null을 리턴한다. (비용 문제가 없지만 그 코드를 사용하는 클라이언트 코드가 주의해야 한다.)
  - (자바 8부터) Optional을 리턴한다. (클라이언트에 코드에게 명시적으로 빈 값일 수도 있다는 걸 알려주고, 빈 값인 경우에 대한 처리를 강제한다.)

- Java8부터는 함수형 언어의 접근 방식에서 영감을 받아서  `java.util.Optional<T>` 클래스를 도입하였음

  

#### Optional

- 값 한개가 들어있을 수도 있고 없을 수도 있는 컨테이너

- return 값으로만 쓰는 것을 권장

  - 메소드 매개변수 타입, 맵의 키 타입, 인스턴트 필드 타입으로 쓰는 것을 지양 

- 프리미티브 타입의 Optional이 존재

  - OptionalInt, OptionalLong...

- Collection, Map, Stream Array, Optional은 Optional로 감싸지 말 것

  - 의미가 없음. 어짜피 null check를 한번 더 해야하는 경우가 있음 

  ```java
  public void setProgress(Optional<Progress> progress) {
    // Optional을 null check 한 뒤 존재한다면 setProgress
  	if(progress.isPresent()) {
      progress.ifPresent(p -> this.progress = p);
  	}
  }
  ```

  



#### Optional API

- Optional 사용 예

  ```java
  Optional<Progress> getProgress() {
  	return Optional.ofNullable(progress);
  }
  ```

- Optional에 null 확인
  - isPresent()
  - isEmpty() (Java 11)
- Optional 값 가져오기
  - get()
- Optional에 값이 있는 경우 if절 사용
  - ifPresent(Progress)

- Optional에 값이 있으면 get 없으면 ~~ return
  - orElse(T)
- Optional에 값이 있으면 get 없으면 do ~~
  - orElseGet(Progress)
- Optional에 값이 있으면 get 없으면 throw
  - orElseThrow()
- Optional 값 filter
  - Optional filter(T)



### References

- https://www.inflearn.com/course/the-java-java8/ **더 자바, Java 8 - 백기선**