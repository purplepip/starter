# Introduction

Bootstrap a Java project for rapid development.

# TL;DR

Either extend as parent

      <parent>
        <groupId>com.purplepip</groupId>
        <artifactId>starter</artifactId>
        <version>1.0.6</version>
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

It's easiest to create project from the [archetype](https://github.com/purplepip/archetype)
which uses this starter project.  If you prefer to go manual then see the 
example pom.xml below.

# Why this Starter?

I tend to use so regularly it's easier for me to bundle what I use together
to help me bootstrap my projects.   The bootstrap project taps into the
following *optional* components :

* Junit & Mockito - for testing
* Lombok, SL4J and logback - for logging
* Spring boot - for service rapid development
* Jacoco code coverage
* Auto Java formatting to google style guide

Please feel free to use as is, or just cherry pick and copy what you 
want :)

# Example pom.xml

A project that uses the starter pom will look something like the following :
```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>com.purplepip</groupId>
    <artifactId>starter</artifactId>
    <version>1.0.6</version>
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
```

Although note it may be easier to start with the 
[archetype](https://github.com/purplepip/archetype)
and cherry pick, delete what you don't want.
