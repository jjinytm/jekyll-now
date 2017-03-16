---
layout: category
title: JavaScript
category: javascript
---

- 인덱스를 지정하여 해당하는 옵션을 선택(selected) 하기
```javascript
document.all.SELECTNAME.options[index].selected = true;
```

- 정규식 표현으로 문자열내 html 태그 제거하기.
```javascript
var str = "<br>내용<br>";
str = str.replace(/(<([^>]+)>)/ig," ");
```
