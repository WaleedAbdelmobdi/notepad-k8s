# Notepad: Simple Spring Boot App

This simple application is used for demo purposes. It exposes the `actuator` endpoints as well as the `/notes` endpoint, which creates a note when it gets a `POST` request.

## Usage


`$ git clone https://github.com/jorgeacetozi/notepad.git`
`$ cd notepad`

Once you succesfully cloned the repository, start the application the jar artifact:

`$ mvn clean install`


Build docker images

`$ docker build -t notepad:v1 .`

Push the image to docker registery

`$ docker tag notepad:v1 waleedhassan/notepad:v1`

`$ docker login` # login to my private Registery 

`$ docker push  waleedhassan/notepad:v1`

## Usage 

`$ git clone `
`$ cd `

Create secret to pull image from the private registery

`$ kubectl create secret docker-registry regcred  --docker-server=DockerHub --docker-username=waleedhassan --docker-password=Moaz@2016 --docker-email=waleed.abdelmobdi@gmail.com `

Deploy MySQL 
`$  kubectl create -f mysql-deployment.yaml`

Deploy NotePad

`$  kubectl create -f notepad-deployment.yaml` 

`$ kubectl --namespace default port-forward $POD 8080:8080 `

Check that the application is up and running hitting the actuator /health endpoint:

`$ curl http://localhost:8080/health`
