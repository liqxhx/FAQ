# 1 
```shell
16-Nov-2025 10:43:21.993 INFO [localhost-startStop-1] org.apache.catalina.core.ApplicationContext.log No Spring WebApplicationInitializer types detected on classpath
16-Nov-2025 10:43:22.022 SEVERE [localhost-startStop-1] org.apache.catalina.core.StandardContext.listenerStart Exception sending context initialized event to listener instance of class [org.springframework.web.context.ContextLoaderListener]
 java.lang.StackOverflowError
        at java.util.HashMap.hash(HashMap.java:339)
        at java.util.HashMap.get(HashMap.java:557)
        at org.slf4j.impl.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:67)
        at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:277)
        at org.apache.log4j.Category.<init>(Category.java:57)
        at org.apache.log4j.Logger.<init>(Logger.java:37)
        at org.apache.log4j.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:43)
        at org.apache.log4j.LogManager.getLogger(LogManager.java:45)
        at org.slf4j.impl.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:73)
        at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:277)
        at org.apache.log4j.Category.<init>(Category.java:57)
        at org.apache.log4j.Logger.<init>(Logger.java:37)
        at org.apache.log4j.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:43)
        at org.apache.log4j.LogManager.getLogger(LogManager.java:45)
        at org.slf4j.impl.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:73)
        at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:277)
        at org.apache.log4j.Category.<init>(Category.java:57)
        at org.apache.log4j.Logger.<init>(Logger.java:37)
        at org.apache.log4j.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:43)
        at org.apache.log4j.LogManager.getLogger(LogManager.java:45)
        at org.slf4j.impl.Log4jLoggerFactory.getLogger(Log4jLoggerFactory.java:73)
        at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:277)
        at org.apache.log4j.Category.<init>(Category.java:57)
        at org.apache.log4j.Logger.<init>(Logger.java:37)
 
 在catalina.out里有这样的日志
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/tomcat-inte-develop-8082/webapps/ifms-inte/WEB-INF/lib/slf4j-log4j12-1.6.1.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/tomcat-inte-develop-8082/webapps/ifms-inte/WEB-INF/lib/logback-classic-1.2.3.jar!/org/slf4j/impl/StaticLoggerBinder.class]

执行
mvn dependency:tree
用发现是zookeeper默认引用，排除即可
[INFO] |  +- org.apache.zookeeper:zookeeper:jar:3.4.8:compile
[INFO] |  |  +- org.slf4j:slf4j-log4j12:jar:1.6.1:compile
```
