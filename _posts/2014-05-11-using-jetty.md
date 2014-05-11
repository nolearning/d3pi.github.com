---
layout: post
title: Jetty and Eclipse
---

Servlet & Tomcat & Jetty
---------------------------
* [How servlet works](http://www.ibm.com/developerworks/cn/java/j-lo-servlet/)
* [Tomcat 系统架构与设计模式，第 1 部分: 工作原理](http://www.ibm.com/developerworks/cn/java/j-lo-tomcat1/index.html)
* [Tomcat 系统架构与设计模式，第 2 部分: 设计模式分析](http://www.ibm.com/developerworks/cn/java/j-lo-tomcat2/)
* [嵌入式Tomcat7.0配置和启动代码](http://linhao315.iteye.com/blog/1477497)

Jetty vs tomcat
-------------------------
There are many article talk about the Java Web Servers, such as Tomcat, Jetty, Resin, Netty. Tomcat is the most used Java Web Server, and Jetty is widely used in many cloud platform.

more details see:

* [why use jetty?](https://www.webtide.com/choose/jetty.jsp)
* [Jetty VS Tomcat Performance Comparison](http://www.asjava.com/jetty/jetty-vs-tomcat-performance-comparison/)
* [TOMCAT VS JETTY VS RESIN](http://blog.newitfarmer.com/architecture/j2ee-architecture/3056/repost-tomcat-vs-jetty-vs-resin)
* [Servlet Performance Report](http://www.webperformance.com/library/reports/ServletReport/)


Jetty in use
----------------
* [Jetty : The Definitive Reference](http://www.eclipse.org/jetty/documentation/current/)
* [Using Jetty 7 & 8 with Eclipse ](http://wiki.eclipse.org/Jetty/HowTo/Using_Jetty_with_Eclipse)
* [Embedding Jetty](http://www.eclipse.org/jetty/documentation/current/embedding-jetty.html)
* [Embedding Jetty 7 & 8](http://wiki.eclipse.org/Jetty/Tutorial/Embedding_Jetty)
* [Jetty WTP Plugin](http://wiki.eclipse.org/Jetty_WTP_Plugin)
* [Hello world with Jetty + Maven + Eclipse WTP tutorial](http://devblog.virtage.com/2013/02/hello-world-with-jetty-maven-eclipse-wtp-tutorial/)

JDNI
-----------
* [Integration with Maven WAR Plugin](https://docs.sonatype.org/display/M2ECLIPSE/Integration+with+Maven+WAR+Plugin)
* [Configuring JNDI](http://www.eclipse.org/jetty/documentation/current/jndi.html)
* [JNDI in Jetty](http://wiki.eclipse.org/Jetty/Feature/JNDI)
* [Configuring JNDI DataSource for Database Connection Pooling in Tomcat](http://www.codejava.net/servers/tomcat/configuring-jndi-datasource-for-database-connection-pooling-in-tomcat)
* [Tomcat DataSource JNDI Example for Servlet Web Application](http://www.journaldev.com/2513/tomcat-datasource-jndi-example-for-servlet-web-application)

run_jetty_run
---------------
JNDI enable in run configurations->Jetty WebApp->***App->Jetty Tab->ShowAdvanced Options->Other configs->JNDI support

Database in Jetty
-------------------
Add jetty_env.xml to WEB_INF dir, then write database setting

* [Datasource Examples](http://www.eclipse.org/jetty/documentation/current/jndi-datasource-examples.html)
* [Configure JNDI Datasource](http://wiki.eclipse.org/Jetty/Howto/Configure_JNDI_Datasource)
