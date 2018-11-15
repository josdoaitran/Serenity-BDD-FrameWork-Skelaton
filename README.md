# Serenity Behaviour Driven Development FW

Serenity BDD FW

*Document*: http://www.thucydides.info/docs/serenity/

In Serenity, requirements are organized into three levels:

- capabilities
- features
- stories 
 
## Maven Repository

Maven Dependencies
To make use of Serenity with JUnit, we should include serenity-core and serenity-junit in the pom.xml:
```
<dependency>
    <groupId>net.serenity-bdd</groupId>
    <artifactId>serenity-core</artifactId>
    <version>1.2.5-rc.11</version>
</dependency>
<dependency>
    <groupId>net.serenity-bdd</groupId>
    <artifactId>serenity-junit</artifactId>
    <version>1.2.5-rc.11</version>
</dependency>
```
We also need serenity-maven-plugin to have reports aggregated from test results:

```
<plugin>
    <groupId>net.serenity-bdd.maven.plugins</groupId>
    <artifactId>serenity-maven-plugin</artifactId>
    <version>1.2.5-rc.6</version>
    <executions>
        <execution>
            <id>serenity-reports</id>
            <phase>post-integration-test</phase>
            <goals>
                <goal>aggregate</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```
If we want Serenity to generate reports even if there’s a test failure, add the following to the pom.xml:

```
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>2.20</version>
    <configuration>
        <testFailureIgnore>true</testFailureIgnore>
    </configuration>
</plugin>
```
