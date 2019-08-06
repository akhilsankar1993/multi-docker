# multi-docker

## Goal
To run a multi-container application on AWS and allow them to communicate with
each other.

## The Deployment Flow
I am using TravisCI to:
  - build a test image of each service and run their test suite.
  - once all tests pass, build production images of each of the services.
  - deploy them to the Docker Hub.
  - push all project files to AWS EB.

## AWS Configuration
  - AWS will then pull these prod images from the Docker Hub and run containers of them.
  - It is configured with security groups and the requisite ENV variables to allow
  the containers to communicate with each other from within a VPC.
