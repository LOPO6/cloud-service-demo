Project name: cloud-service-demo
Purpose: to demonstrate the benefits of using a github repo to code, leading to the potential of linking with cloud services in the future
files included:
 - index.html
 - README.md

Version control helps a cloud project because it allows you to test potential features with the cloud environment before actually implementing them by pushing them to the official github. 

Docker is a platform that allows devs to package apps and their dependencies into containers. It makes apps easier to develop, distribute, and run consistently across different environments and os's.

A docker image is a read only template used to create docker containers, it contains everything needed to run an app, including the app files, dependencies, and configuration. 

A docker container is a running instance of a docker image. It provides an isolated environment in which an application can execute. 

To build and run an application using docker, use docker build -t cloud-service-demo:1.0 . in the folder terminal to build a docker image using docker file. After that, run docker run -d -p 8080:80 --name cloud-service-container cloud-service-demo:1.0 in the terminal to create and start a container from the image. This command runs the container, and maps a port (in this case port 8080) to the container (alongside also giving it a name and specifying which image to run).

