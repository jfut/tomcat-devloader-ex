tomcat-devloader-ex
===================

Tomcat DevLoader with extra features.

Overview
--------

This provides extra features for Tomcat DevLoader of [Sysdeo Eclipse Tomcat Launcher plugin](http://www.eclipsetotale.com/tomcatPlugin.html).

* Exclude specific jar files at launching Eclipse Tomcat Launcher.
* Add class path to java.class.path.

Build
-----

You can execute it using the command below:

<pre>
mvn package
</pre>

Installation
------------

Delete default DevLoader class files.

* Tomcat 5.x
    * $TOMCAT_HOME/server/classes/org/apache/catalina/loader/
    * $TOMCAT_HOME/server/classes/org/apache/catalina/mbeans/
* Tomcat 6.x
    * $TOMCAT_HOME/lib/classes/org/apache/catalina/loader/
    * $TOMCAT_HOME/lib/classes/org/apache/catalina/mbeans/

Copy devloader-ex-x.x.jar to $TOMCAT_HOME/lib

* Tomcat 5.x: $TOMCAT_HOME/server/lib
* Tomcat 6.x: $TOMCAT_HOME/lib

### optional (if you want to use the custom exclude settings)

Copy conf/devloader.conf to $TOMCAT_HOME/conf/devloader.conf

* Example:
    * C:\Software\Java\tomcat\conf/devloader.conf
    * /usr/local/java/tomcat/conf/devloader.conf

Configurations (Optional)
-------------------------

Cutomize exclude patterns.

* $TOMCAT_HOME/conf/devloader.conf
* Format: java.util.regex.Pattern

<pre>
# default configration
(.*)/servlet-api(.*).jar
(.*)/jsp-api(.*).jar
(.*)/geronimo-jsp(.*).jar
(.*)/geronimo-servlet(.*).jar

# for examples
(.*)/servlet-api(.*).jar
file:/(.*)/servlet-api(.*).jar
(.*)/test/(.*)
</pre>

References
----------

* [m2eclipseプラグインとSysdeo/SQLI Eclipse Tomcat Launcher pluginのDevLoader改変](http://jfut.integ.jp/2007/11/16/m2eclipse-and-devloader-ex/)
