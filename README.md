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