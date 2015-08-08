Resource location
=================
Advanced Java EE Development with WildFly Book - Chapter 10 code

Rest JSON Example
==========================
* Technologies: Rest, JSON
* Summary: Processing JSON in a RESTful web service
* Target Server: WildFly

System requirements
-------------------
All you need to build this project is Java 7.0 (Java SDK 1.7) or better, Maven 3.1 or better.

The application this project produces is designed to be run on JBoss WildFly.

Configure Maven
---------------
If you have not yet done so, you must [Configure Maven](../README.md#mavenconfiguration) before testing the quickstarts.

Start JBoss WildFly with the Web Profile
-------------------------
1. Open a command line and navigate to the root of the JBoss server directory.
2. The following shows the command line to start the server with the web profile:

        For Linux:   JBOSS_HOME/bin/standalone.sh
        For Windows: JBOSS_HOME\bin\standalone.bat

Build and Deploy the Quickstart
-------------------------
_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](../README.md#buildanddeploy) for complete instructions and additional options._

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        mvn clean package wildfly:deploy

4. This will deploy `target/Rest-Json.war` to the running instance of the server.

Prerequisites before running the application
--------------------------------------------
* Create a text file named "jsonOutput.txt" inside folder "/home/nuwan/Desktop". If the application is running on windows platform, change the file path in createJson.jsp file accordingly. (C:/jsonOutput.txt)

Access the application 
---------------------
The application can be tested with following URLs:                 
* <http://localhost:8080/Rest-Json/resources/jaxrs>
* <http://localhost:8080/Rest-Json/createJson.jsp>
* <http://localhost:8080/Rest-Json/jaxrsGetJsonReturnType.jsp>
* <http://localhost:8080/Rest-Json/jaxrsGetJsonStringMethodParam.jsp>
* <http://localhost:8080/Rest-Json/jaxrsPostJsonMethodParam.jsp>
* <http://localhost:8080/Rest-Json/parseJson.jsp>

Undeploy the Archive
--------------------
1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        mvn wildfly:undeploy

Run the Quickstart in JBoss Developer Studio or Eclipse
-------------------------------------
You can also start the server and deploy the quickstarts from Eclipse using JBoss tools. For more information, see [Use JBoss Developer Studio or Eclipse to Run the Quickstarts](../README.md#useeclipse) 

Debug the Application
------------------------------------

If you want to debug the source code or look at the Javadocs of any library in the project, run either of the following commands to pull them into your local repository. The IDE should then detect them.

        mvn dependency:sources
        mvn dependency:resolve -Dclassifier=javadoc