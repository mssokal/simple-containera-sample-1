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
```

**(3)** To check the image that has been built, you can use one or more of the command below:
```
$ docker image ls
...
$ docker image ls ecs-nht-apache-*
...
$ docker inspect ecs-nht-apache-sample-1
...
```

**(4)** Running a container from the image
Interactive mode
```
$ docker run --interactive --tty -p 8080:80 ecs-nht-apache-sample-1
```

Detached mode:
```
$ docker run --detach -p 8080:80 ecs-nht-apache-sample-1
```


## Sample 2

The sample one uses the following files:
- Dockerfile.2
- src/sample2/dash-brain-viewer.tar.gz


### How to use this example

**(1)** Make sure your current directory is "simple-containera-sample-1"

**(2)** Have a look into the file "Dockerfile.2" before you build the container to see the declarations used understand what is happening. Use the [Dockerfile reference documentation](https://docs.docker.com/engine/reference/builder/) to know more about each declaration.

```
$ docker build --tag ecs-nht-brain-sample-2:latest --file Dockerfile.2 .
```      

NOTE: Please observe the message in the end for the build as indicated below:
```
Successfully built d73b33566876
Successfully tagged ecs-nht-brain-sample-2:latest
```
          
**(3)** To check the image that has been built, you can use one or more of the command below:
```     
$ docker image ls
...          
$ docker image ls ecs-nht-brain-*
... 
$ docker inspect ecs-nht-brain-sample-2
...
```



**(4)** Running a container from the image
Interactive mode
```
$ docker run --interactive --tty -p 8080:8050 <image_id>
```

Detached mode:
```
$ docker run --detach -p 8080:8050 <image_id>
```

