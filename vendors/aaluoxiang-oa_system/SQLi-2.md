# Oasys by aaluoxiang has SQL injection

**BUG_Author**: acmglz

vendors: https://gitee.com/aaluoxiang/oa_system

**The star of the system is 6.8k.**

Vulnerability File: 
- /oa_system-master/src/main/java/cn/gson/oasys/controller/address/AddrController.java
- /oa_system-master/src/main/resources/mappers/address-mapper.xml

First get the code and look at the dependency, find that mybatis is used in the project, and then see if ${} is used in the mapping file: as you can see, the following interface uses ${} string concatenation.
- /oa_system-master/src/main/resources/mappers/address-mapper.xml
![image](https://user-images.githubusercontent.com/54017627/235348139-912783e2-e928-43a1-9f6a-b75f24f5eac3.png)



Next, search the controller to see which controller uses the interface, and finally find a use in the notification list:
- /oa_system-master/src/main/java/cn/gson/oasys/controller/address/AddrController.java

![image](https://user-images.githubusercontent.com/54017627/235348226-41d8e752-7dd9-444f-b746-a12038b42d8f.png)


Vulnerability verification:

The construction request is as follows:

By constructing paylaod, sql injection is realized successfully.

![image](https://user-images.githubusercontent.com/54017627/235348247-9719ff90-6b76-42ef-9161-61d19db32cd5.png)

![image](https://user-images.githubusercontent.com/54017627/235348272-1c49b1d2-3136-4713-b359-30555b251006.png)

![image](https://user-images.githubusercontent.com/54017627/235348313-0185659f-5081-4ef8-8531-9c5f979fcffb.png)
