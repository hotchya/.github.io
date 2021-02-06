---
title: Version control and distribution
date: 2021-02-06 09:38:00
categories: etc
tags: github, docker, solution
---

# Version control and distribution


## Version control and deployment procedure

![1](https://user-images.githubusercontent.com/54389889/107114983-dad52f00-68ac-11eb-983f-dd4c8bd6abe9.png)

When done with Docker, I don't recommend this procedure for tasks that cause drawbacks.

## Requirements for each step

Please proceed with the development while paying attention to the development environment and dependency. If you are using Python, you will have to deal with anaconda environment files such as environment.yml or requirements.txt, which can be installed with the pip command. Once you are familiar with the development environment and dependencies, you will be comfortable working with Dockerfiles. If the docker container works normally with a Dockerfile, push the project containing the Dockerfile to github. If the project has been uploaded to the GitHub repository normally, create a new repository on dockerhub and link it with the GitHub repository. (The Docker image is automatically built by triggering git push.) At this time, pay attention to the Docker tag for the Docker image version control. When you're done, you can create a dependency-free, automatic build deployment environment.