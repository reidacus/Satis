###Helm Satis Project

##Overview
The idea of this projeect is to have Satis eventually containerised and compiled into a helm chart, ready for deploying into a K8s cluster. The project is decomposed into the following areas:

#Docker-Compose
This simply takes the Satis container image which sits on Docker Hub and turns this into a docker compose file which reads in the config.json and outputs to the 'output' folder. Make sure that your cwd is ./satis/Docker_Compose before running docker-composee up
**Status: Completed

#Manifest
This section contains the manifest file in yaml format for deploying the exact same solution to K8s instead of Docker. 
**Status : In Progress

#Helm
This section contains the packaged helm chart of the manifest file
**Status : In Progress