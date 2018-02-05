To RUN two app with Redis on Local with docker-compose please follow below steps.

1.Install Docker and Docker-compose on your system.

2. Clone Git repo into your system.  git clone https://github.com/serversteam/ecs-node.git 

3. cd ecs-node

4. make sure you have docker-compose.yml file downloaded from repo.

5. Run docker-compose up -d    ( this will create 2 node for app and 1 redis for storge.)

6. to see container  run  docker ps   ( you will see three container like below )

root@ip-172-31-52-46:/opt/node-redis-docker# docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                           NAMES
dc4d5665dbd1        ubuntu              "/bin/bash"              2 hours ago         Up 2 hours                                          sad_pasteur
ffa1be8a2980        wh01server/node     "npm start"              4 hours ago         Up 4 hours          0.0.0.0:3000->3000/tcp          noderedisdocker_node-app_1
5ff127744313        redis               "docker-entrypoint.s…"   4 hours ago         Up 4 hours          0.0.0.0:6379->6379/tcp          noderedisdocker_redis_1
7f8eee8d2f64        wh01server/azure    "/entrypoint.sh /sta…"   4 hours ago         Up 4 hours          443/tcp, 0.0.0.0:8080->80/tcp   azure-vote-front


7. Now you can access node and azure voting app from public IP of your instance.

Go into browser : 
http://public or Instance IP :3000 
http://public or Instance IP :8080 

you will see output like this :  http://prntscr.com/iacxhk   , http://prntscr.com/iacxnr

So here we Ran Successfully one node js and Azure voting sample app using docker compose on local

