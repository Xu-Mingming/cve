## SQL injection vulnerability exists in the inventory management system
## supplier
https://www.sourcecodester.com/php/15419/simple-inventory-management-system-phpoop-free-source-code.html
## Vulnerability file
/php-simple-ims/ims/action.php
## describe
Unrestricted SQL injection attacks exist in the inventory management system. The controllable parameters are as follows :btn_action This function executes the btn_action parameter into an SQL statement without any restrictions. Malicious attackers can exploit this vulnerability to obtain sensitive information in the server database
## code analysis
The action.php parameter in action.php is controllable, and is directly carried into the SQL statement for execution, resulting in SQL injection
![图片1](https://github.com/user-attachments/assets/b11bceb4-c42e-4929-965a-dfce0e7435e4)
## recurrence
![image](https://github.com/user-attachments/assets/b0f47621-1d4c-4297-9f7d-0252e8f8f50e)
![image](https://github.com/user-attachments/assets/a38c57d3-8a3e-4626-b2c7-d876a61dc973)

