# Docker Lab 

- First Alpine Linux Container 
- url https://training.playwith-docker.com/ops-s1-hello/#
- concept
  - docker engine
  - containers & images
  - image registriess, docker hub/docker store
  - container isolation

## Hello world

```
docker container run hello-world
```

1. type `docker container run hello-world`
2. pull from registry
3. get image `hello-world:latest`
4. reply `Hello from Docker`

## Docker Images

```
docker image pull alpine
docker image ls
```

## Docker Container Run

```
# often used commands.
docker container run -it /bin/ash
## interactive shell
docker container ls
## list running containers
docker container ls -a
## list containers executed previously
```



```
# example
docker container run alpine ls -l 
## after ls cmd, 1st alpine would shutdown
docker container run alpine echo "hello from alpine" 
## after echo cmd, 2nd alpine would shutdown
docker container run alpine /bin/sh
## after sh cmd, 3rd alpine would shutdown
docker container run -it alpine /bin/sh
## docker goes into interactive mode
```



### Container Isolation

```
# example
docker container run -it alpine /bin/ash
touch 'hello.txt'
##　hello.txt appears
docker container run alpine ls
## hello.txt is missing, because it's another new and seperate instance.
docker container ls -a
## we could get the container id of the docker executed touch command
docker container start <container ID> 
## we start that container.
docker container exec <container ID> ls 
## we could see hello.txt in directory
docker container exec -it <container ID> /bin/ash
## we go into interactive shell of the continer
docker container stop <container ID>

```

