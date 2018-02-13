---
title: Connecting a Spring Boot App to Pivotal Cloud Cache with Session State Caching
---
<a id="spring-boot-ssc"></a>

This section describes the two ways in which you can connect a Spring Boot app to PCC: 

+ Using a Tomcat app with a WAR file. This is the default method for Tomcat apps.
+ Using the spring-session-data-gemfire library. This method requires that you use the correct version of these libraries.

##<a id="tomcat"></a> Use the Tomcat App

In PCC v1.1 and later, to get a Spring Boot app running with session state caching (SSC) on PCC,
you must create a WAR file using the `spring-boot-starter-tomcat` plugin instead of the `spring-boot-maven` plugin to create a JAR file.

For example, if you want your app to use SSC, you cannot use `spring-boot-maven` to build a JAR file and push your app to PCF,
because the Java buildpack does not pull in the necessary JAR files for SSC when it detects a Spring JAR file.

To build your WAR file, add this depedency to your `pom.xml`:

```xml
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-tomcat</artifactId>
  <scope>provided</scope>
</dependency>
```

For a full example of running a Spring Boot app that connects with SSC, [run this app](https://github.com/cf-gemfire-org/http-session-caching) and use this following for your `pom.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>

  <groupId>io.pivotal.gemfire.demo</groupId>
  <artifactId>HttpSessionCaching-Webapp</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <packaging>war</packaging>

  <name>HttpSessionCaching-Webapp</name>
  <description>Demo project for GemFire Http Session State caching</description>

  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>1.5.3.RELEASE</version>
    <relativePath/> <!-- lookup parent from repository -->
  </parent>

  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
    <java.version>1.8</java.version>
  </properties>

  <dependencies>
    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-thymeleaf</artifactId>
    </dependency>

    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-tomcat</artifactId>
      <scope>provided</scope>
    </dependency>

    <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-test</artifactId>
      <scope>test</scope>
    </dependency>
  </dependencies>

</project>
```

##<a id="spring-session"></a> Use a Spring Session Data GemFire App

You can connect your Spring app to PCC to do session state caching.
Use the correct version of the `spring-session-data-gemfire` library;
apps built for PCC v1.3.0 and later versions are compatible with
Spring Session Data GemFire v2.0.0.M2 and later versions.

###<a id=spring_session_data_gemfire></a> Upgrade PCC and Spring Session Data GemFire

1. Before your operator upgades PCC, stop your app.
This avoids breaking the app in this upgrade process.

1. Upgrade PCC. See [Upgrading Pivotal Cloud Cache](operator.html#upgrade) for details.

1. Rebuild your app using a `build.gradle` file that depends on 
the correct version of Pivotal GemFire.
Here is an example `build.gradle` file:

    ```
    version = '0.0.1-SNAPSHOT'

    buildscript {
      ext {
        springBootVersion = '2.0.0.M3'
      }
      repositories {
        mavenCentral()
        maven { url "https://repo.spring.io/snapshot" }
        maven { url "https://repo.spring.io/milestone" }
      }
      dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}")
      }
    }

    apply plugin: 'java'
    apply plugin: 'org.springframework.boot'
    apply plugin: 'idea'

    idea{
      module{
        downloadSources = true
        downloadJavadoc = true
      }
    }

    sourceCompatibility = 1.8
    targetCompatibility = 1.8

    repositories {
      mavenCentral()
      maven { url "https://repo.spring.io/libs-milestone" }
      maven { url "https://repo.spring.io/milestone" }
      maven { url "http://repo.springsource.org/simple/ext-release-local" }
      maven { url "http://repo.spring.io/libs-release/" }
      maven { url "https://repository.apache.org/content/repositories/snapshots" }
    }


    dependencies {
      compile("org.springframework.boot:spring-boot-starter-web:2.0.0.M3")
      compile("org.springframework.session:spring-session-data-gemfire:2.0.0.M2")
      compile("io.pivotal.spring.cloud:spring-cloud-gemfire-spring-connector:1.0.0.RELEASE")
      compile("io.pivotal.spring.cloud:spring-cloud-gemfire-cloudfoundry-connector:1.0.0.RELEASE")
    }
    ```

2. Clear the session state region.
3. Start the rebuilt app.

