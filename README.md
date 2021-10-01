# Helm Satis Project

## Overview
The idea of this projeect is to have Satis eventually containerised and compiled into a helm chart, ready for deploying into a K8s cluster. The project is decomposed into the following areas:

### Docker-Compose
This simply takes the Satis container image which sits on Docker Hub and turns this into a docker compose file which reads in the config.json and outputs to the 'output' folder. Make sure that your cwd is ./Docker_Compose before running docker-compose up
**Status**: Completed

### Manifest
This section contains the manifest file in yaml format for deploying the exact same solution to K8s instead of Docker. The podmanifest.yaml file was created with _kompose convert --volumes hostPath_
#### Problems
1. In the docker container we execute build config.json output however build is a PHP command. This works as a locally deployed Docker image as my local host has PHP installed however the K3D agent nodes do NOT have PHP installed. Question: How do we go about installing a package onto the K3D nodes?
    Note to Self : It looks like these use an Alpine Linux image so will be the apk package manager, but i'm still unable to install a package to these nodes. How to work around this?
2. Storage. The volumeMounts have to be changed to hostPaths just for temp testing but this means that any output will be redirected onto the K3D node rather than my local machine
**Status** : In Progress

### Helm
This section contains the packaged helm chart of the manifest file. Once the above is correctly worked out, then it should simply be a case of running kompose convert -c 
**Status** : In Progress