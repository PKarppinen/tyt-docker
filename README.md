# Trail your trails application

This repository contains all needed Docker files to build and run Trail your trails application cluster.

Needed commands
- To build needed Docker images run: 	**docker-compose -f docker-compose.yml build --build-arg API_IP=\<YOUR SERVER IP ADDRESS\>**
- To run the cluster: **docker-compose -f docker-compose.yml up**
 
Above commands will build and run the cluster with
- A Single node for front end application. Source code repository: https://github.com/PKarppinen/tyt-frontend-repo
- A Single node for back end application. Source code repository: https://github.com/PKarppinen/tyt-api-repo
- A Single node for MongoDB database

All nodes will be in Docker containers. There are no load balancers, any other proxies, auto scaling etc.

Back end application is protected by Spring Security and Basic authentication.

Simple architecture diagram of AWS EC2 setup
![AWS EC2 setup](./Docker-setup.PNG)

Better approach would be to use multi node cluster with load balancers. For example in AWS ECS
![AWS ECS setup](./ECS-setup.PNG)