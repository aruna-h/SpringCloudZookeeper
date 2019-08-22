# DCP-springboot-SpringCloudZookeeper

### Project Title : DCP-springboot-SpringCloudZookeeper

### Description : This service is a part of DCP-springboot project. this application is used to get message through scheduler and zookeeper, where zookeeper is acting as centralized configuration repository where we can store our configuration properties or environment variables.

# Getting Started

These instructions will guide you to set project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

# Prerequisites

To develop, build and run the spring-cloud zookeeper, you need
JDK 1.8
Gradle tool
Install Zookeeper-3.4.7
ZooKeeper setup
1. Go to your ZooKeeper config directory. For me its C:\zookeeper-3.4.7\conf
2. Rename file “zoo_sample.cfg” to “zoo.cfg”
3. Open zoo.cfg in any text editor, like Notepad; I prefer Notepad++.
4. Find and edit dataDir=/tmp/zookeeper to :\zookeeper-3.4.7\data  
5. Add an entry in the System Environment Variables as we did for Java.
a. Add ZOOKEEPER_HOME = C:\zookeeper-3.4.7 to the System Variables.
b. Edit the System Variable named “Path” and add ;%ZOOKEEPER_HOME%\bin; 
6. You can change the default Zookeeper port in zoo.cfg file (Default port 2181).

In application.yml file of the project mention the details
Example :
spring:
  application:
    name: ZookeeperApplication
    
  cloud:
    zookeeper:
      connect-string: localhost:2181
      enabled: true
      
server:
  port: 8888

### Run Zookeeper Server : 
Run ZooKeeper by opening a new cmd and type zkserver.   

To add Property or configuration values:-
go to location: D:\Users\Downloads\softwares\zookeeper-3.4.0\bin then open zkcli
Then in zkcli prompt write: create /config/applicationname/name xyz (if you used @value property as property to be set)
   

# Running the tests :
1)Clone this project using following command :
git clone git@gitlab.com:capgemini-digital-cloud-platform/spring_cloud_zookeeper.git
2)Make sure zookeeper is up and running before launching the Spring Boot code.
3)Use STS:  Run as Spring Boot App

How to import: Go to STS(IDE)->In STS go to file-> import->from drop-down menu select gradle->in Gradle select existing gradle project->Click on browse and go to the directory where you have extracted/cloned the project->select the extracted/cloned folder*->click next->Finish. Once you click on finish wait till the project is imported(progress of which you can see in the bottom right corner) It will take around 3-5 mins. Once it is done, Right Click on the project->Go to Run as->click on Spring boot app. In console (part of IDE) you will see "Started ZookeeperApplication(service name) in 4.191 seconds (JVM running for 4.671) "(only if you have imported the code correctly). 
4)Use CMD(If failing to run through STS): run command java  –jar “name-Of-JAR-In-build/libs/.jar”

# Built With:

Java Spring Boot

Gradle  - Dependency Management 

### Version:
0.0.1

### Author:
Aruna B H