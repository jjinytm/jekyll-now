---
layout: page
title: xPlatform Tip
category: xplatform
---

- 특정 오브젝트에 이벤트를 강제로 발생시키고 싶을 때
```javascript
  //이벤트 객체를 발생시킨다.
  var e1 = new GridClickEventInfo();

  //이벤트를 발생시키고자하는 object(grdResult1)에
  //발생시키고자 하는 이벤트(oncelldblclick) 에
  //fireEvent 메소드를 발생. 인자로 object와 이벤트 객체를 넘겨준다.
	grdResult1.oncelldblclick.fireEvent(grdResult1, e1);
```
