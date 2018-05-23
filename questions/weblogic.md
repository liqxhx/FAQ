```
/home/weblogic/jrockit-jdk1.6.0_45-R28.2.7-4.1.0/bin/java
-jrockit
-Xms1024m
-Xmx16384m
-XX:PermSize=128m
-XX:MaxPermSize=512m
-XX:NewSize=256m
-XX:MaxNewSize=256m
-Dweblogic.Name=AdminServer
-Djava.security.policy=/home/weblogic/bea/wlserver_10.3/server/lib/weblogic.policy
-javaagent:/opt/br/bonree.jar
-Dweblogic.ProductionModeEnabled=true
-da
-Dplatform.home=/home/weblogic/bea/wlserver_10.3
-Dwls.home=/home/weblogic/bea/wlserver_10.3/server
-Dweblogic.home=/home/weblogic/bea/wlserver_10.3/server
-Dweblogic.management.discover=true
-Dwlw.iterativeDev=false
-Dwlw.testConsole=false
-Dwlw.logErrorsToConsole=false
-Dweblogic.ext.dirs=/home/weblogic/bea/patch_wls1036/profiles/default/sysext_manifest_classpath:/home/weblogic/bea/patch_ocp371/profiles/default/sysext_manifest_classpath
-Djava.security.egd=file:/dev/./urandom
-Djava.net.preferIPv4Stack=true
-DUseSunHttpHandler=true
-Djava.library.path=/opt/br/lib
weblogic.Server



```
