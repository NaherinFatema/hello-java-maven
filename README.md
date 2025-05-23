# Jenkins Java Maven Project:

This repository demonstrates a simple Java project built using Maven and automated using Jenkins inside a Docker container. It is part of a DevOps challenge that includes setting up Jenkins, configuring Maven, and executing a successful CI build pipeline.

## Project Structure

task-8/
├── pom.xml
└── src/
  └── main/
    └── java/
      └── HelloWorld.java

## Tools Used

* Java 17
* Maven
* Jenkins (running in Docker)
* Git
* GitHub

## Jenkins Setup Summary

1. Jenkins was launched inside a Docker container:

   docker run -p 8080:8080 -v jenkins\_home:/var/jenkins\_home jenkins/jenkins\:lts

2. Jenkins was accessed via: [http://localhost:8080](http://localhost:8080)

3. Initial setup included:

   * Unlocking Jenkins using the admin password
   * Installing default plugins
   * Creating an admin user

## Maven Configuration

* Accessed via: Manage Jenkins > Tools
* Under Maven installations, a new Maven entry was created

  * Name: Maven
  * Selected: Install automatically

## Jenkins Job Configuration

* Job type: Freestyle Project
* Job name: hello-java-maven
* Used default Jenkins workspace (no custom workspace)
* Build step:

  * Invoke top-level Maven targets
  * Goal: clean install

## Code Deployment to Jenkins Container

Since Jenkins was running in Docker, the code was manually copied into the Jenkins workspace using:

docker cp "C:/Internship/task-8/." <container-name>:/var/jenkins\_home/workspace/hello-java-maven

This ensured pom.xml and the src/ directory were available to Jenkins.

## Building the Project

* The job was triggered via Jenkins Dashboard by clicking "Build Now"
* Console output confirmed success with the message:

  \[INFO] BUILD SUCCESS

## Repository

[https://github.com/NaherinFatema/hello-java-maven](https://github.com/NaherinFatema/hello-java-maven)

Naherin Fatema

