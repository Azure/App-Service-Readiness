---
title: "Java, Tomcat, and JBoss EAP version updates"
author_name: "Jason Freeberg"
tags: 
    - Java
---

The latest App Service releases included new Java, Tomcat and JBoss EAP versions.

## Windows

- New Tomcat versions
  - 9.0.38
  - 8.5.58
- New Java versions
  - 11.0.8
  - 8.0.265
  - 7.0.272

Eclipse Foundation has deprecated Jetty 9.1 and 9.3 ([source](https://www.eclipse.org/jetty/download.php)), so these runtimes are no longer shown on the Portal. You can still [create sites with these versions](https://docs.microsoft.com/azure/app-service/overview#built-in-languages-and-frameworks). Tomcat 8.0 has [reached End-Of-Life](https://tomcat.apache.org/tomcat-80-eol.html) and will also be hidden in an upcoming Portal update. Web apps using these outdated runtimes will continue to run, but using the latest versions ensures that your apps are running on the most secure and performant runtimes.

## Linux

- JBoss EAP is now available with Java 11
  - JBoss EAP now has an "auto-update" option. This option currently uses JBoss 7.2 but will automatically use the latest JBoss versions as they are added.
- New Java versions 
  - 8u252
  - 11.0.7
- New Tomcat versions
  - 9.0.37
  - 8.5.57

## How to upgrade your Java or Tomcat version

To upgrade your Java or Tomcat version, open the Azure Portal to your web app and open the **Configuration** blade. Under the **General settings** tab you can select a new Java and Tomcat version using the dropdowns for **Java minor version** and **Java web server version**.

![Upgrade your Java versions in the Portal]({{site.baseurl}}/media/2021/01/upgrade-java-versions.png)
