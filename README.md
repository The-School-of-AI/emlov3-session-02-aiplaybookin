[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/tWFZppNq)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11276319&assignment_repo_type=AssignmentRepo)
# emlov3-session-02

# PyTorch Docker Assignment

Welcome to the PyTorch Docker Assignment. This assignment is designed to help you understand and work with Docker and PyTorch.

## Assignment Overview

In this assignment, you will:

1. Create a Dockerfile for a PyTorch (CPU version) environment.
2. Keep the size of your Docker image under 1GB (uncompressed).
3. Train any model on the MNIST dataset inside the Docker container.
4. Save the trained model checkpoint to the host operating system.
5. Add an option to resume model training from a checkpoint.

## How to run the code

1. Login to [Dockerhub](https://hub.docker.com "visit here") 
2. Create an account
3. Go to *Account Settings* and create a access token 
4. From your local machine/ gitpod etc wherever the code is ( and has docker installed) 
```
docker login -u vikashkr117
```
and enter the *password*

6. To build the docker image
```
docker build --tag vikashkr117/docker-demo-2023 .
```

7. To run the docker
```
docker run --rm vikashkr117/docker-demo-2023
```

8. To run test cases
```
bash ./tests/grading.sh
```

9. To push to DockerHub
```
docker push vikashkr117/docker-demo-2023
```

10. To pull from Dockerhub
```
docker pull vikashkr117/docker-demo-2023
```



## Use *BLACK* to format code
1. Install
```
pip install black
```

2. To format the scripts in current directory
```
black .
```

## Other reference commands
To remove 
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - all dangling build cache
```
docker system prune  // to remove any 
```

```
docker ps                  // ps to see running containers
docker image ls            // to see all images built
docker run -it ubuntu ls
docker run -it ubuntu bash  // access inside the container : host fliesystem
docker exec -it <name of running container> <command to execute>    //e.g.  docker exec -it stotic bash
docker ps -a     // all container that was run and existed, it also shows command run in that
docker ps -aq    // all container id only that was run and existed, it also shows command run in that
// mount volume (code folder etc) to a docker
docker run -it -v <local path>:<docker path> ubuntu bash
// to remove all previous exited containers 
docker rm $(docker ps -aq)
docker inspect ubuntu // look inside the image details
docker run -p 80:5000 catgif          // route port 80 of host machine to port 5000 of conatiner
```