# AzureJavaWebApp
# Creating Spring boot app and deploy it on Azure
This repository Contains step that helps me to run Java spring boot app on azure web app(azure app service) using docker container

# Pre requisites
1. Linux machine or VM having Docker & git installed.
2. Azure Credentials
3. Docker hub account - not using azure container registry.

# Steps
1. Java -
Compile & Package
--------------
-  I created a java demo project and pushed to github for that you can use your own also.
Reference Repository : [Azure-Webapp-java](https://github.com/MontuD/azure-webapp-java)
-  You have to clone or if you already have a project
-  Compile it and package using maven 
    use mvn package
--------------
2. Docker  
--------------
Dockerize the above jar into Docker Image to be pushed on Docker Hub.
In this section preparing a Dockerfile that helps for creating docker image that we can use to deploy on azure.
 - I had Created my own image on the top of ubuntu:latest.
 - installed java (version 11) and maven (version 3.6) on it.
 - Pushed on Docker hub.
 - On the top of it Copied the created jar file from the java section using COPY command
 COntent of Dockerfile will be
 FROM montud/java11-with-mvn 
 WORKDIR /javawebapp
 COPY /projectdir/target/*.jar /javawebapp/spring-app.jar
 ENV PORT 8080
 EXPOSE PORT 8080
 ENTRYPOINT ["java" , "-jar","spring-app.jar"]
 



    





Login to Azure Portal
