# JavaEE reference application - Boilerplate project - CD Book Store

## Table of Contents
**[Resource location](#resource-location)**  
**[Overview](#overview)**  
**[System requirements](#system-requirements)**  
**[Deployment and Tests](#deployment-and-tests)**  
**[Important code blocks](#important-code-blocks)**  


## Resource location

Resource - [PluralSight] Java EE: The Big Picture (Oct 28, 2015)

Github Repository - [https://github.com/agoncal/agoncal-application-cdbookstore](https://github.com/agoncal/agoncal-application-cdbookstore)

## Overview

This e-commerce web app allows you to buy CDs and Books.

The goals of this sample is to :

* use Java EE 7 and just Java EE 7 : no external framework or dependency (except web frameworks or logging APIs)
* make it simple : no complex business algorithm, the point is to bring Java EE 7 technologies together to create an eCommerce website

The only external framework used are [Arquillian](http://arquillian.org/), [Twitter Bootstrap](http://twitter.github.io/bootstrap/) and [PrimeFaces](http://www.primefaces.org/). Arquillian is used for integration testing. Using Maven profile, you can test services, injection, persistence... against different application servers. Twitter Bootstrap and PrimeFaces bring a bit of beauty to the web interface.

To fill up the database, I've used some Amazon Web Services. You will find the raw XML data in the `xml` directory with XSLT transformation (zipped so it's not too big).

## System requirements

The case study was developed using the following:

- Development Environment
	- Windows 10, 64-bit
	- IntelliJ Idea 15.0 Ultimate
- Technologies
	- JDK 1.7.0_45
	- Java EE 7 (JPA 2.1, CDI 1.1, Bean Validation 1.1, EJB Lite 3.2, JSF 2.2, JAX-RS 2.0)
	- Twitter Bootstrap (Bootstrap 3.x, JQuery 2.x, PrimeFaces 5.x)
- Application Servers
	- WildFly 8.1.0.Final

## Deployment and Tests

### Deployment and test scenario demo video

[Watch video - 1.server deployment, tests with arquillian and test scenario demo video](https://youtu.be/_rCyKZoaJjg)

### Start Wildfly

Open a command line and navigate to the root of the Tomcat directory.
The following shows the command line to start the server:

	For Linux:   WILDFLY_HOME/bin/startup.sh
	For Windows: WILDFLY_HOME\bin\startup.bat

### Build and Deploy the application

1. You can compile and package it without tests using `mvn clean compile -Dmaven.test.skip=true`, `mvn clean package -Dmaven.test.skip=true` or `mvn clean install -Dmaven.test.skip=true`. Once you have your war file, you can deploy it.

2. Make sure you have started the Wildfly Server as described above.

3. Open a command line and navigate to the root directory of this example.
4. Type this command to build and deploy the archive:

		mvn wildfly:deploy  
5. Type this command to build and deploy the archive without tests.

		mvn wildfly:deploy -Dmaven.test.skip=true  

6. This will deploy target/applicationCDBookStore.war to the running instance of the server.

### Undeploy the Archive
1. Make sure you have started the Tomcat Server as described above.
2. Open a command line and navigate to the root directory of this example.
3. When you are finished testing, type this command to undeploy the archive:

        mvn wildfly:undeploy

### Test with Arquillian

Launching tests under WildFly is straight forward. You only have to launch WidlFly and execute the tests using the Maven profile :

    mvn clean test -Parquillian-wildfly-remote

### Test scenario

1. Once deployed go to the following URL and start buying some books and cds: [http://localhost:8080/applicationCDBookStore](http://localhost:8080/applicationCDBookStore).

2. The admin [REST interface](rs/application.wadl) allows you to create/update/remove items in the catalog, orders or customers. You can run the following [curl](http://curl.haxx.se/) commands :

	* `curl -X GET http://localhost:8080/applicationCDBookStore/rs/catalog/categories`
	* `curl -X GET http://localhost:8080/applicationCDBookStore/rs/catalog/products`
	* `curl -X GET http://localhost:8080/applicationCDBookStore/rs/catalog/items`

	You can also get a JSON representation as follow :

		* `curl -X GET -H "accept: application/json" http://localhost:8080/applicationCDBookStore/rs/catalog/items`

## Important code blocks