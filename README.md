# dockerStartUp
This is a docker start up 

Alpine: Light version is created for containers, best practices is to use that version of linux for containers.

Key Docker commands

docker build: Build a docker image
docker run: Run a docker image as a container
docker commit: Commit a docker container as an image
docker tag: Tag a docker image
docker login: To login for docker hub
docker images | head : Show latest images
docker ps : Show running images
docker ps -a: Show all latest images running or stopped
docker 

Image: In Object programming the image is like a class.

Container: In object programming the container is like an object.

Keys:

-d: run the container in the background (detach)
-it: Interactive
-p: port mapping (port container:port of the app)
-f: Force process


Example to create an image on our local machine

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

Interactive Command:

exit(exit of the command line but the container still running): Ctrl+p+q


****Volumes

