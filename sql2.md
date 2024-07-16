## SQL injection vulnerability exists in online bookstore system
## supplier
https://www.sourcecodester.com/php/15423/simple-online-book-store-system-php-free-source-code.html
## Vulnerability file
/admin_delete.php
## Vulnerability location
/admin_delete.php?bookisbn=11
## describe
Unrestricted SQL injection attacks exist in online bookstore systems. The parameters that can be controlled are :bookisbn This function executes the bookisbn parameter into the SQL statement without any restrictions. A malicious attacker can exploit this vulnerability to obtain sensitive information from a server database
## code analysis
The bookisbn parameter in admin_delete.php is controllable and carried directly into SQL statement execution, resulting in SQL injection
![image](https://github.com/user-attachments/assets/b9c21252-5ffa-4ad1-ab60-9795d356f75c)
## recurrence
![image](https://github.com/user-attachments/assets/09c42a50-0a11-41b1-b061-c09a1add7583)
![image](https://github.com/user-attachments/assets/fbbe1d9d-48ff-4ba7-b62e-89762eb743cf)
