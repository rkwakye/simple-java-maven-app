  
  
* Ran Pipeline and got error:
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
+ docker pull maven:3.9.5-eclipse-temurin-17-alpine

error during connect: Post "https://docker:2376/v1.24/images/create?fromImage=maven&tag=3.9.5-eclipse-temurin-17-alpine": dial tcp: lookup docker on 127.0.0.11:53: server misbehaving

script returned exit code 1"
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

* Seems there is a DNS problem with the jenkins install. Revisit the setup from the beginning.
* was missing the docker:dind Docker image which allows youto execute docker commands inside jenkins nodes.
* maven docker container could then be made. pipeline executed sucessfully. 