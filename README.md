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

Kubernetes is an open source container management platform used to deploy, manage, and scale containerized apps. It allows for tasks like managing app instances, restarting failed containers, and maintaining the desired number of running Pods to be automated. 

A  is the smallest deployable unit in kubernetes, it contains one or multiple containers that are in charge of running applications. A deployment is what is in charge of managing these pods and it ensures that the desired number of app instances are running. Kubernetes services provide a stable way to access a group of pods, it uses labels to identify what pods it's supposed to connect to and allows apps to talk with those pods without actually having to know its ip address. 

How to start minicube: 
start docker desktop using minikube start --driver=docker, then load the existing docker image (using this project as an example) minikube image load cloud-service-demo:1.0. You can apply the development and service yaml files by first using  kubectl apply -f kubernetes/deployment.yaml and the using kubectl apply -f kubernetes/service.yaml in the terminal. Doing this creates the deployhment and service resources in the kubernetes cluster. You can access the application by running kubectl port-forward service/cloud-service-demo 8080:80 and then going to https://localhost:8080, if you need to use a different pport you can edit the value in the terminal command and that will tweak it. 
