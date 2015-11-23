# IRIS

A runtime for Interaction, Reporting & Information Services.


## Purpose

Quickly and easily create REST APIs for use by humans and machines.

The project allows you to:

* create web based services according to RESTful constraints
* aggregate / mashup multiple resource managers into a single interaction service
* program Hypermedia (HATEOAS) interactions with a state machine domain specific language (DSL)

## Required steps
NB Java JDK 1.8 will not work
* Install Java JDK 1.7 (or JDK 1.6 by skipping some integration test modules) (http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)
* Install Maven 3.0.5 (http://archive.apache.org/dist/maven/maven-3/3.0.5/binaries/)
* Configure settings.xml in your maven/conf folder to add the following maven repository
  *Add in the profile section: 
    <profile>
      <id>Any Profile Name</id>

      <repositories>
        <repository>
          <id>Any Repo ID Name</id>
          <name>Any Repo Name</name>
          <url>**SEE BELOW**</url>
          <layout>default</layout>
        </repository>
      </repositories>
    </profile>
  * If you're within a Temenos network the URL is:
    * http://maven.oams.com/content/groups/all/
  * If you're **NOT** within a Temenos network the URL is:
    * https://repository-temenostech.forge.cloudbees.com/snapshot/

* Create a clone repository of the IRIS tree (https://github.com/temenostech/IRIS)
 * Install TurtoiseGIT if you want a GUI 
* Add JRE7/bin folder to your environment Path variables
* Add JAVA_HOME to your environment variables
* Add maven/bin folder to your environment Path variables
* Open a command prompt
 * To check if the previous steps have gone correct type: **java -version** (it should say java version 1.7) and **mvn -version** (it should say maven version 3.0.5)
 * Go to your cloned repository
 * Type: **SET MAVEN_OPTS=-Xms512m -Xmx1024m -XX:PermSize=256m -XX:MaxPermSize=512m**
 * Type: **mvn clean install**

## Build commands:

NB - Due to the InMemory database the integration tests need quite a bit of memory in the PERM space.
`SET MAVEN_OPTS=-Xms512m -Xmx1024m -XX:PermSize=256m -XX:MaxPermSize=512m`

`mvn clean` Clean projects

`mvn install` Build and install to maven repository

`mvn install -Ddebug` Build and install to maven repository without running integration tests

`mvn site` Build maven site

`mvn site:deploy` Deploy maven site [default: C:\temp\iris\site]

