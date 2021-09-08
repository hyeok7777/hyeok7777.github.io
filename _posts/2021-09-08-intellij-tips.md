---
title:  "IntelliJ 단축키 활용"
excerpt: ""

categories:
  - IntelliJ
tags:
  - [IntelliJ]
toc: true
classes: wide
toc_sticky: false
 
date: 2021-09-08
last_modified_at: 2021-09-08

---





# IntelliJ 단축키 활용 

M : 맥 / W : 윈도우, 리눅스

### Code Edit

- #### 메인메소드 생성 및 실행

  1. **디렉토리, 패키지, 클래스 등 생성 목록 보기** 

     - M : command + n
     - W : Alt + Insert

  2. **코드 템플릿**

     - 메인 메소드 : psvm
     - System.out.println() : sout

  3. **실행환경 실행**

     1. 현재 포커스
        - M : control + shift + R
        - W : Shift + Ctrl + F10

     2. 이전 실행
        - M : control + R
        - W : shift + F10

- #### 라인 수정하기 

  1. **라인 복제하기**

     - M : command + D
     - W : Ctrl + D

  2. **라인 삭제하기**

     - M : command + Backspace
     - W : Ctrl + Y

  3. **문자열 라인 합치기**

     - M, W : control + shift + J

  4. **라인 단위로 옮기기**

     1. 구문 이동 

        - M : shift + command + ⬆️⬇️
        - W : shift + Ctrl + ⬆️⬇️

     2. 라인 이동

        - M : shift + option + ⬆️⬇️

        - W : shift + Alt + ⬆️⬇️

  5. **Element 단위로 옮기기**

     - M : option + shift command + ⬅️➡️
     - W : Alt + Ctrl + Shift + ⬅️➡️

- #### 코드 즉시보기

  1. **인자값 즉시 보기**
     - M : command + P
     - W : Ctrl + P
  2. **코드 구현부 즉시 보기**
     - M : option + Space
     - W : Shift + Ctrl + I
  3. **Doc 즉시 보기**
     - M : F1
     - W : Ctrl + Q

### 포커스

- #### 포커스 에디터 

  1. **단어별 이동**

     - M : option + ⬅️➡️
     - W : Ctrl + ⬅️➡️

  2. **단어별 선택**

     - M : shift + option + ⬅️➡️
     - W : Shift + Ctrl + ⬅️➡️

  3. **라인 첫/끝 이동**

     - M : fn + ⬅️➡️

     - W : Home, End

  4. **라인 전체 선택**

     - M : shift + fn + ⬅️➡️

     - W : Shift + Home, End

  5. **Page Up / Down**

     - M : fn + ⬆️⬇️

     - W : Page Up / Down

- #### 포커스 특수키

  1. **포커스 범위 한 단계씩 늘리기**
     - M : option + ⬆️⬇️
     - W : Ctrl + W (위) / Shift + Ctrl + W (아래)
  2. **포커스 앞으로, 뒤로 가기** (이전의 포커스가 있던 위치로 이동, 되돌리기)
     - M : command + [,  ]
     - W : Ctrl + Alt + ⬅️➡️
  3. **멀티 포커스**
     - M : option 키 두번 누른채로 ⬆️⬇️⬅️➡️
     - W : Ctrl 키  두번 누른채로 ⬆️⬇️⬅️➡️
  4. **오류 라인으로 자동 포커스**
     - M, W : F2

## 검색

- #### 검색 텍스트

  1. **현재 파일에서 검색**
     - M : command + F
     - W : Ctrl + F
  2. **현재 파일에서 교체**
     - M : command + R
     - W : Ctrl + R
  3. **전체에서 검색**
     - M : command + shift + F
     - W : Ctrl + Shift + F
  4. **전체에서 교체**
     - M : command + shift +  R
     - W : Ctrl + Shift + R

- #### 검색 기타

  1. **파일 검색**

     - M : command + shift +  O

     - W : Ctrl + Shift + N

  2. **메소드 검색** 

     - M : command + option +  O

     - W : Ctrl + Shift + Alt + N

  3. **Action 검색** 

     - M : command + shift +  A

     - W : Ctrl + Shift + A

  4. **최근 열었던 파일 목록 보기**

     - M : command + E
     - W : Ctrl + E

  5. **최근 수정한 파일 목록 보기**

     - M : command + shift + E
     - W : Ctrl + Shift + E

### 자동완성

- #### 자동완성

  1. **스마트 자동완성**

     - M : control + shift + Space
     - W : Ctrl + Shift + Space

  2. **스태틱 메소드 자동 완성**

     - M : control + Space * 2
     - W : Ctrl + Space * 2

  3. **Getter / Setter / 생성자 자동완성**

     - M : command + n
     - W : Alt + Insert

  4. **Override 메소드 자동완성**

     - M : command + I

     - W : Ctrl + I

     

     

     

     

[출처]: https://www.inflearn.com/course/intellij-guide/







