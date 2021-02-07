---
title: "Version control and distribution"
date: 2021-02-06
categories: etc
---

## Version control and deployment procedure

![1](https://user-images.githubusercontent.com/54389889/107114983-dad52f00-68ac-11eb-983f-dd4c8bd6abe9.png)

When done with Docker, I don't recommend this procedure for tasks that cause drawbacks.

## Notes for each step

Please proceed with the development while paying attention to the development environment and dependency. 

If you are using Python, you will have to deal with anaconda environment files such as environment.yml or requirements.txt, which can be installed with the pip command.

Once you are familiar with the development environment and dependencies, you will be comfortable working with Dockerfiles. If the docker container works normally with a Dockerfile, push the project containing the Dockerfile to github. 

![image](https://user-images.githubusercontent.com/54389889/107140238-0e26c500-6964-11eb-92f1-41622792f2a7.png)

Go to Docker Hub -> Login -> Account setting -> Linked Accounts and link your GitHub account.

And create a new repository on dockerhub and connect it with the GitHub repository. (Docker images are built automatically by triggering a git push.)
 
At this time, pay attention to the Docker tag for the Docker image version control. When you're done, you can create a dependency-free, automatic build deployment environment.