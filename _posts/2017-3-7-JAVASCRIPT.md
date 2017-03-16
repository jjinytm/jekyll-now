---
layout: post
title: JavaScript
---

Select option by index
```{.javascript}
document.all.SELECTNAME.options[index].selected = true;
```

정규식 표현으로 문자열내 html 태크 제거하기.
var str = "<br>내용<br>";
str = str.replace(/(<([^>]+)>)/ig," ");
