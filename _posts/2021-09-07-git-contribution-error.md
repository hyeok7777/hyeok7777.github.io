---
title:  "Github Contribution이 반영되지 않을 때"
excerpt: ""

categories:
  - git
tags:
  - [git, github]
toc: true
classes: wide
toc_sticky: false
 
date: 2021-09-07
last_modified_at: 2021-09-07

---



## 어라 이게 뭐지?

<img alt="image-20210907201132863" src="https://user-images.githubusercontent.com/19897864/132344869-b1a32cdc-72da-49fd-9fc5-ae0c24dc7009.png">

 Github에는 repository 메인 페이지에 contribution 그래프가 있다. 개발자의 삶을 열심히 살다보면 회색이었던 그래프들이 초록색으로 바뀌는 것을 볼 수 있다. 보통 잔디를 채운다고 하는데 code rivew, commit, pull request 와 같은 activity들을 하면 그래프가 초록색으로 바뀐다. 잔디가 심어지면 심어질 수록 뿌듯함을 느낄 수 있다. 그런데 종종 commit을 날리고 push request를 해도 그래프가 채워지지 않는 경우가 있다. 



## 왜?

- ***commit 할 때 email 주소가 github 계정의 email 주소와 같아야 한다.***

  대부분 이 이유 때문이다. 나 같은 경우는 내 PC의 git 설정에서 email 주소가 전부 빠져있었다. 

  그동안 헛짓거리 한거지 뭐..
  
  <img alt="image-2021-09-07-20 18 29" src="https://user-images.githubusercontent.com/19897864/132344916-60e01f4b-5afa-45a2-b49f-6de6b67b07c9.png" align="center" style="zoom:50%;" >



- 추후에는 이런일이 없도록 아래 명령어를 통해 github와 동일하게 이메일을 먼저 바꿔준다.

  ```shell
  git config user.email 바꿀이메일주소
  ```

- 그럼 지금까지 commit 했던 나의 작업물들은? 

  

## 해결방법

### ***🔥 주의🔥 절대 협업 중인 프로젝트에는 사용하지 말 것 </u>*** 

```shell
git filter-branch --env-filter ' 
NEW_NAME="본인이름"
NEW_EMAIL="이메일@gmail.com"
 
export GIT_AUTHOR_NAME=$NEW_NAME
export GIT_COMMITTER_NAME=$NEW_NAME
export GIT_AUTHOR_EMAIL=$NEW_EMAIL
export GIT_COMMITTER_EMAIL=$NEW_EMAIL
'
```

- shell 스크립트로 Author를 다 바꿔버리면 된다 

- 바꾼 후 아래 명령어를 통해 강제로 push한다

  ```
  git push -f
  ```

  

