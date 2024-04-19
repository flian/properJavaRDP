properJavaRDP

Copyright (c) 2005 Propero Ltd <www.propero.net>

在原有的基础上修复一些bug

使用说明：
启动参数中加`--disk_device_map` 添加本地目录映射到远程桌面目录
如:

--disk_device_map share@D:\\Download,test@D:/upload
表示把本地的D:\\Download目录挂到远程目录，名字share
把本地D:/upload目录挂载到远程桌面，名字test
linux同样类似的挂载目录

启动命令示例：
java -jar properJavaRDP-0.1.18-SNAPSHOT.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14
更多启动命令，参考Rdesktop.usage()方法

remote debug:
java -agentlib:jdwp=transport=dt_socket,server=y,address=5003,suspend=y -jar properJavaRDP-0.1.18-SNAPSHOT.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14