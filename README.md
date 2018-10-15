# TL;DR

Either extend as parent

      <parent>
        <groupId>com.purplepip</groupId>
        <artifactId>starter</artifactId>
        <version>1.0.2</version>
      </parent>

Or import as a BOM

      <dependency>
        <groupId>com.purplepip</groupId>
        <artifactId>starter</artifactId>
        <version>${purplepip.version}</version>
        <type>pom</type>
        <scope>import</scope>
      </dependency>
      
Note that importing as BOM does not do quite as much as extending the parent,
for example properties are not imported, however BOM is appropriate when
you wish to extend another project.  If you want some properties, you'll need
to copy them into your local pom.

# Starter pom.xml

Kick off a project with starter pom like :

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelVersion>4.0.0</modelVersion>
      <parent>
        <groupId>com.purplepip</groupId>
        <artifactId>starter</artifactId>
        <version>1.0.2</version>
      </parent>
    
      <artifactId>my-artifact</artifactId>
      <name>My Artifact</name>
      <version>1.0.0-SNAPSHOT</version>
      <packaging>pom</packaging>
    
      <repositories>
        <repository>
          <id>purplepip-releases</id>
          <url>https://packagecloud.io/purplepip/releases/maven2</url>
        </repository>
      </repositories>
    </project>