## XDataETL下载 ##
### 查看本地maven库路径 ###
<img src="https://raw.githubusercontent.com/baozouxiaoshou/XDataETL/master/image/3.png" width = "500" height = "320" alt="图1" />
### 将依赖下载相应的路径下 ###
 <img src="https://raw.githubusercontent.com/baozouxiaoshou/XDataETL/master/image/4.png" width = "500" height = "320" alt="图1" />
### 两种下载方式 ###
1、在此目录下右键命令窗口 --> 执行  <br/>**git clone https://github.com/baozouxiaoshou/XDataETL/tree/master/xDataETL**
<br/>2、如果本地未安装git，则下载zip文甲，解压到相应的路径下<br/>
下载地址[https://raw.githubusercontent.com/baozouxiaoshou/XDataETL/master/xDataETL.zip](https://raw.githubusercontent.com/baozouxiaoshou/XDataETL/master/xDataETL.zip "XDataETL依赖下载地址")

## XDataETL配置项目环境中 ##

### maven项目 ###

<pre>
pom.xml文件中添加引用
</pre> 
```<dependency>```</br>
&nbsp;&nbsp;&nbsp;&nbsp;```<groupId>com.pansoft.xbrl</groupId>```  
&nbsp;&nbsp;&nbsp;&nbsp;```<artifactId>XDataETL</artifactId>```  
&nbsp;&nbsp;&nbsp;&nbsp;```<version>0.0.1-SNAPSHOT</version> ```</br>
```</dependency>```

 
### 普通项目 ###
<pre style="font-size:14px">
将jar包直接引用到项目中
</pre>

### XDataETL初始化 ###
<pre style="font-size:14px">
<code>
        // 处理器
        XDataETLBuilder xDataEtlBuilder = XDataETLBuilder.getInstance();
        try {
            // 初始化   主数据连接信息、临时数据库连接信息、参数配置文件路径，自定义处理器配置文件 回调类
            xDataEtlBuilder.initialized(mainOpt, tempOpt, propCfgPath, handlerCfgPath, jobCallback);
        }
        catch (BuilderException e) {
            // TODO Auto-generated catch block
            e.printStackTrace();
        }
</code>
</pre>

### 注意事项 ###
<pre style="font-size:14px">
1、maven引用包是否冲突，根据控制台提示查看相关的包。（图1）
<img src="https://raw.githubusercontent.com/baozouxiaoshou/XDataETL/master/image/1.png" width = "500" height = "320" alt="图1" />
2、引入jar包之后启动tomcat包类找不到，clean一下tomcat（图2）
<img src="https://raw.githubusercontent.com/baozouxiaoshou/XDataETL/master/image/2.png" width = "500" height = "120" alt="图1" />
</pre>
3、tomcat版本Tomcat8主选，虚拟机jdk1.8主选
