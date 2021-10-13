
Build the docker image
$ docker build . -t sampleapp

Multi-stage build
$ docker build . -f Dockerfile.multistage -t sampleapp

Tag the image
$ docker tag sampleapp testrepo/sampleapp:1.0.0

Login to docker with your docker Id
$ docker login
Login with your Docker ID to push and pull images

Push the image to docker hub
$ docker push testrepo/sampleapp:1.0.0

Create Kubenetes deployment
$ kubectl apply -f deployment.yml

Create a loadbalancer service to expose the app
kubectl apply -f service.yml

Get the service configuration ( External IP)
kubectl get services

Check the EXTERNAL-IP column and copy the IP address associated with the sampleapp-service.
Access the app through browser http://<ipaddress>