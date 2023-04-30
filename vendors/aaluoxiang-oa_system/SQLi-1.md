# Oasys by aaluoxiang has SQL injection

BUG_Author: acmglz

vendors: https://gitee.com/aaluoxiang/oa_system

**The star of the system is 6.8k.**

Vulnerability File: 
- /oa_system-master/src/main/java/cn/gson/oasys/controller/inform/InformController.java
- /oa_system-master/target/classes/mappers/notice-mapper.xml

First get the code and look at the dependency, find that mybatis is used in the project, and then see if ${} is used in the mapping file: as you can see, the following interface uses ${} string concatenation.
- /oa_system-master/target/classes/mappers/notice-mapper.xml
![image](https://user-images.githubusercontent.com/54017627/235347721-1ba84300-1f95-4d8f-8f11-7e4cef7bae3f.png)



Next, search the controller to see which controller uses the interface, and finally find a use in the notification list:
- /oa_system-master/src/main/java/cn/gson/oasys/controller/inform/InformController.java

![image](https://user-images.githubusercontent.com/54017627/235347674-e1eca7b1-7c7f-4696-8ac3-b5c69c822b84.png)


Vulnerability verification:

By constructing paylaod, sql injection is realized successfully.

![image](https://user-images.githubusercontent.com/54017627/235347747-eb984219-7c40-47bc-9882-28df2edc576a.png)

![image](https://user-images.githubusercontent.com/54017627/235347763-84987514-24c7-4f74-b3ec-699830db1283.png)
