## 库存管理系统存在SQL注入漏洞
## 供应商
https://www.sourcecodester.com/php/15419/simple-inventory-management-system-phpoop-free-source-code.html
## 漏洞文件
/php-simple-ims/ims/action.php
## 描述
库存管理系统存在不受限制的SQL注入攻击，可控参数为:btn_action 该函数将btn_action参数带入SQL语句中执行，不受任何限制，恶意攻击者可利用此漏洞获取服务器数据库中的敏感信息。
## 代码分析
action.php中action.php参数可控，直接带入SQL语句中执行，造成SQL注入
![图片1](https://github.com/user-attachments/assets/b11bceb4-c42e-4929-965a-dfce0e7435e4)
## 复现
![image](https://github.com/user-attachments/assets/b0f47621-1d4c-4297-9f7d-0252e8f8f50e)
![image](https://github.com/user-attachments/assets/a38c57d3-8a3e-4626-b2c7-d876a61dc973)

