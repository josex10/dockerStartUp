# dockerStartUp
This is a docker start up 

**Alpine**: Light version is created for containers, best practices is to use that version of linux for containers.

**Key Docker commands**

- docker build: Build a docker image
- docker run: Run a docker image as a container
- docker commit: Commit a docker container as an image
- docker tag: Tag a docker image
- docker login: To login for docker hub
- docker images | head : Show latest images
- docker ps : Show running images
- docker ps -a: Show all latest images running or stopped
- docker rename (dockername/dockerid) (newname)
- docker rm (dockername/dockerid) 
- docker container prune: Remove all the containers stoped
- docker exec: 
- docker logs: See the last logs
- docker logs -f:  See the logs on live
- docker logs --tail 10 -f: See the last 10 lines of the logs on live
- docker volumes: show all the volumes in docker
- docker volumne create volumeName: create a volumne 
- docker system prune

**Image**: In Object programming the image is like a class.

**Container**: In object programming the container is like an object.

****Keys****

- -d: run the container in the background (detach)
- -it: Interactive
- -p: port mapping (port container:port of the app)
- -f: Force process
- -v: mount bind


****Example to create an image on our local machine****

1. Create the Dockerfile
2. run the following command (it's neccesary to be on the same level of the docker file): 
  docker image build  -t (yourDockerhub username)/(image name):(tag name) .
  docker image build -t jodevelopers/gsd:first-ctrl .
3. Check the image locally running the following command:
  docker images
4. Push your image to a docker hub running the follogin command:
  docker image push (yourDockerhub username)/(image name):(tag name)
  docker image push jodevelopers/gsd:first-ctrl
5. Remove the image from your local machine
  docker image rm (yourDockerhub username)/(image name):(tag name)
  docker image rm jodevelopers/gsd:first-ctrl
6. Check if the image is already remove running the following command:
  docker image ls
7. Create a container of the image, run the following command:
  docker container run -d --name (containerName) -p (port container:port of the app) (image name)
  docker container run -d --name myFirstContainer -p 8000:8080 jodevelopers/gsd:first-ctrl
8. To see the container running run the following command:
  docker container ls
9. To Stop the contaiter run the following command: 
  docker container stop (container name)
  docker container stop myFirstContainer
10. To make sure that the container is stopped run the command of the step 8.
11. To see all the container up/stoped run the following command:
  docker container ls -a
12. To start the containter again run the following command:
  docker container start (container name)
  docker container start myFirstContainer
13. To remove the container run the following command (it's neccesary to stop the container first):
  docker container rm (container name)

****Interactive Command****

- exit(exit of the command line but the container still running): Ctrl+p+q

****Container Life Cycle****

****Bind Mount ****

- It??s to share a machinehost folder to a container 
- It??s the easy way to share or keep documents on the container
- It??s no secure at all because if you give acces to the container to sensitive data and you??re using an image not wecure probably will be dangerous
- To use use the following command
	- docker run -d --name db -v src/documents/docker/mongo:src/db mongo
- For bind mounts docker uses -v and the path of the machinehost then the path of the container
	- -v (machinehost path:container path)

****Volumes****
- It??s like a private folder into the container but its persistant
- It??s more secure because only the container know where it is located and also only the container can see the files into it
- To use it it??s neccessary to add the following command:
	- docker volume create volumeName 
	- Or: --mount src:
	- 
****Docker Compose****
- docker-compose up
- docker-compse up -d
- docker network ls
- docker network inspect networkname
- docker-compose logs
- docker-compose logs containername
- docker-compose logs -f containername
- docker compose logs -f containername1 containername2 ...
- docker-compose exec containername fn -> docker-compose exec app bash (it's not neccesary the interactive mode)
- docker-compose ps
- docker-compose down
- docker-compose build
- docker-compose -d --scale containername=numberOfContainers

*********

****UBUNTU****
- All the ubuntu commands return an exit code.
- The exit code 0 is everithing is correct.
- The exit code != 0 probablly an error was occur on the process.


****Commands****
  - ls: List all the file names of the root or path located
  - ls -lac: List all the files of the roor or path located but with all the information of the each folder.
  - cat /etc/lsb-release: Show information about the Linux version installed
  

