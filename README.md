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
* Java JDK 1.7 (or JDK 1.6 by skipping some integration test modules) (http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)
* Maven 3.0.5 (http://archive.apache.org/dist/maven/maven-3/3.0.5/binaries/)
* Configure settings.xml in your maven/conf folder to add the following maven repository
  *Add: 
    <profile>
      <id>Your Profile Name</id>

      <repositories>
        <repository>
          <id>Your Repo Name</id>
          <name>Your Repo Name</name>
          <url>**SEE BELOW**</url>
          <layout>default</layout>
        </repository>
      </repositories>
    </profile>
  * If you're within a Temenos network the URL is:
    * http://maven.oams.com/content/groups/all/
  * If you're **NOT** within a Temenos network the URL is:
    * https://repository-temenostech.forge.cloudbees.com/snapshot/

* Add JRE7/bin folder to your environment Path variables

## Build commands:

NB - Due to the InMemory database the integration tests need quite a bit of memory in the PERM space.
`SET MAVEN_OPTS=-Xms512m -Xmx1024m -XX:PermSize=256m -XX:MaxPermSize=512m`

`mvn clean` Clean projects

`mvn install` Build and install to maven repository

`mvn install -Ddebug` Build and install to maven repository without running integration tests

`mvn site` Build maven site

`mvn site:deploy` Deploy maven site [default: C:\temp\iris\site]

