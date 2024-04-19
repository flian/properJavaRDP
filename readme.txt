properJavaRDP

Copyright (c) 2005 Propero Ltd <www.propero.net>

在原有的基础上修复一些bug

remote debug:
java -agentlib:jdwp=transport=dt_socket,server=y,address=5003,suspend=y -jar properJavaRDP-0.1.18-SNAPSHOT.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14