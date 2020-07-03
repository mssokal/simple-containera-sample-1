# simple-containera-sample-1
List of simple and small conatiners that can be used during Docker training.

## How to clone this repository

The first step is making sure you have clone the repository. On a terminate, execute the command below:
```
$ git clone https://github.com/mssokal/simple-containera-sample-1.git
```

Once the repository is cloned you can jump into the examples.

## Sample 1

The sample one uses the following files:
- Dockerfile.1
- src/sample1/index.html.1


### How to use this example

**(1)** Make sure your current directory is "simple-containera-sample-1"

**(2)** Have a look into the file "Dockerfile.1" before you build the container to see the declarations used understand what is happening. Use the [Dockerfile reference documentation](https://docs.docker.com/engine/reference/builder/) to know more about each declaration.

```
$ docker build --tag ecs-nht-apache-sample-1:latest --file Dockerfile.1 .
Sending build context to Docker daemon  79.87kB
Step 1/3 : FROM httpd:latest
latest: Pulling from library/httpd
8559a31e96f4: Pull complete 
bd517d441028: Pull complete 
f67007e59c3c: Pull complete 
83c578481926: Pull complete 
f3cbcb88690d: Pull complete 
Digest: sha256:387f896f9b6867c7fa543f7d1a686b0ebe777ed13f6f11efc8b94bec743a1e51
Status: Downloaded newer image for httpd:latest
 ---> ccbcea8a6757
Step 2/3 : WORKDIR /usr/local/apache2/htdocs
 ---> Running in 426c5be0f61f
Removing intermediate container 426c5be0f61f
 ---> d3dda9983d0e
Step 3/3 : COPY ./src/sample1/index.html.1 index.html
 ---> caa99d084476
Successfully built caa99d084476
Successfully tagged ecs-nht-apache-sample-1:latest
$
```

**(3)** To check the image that has been built, you can use one or more of the command below:
```
$ docker image ls
...
$
$ docker image ls ecs-nht-apache-*
...
$
$ docker inspect ecs-nht-apache-sample-1
...
```
