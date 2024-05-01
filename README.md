#properJavaRDP

Copyright (c) 2005 Propero Ltd <www.propero.net>

fork from: https://github.com/bleehome/properJavaRDP

## 修改说明
1. 切换成maven项目。
2. 依赖升级。（待完成）
3. 启动命令添加 `--disk_device_map`

我的另外一个项目使用了properJavaRDP,请参考：[javaWebSsh](https://github.com/flian/webssh)

在原有的基础上修复一些bug


## 其他说明
### 使用说明：
启动参数中加`--disk_device_map` 添加本地目录映射到远程桌面目录
如:

--disk_device_map share@D:\\Download,test@D:/upload
表示把本地的D:\\Download目录挂到远程目录，名字share
把本地D:/upload目录挂载到远程桌面，名字test
linux同样类似的挂载目录

### 启动命令示例：

注意，默认打包会产生两个包：
胖包： 包含全部的依赖，可以直接通过java -jar运行
痩包： 默认给项目依赖使用的，包内没有依赖。依赖默认copy到./lib下，如果需要直接运行痩包，需要把lib目录一并拷走。

#### 痩包
java -jar properJavaRDP-0.1.18-SNAPSHOT.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14
更多启动命令，参考Rdesktop.usage()方法

remote debug:
java -agentlib:jdwp=transport=dt_socket,server=y,address=5003,suspend=y -jar properJavaRDP-0.1.18-SNAPSHOT.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14

#### 全包
java -jar properJavaRDP-0.1.18-SNAPSHOT-jar-with-dependencies.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14
更多启动命令，参考Rdesktop.usage()方法

remote debug:
java -agentlib:jdwp=transport=dt_socket,server=y,address=5003,suspend=y -jar properJavaRDP-0.1.18-SNAPSHOT-jar-with-dependencies.jar -g 1024x768 -l INFO -T HelloProperJavaRDP  --disk_device_map share@D:\\Download,test@D:/upload 192.168.1.14