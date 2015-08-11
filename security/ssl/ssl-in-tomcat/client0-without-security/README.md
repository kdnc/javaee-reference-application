Resource location
-----------------
* Web article - <http://krishnasblog.com/2012/12/11/spring-security-certificate-authentication-authorization-example/>
* Git repository - <https://github.com/skprasadu/enable-ssl-in-tomcat>

Additional Resources
-------------------
* Set Tomcat administrator password to access tomcat manager - <http://www.mkyong.com/tomcat/tomcat-default-administrator-password/>
* Maven - Deploy war in Tomcat 7 & 8 - <http://kosalads.blogspot.com/2014/03/maven-deploy-war-in-tomcat-7.html>

System requirements
-------------------
All you need to build this project is Java 7.0 (Java SDK 1.7) or better, Maven 3.1 or better.

The application this project produces is designed to be run on Tomcat.

Start Tomcat
------------
1. Open a command line and navigate to the root of the Tomcat directory.
2. The following shows the command line to start the server:

        For Linux:   TOMCAT_HOME/bin/startup.sh
        For Windows: TOMCAT_HOME\bin\startup.bat

Build and Deploy the application
--------------------------------
1. Make sure you have started the Tomcat Server as described above.
2. Open a command line and navigate to the root directory of this example.
3. Type this command to build and deploy the archive:

        mvn tomcat7:deploy  

4. This will deploy `target/security-ssl-ssl_in_tomcat_without_security.war` to the running instance of the server.

Access the application 
----------------------
The application can be tested with following URLs:                 
* <http://localhost:8080/security-ssl-ssl_in_tomcat_without_security/>

Undeploy the Archive
--------------------
1. Make sure you have started the Tomcat Server as described above.
2. Open a command line and navigate to the root directory of this example.
3. When you are finished testing, type this command to undeploy the archive:

        mvn tomcat7:undeploy