# docker-artifactory
## Introduction
The version of the docker image of Artifactory OSS (https://hub.docker.com/r/mattgruter/artifactory/) is too old,and its function is also limitted. 

JFrog also provide docker image for Artifactory Pro version, however it is docker images can't be pulled from docker.bintray.io/jfrog/artifactory-pro:latest.

So by customzing the Dockerfile "https://hub.docker.com/r/mattgruter/artifactory/~/dockerfile/" to support build your own docker image for Artifactory Pro.

## Build
1. Clone this repository to foler like "docker-artifactory";
2. Download Artifactory Pro Standalone (zip package) from https://www.jfrog.com/download-artifactory-pro/;
3. Pick the artifactory.war file from downloaded zip packgae into "docker-artifactory/5.3.0";
4. Run "docker buid -t xxxx .";

Note,
In the Dockerfile, you can also change the tomcat version.

## Docker Hub release
