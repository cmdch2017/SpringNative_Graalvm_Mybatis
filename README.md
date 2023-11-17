# SpringNative_Graalvm_Mybatis
SpringNative
首先本地安装一个mysql，然后执行resources的1.sql
1、打开 x64 Native Tools Command Prompt for VS
mvn -Pnative -DskipTests clean native:compile
2、执行反射编译语句
java -agentlib:native-image-agent=config-output-dir=C:\Demos\graalvm\src\main\resources\META-INF\native-image  -jar .\target\graalvm-0.0.1-SNAPSHOT.jar 
3、PowerShell中进入项目target目录下
.\graalvm.exe
![image](https://github.com/cmdch2017/SpringNative_Graalvm_Mybatis/assets/32605664/1060622f-be8f-4c60-b73b-4cec71c89b83)
