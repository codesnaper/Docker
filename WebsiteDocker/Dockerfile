#Start a new build image and Set the base image. Its 1st Directive in dockerfile except ARG
FROM ubuntu:10.04

#Set enviornment property
ENV WEBSITE_VERSION 1.0.0
ENV IMAGE_VERSION 1.0.0
ENV NGINX_VERSION 1.14.0-0ubuntu1.3

#To run command
RUN apt-get update && apt-get install -y curl
RUN apt-get update && apt-get install -y nginx=${NGINX_VERSION}
RUN echo "Image version ${IMAGE_VERSION}"

#Default command used to run a container at execution time
CMD [ "nginx","-g","daemon off;" ]

#Build a dockerfile: docker build -t custom-website .
