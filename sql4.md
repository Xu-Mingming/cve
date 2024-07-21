## The clinic patient management system has SQL injection vulnerability
## supplier
https://www.sourcecodester.com/php-clinics-patient-management-system-source-code
## Vulnerability file
/pms/ajax/get_patient_history.php
## describe
Unrestricted SQL injection attacks exist in the inventory management system. The parameters that can be controlled are as follows:  patient_id  This function executes the patient_id parameter into an SQL statement without any restrictions. Malicious attackers can use this vulnerability to obtain sensitive information in the server database
## code analysis
The patient_id parameter in get_patient_history.php is controlled and is directly carried into the SQL statement for execution, resulting in SQL injection
![image](https://github.com/user-attachments/assets/df74ec29-0692-426d-9461-bde368d16b3f)
Injection via the patient_id parameter
![image](https://github.com/user-attachments/assets/ace05073-3cf0-406c-90bf-d00bf139839a)
![image](https://github.com/user-attachments/assets/f05954e1-f973-4459-8b83-1d5eb73787f7)

