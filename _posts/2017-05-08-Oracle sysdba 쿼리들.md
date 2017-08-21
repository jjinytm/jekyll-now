---
layout: page
title: Oracle sysdba쿼리들
category: oracle
---

- 계정생성
```javascript
CREATE USER [유저명] IDENTIFIED BY [비밀번호];
```

- 생성한 계정에 권한 부여하기
```javascript
//DBA 권한 부여
GRANT CONNECT, RESOURCE, DBA TO [유저명];
```

- 생성한 계정의 비밀번호를 수정하기
```javascript
ALTER USER [유저명] IDENTIFIED BY [비밀번호];
```
