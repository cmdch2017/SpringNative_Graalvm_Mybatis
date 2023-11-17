# SpringNative_Graalvm_Mybatis
## 遇到的问题请见博客
https://blog.csdn.net/weixin_43914278/article/details/134446327
## how to start
用了Graalvm打包，市面上大多数产品不支持Mybatis，或者没用RestController，我这个案例将其整合起来了
本地安装了mysql，且执行sql语句
CREATE TABLE persons (
                         id INT PRIMARY KEY,
                         name VARCHAR(255),
                         age INT
);
INSERT INTO persons (id, name, age) VALUES
                                        (1, 'John Doe', 25),
                                        (2, 'Jane Smith', 30),
                                        (3, 'Bob Johnson', 22);
                                    
访问端口：http://localhost:8086/person/list
![image](https://github.com/cmdch2017/SpringNative_Graalvm_Mybatis/assets/32605664/1060622f-be8f-4c60-b73b-4cec71c89b83)
## 核心启动步骤
SpringNative
首先本地安装一个mysql，然后执行resources的1.sql
1、打开 x64 Native Tools Command Prompt for VS
mvn -Pnative -DskipTests clean native:compile
2、执行反射编译语句
java -agentlib:native-image-agent=config-output-dir=C:\Demos\graalvm\src\main\resources\META-INF\native-image  -jar .\target\graalvm-0.0.1-SNAPSHOT.jar 
3、PowerShell中进入项目target目录下
.\graalvm.exe
