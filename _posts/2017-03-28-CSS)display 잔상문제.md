---
layout: page
title: CSS) display 사용시 잔상생기는 
category: html
---

tr태그에서 display:block 과 none 사용시 잔상이 발생한다.
이경우에는 tr-td안에 div를 사용하고 테이블을 사용함으로써 해결할수 있다.

```javascript
<tr id="viewform" style="display:none">
</tr>
//위처럼 사용하지 않고 아래와 같이 tr td안에 div를 사용한다.

<tr>
  <td>
    <div id="viewform" style="display:none">
      <table>
        <tr><td></td></tr>
      </table>
    </div>
  </td>
</tr>

//script
<script>
  function div_form() { 
    document.getElementById('viewform').style.display = "block"; 
  }
</script>
```
