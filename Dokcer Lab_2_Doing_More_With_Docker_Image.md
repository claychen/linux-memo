# Dokcer Lab2

- Subtitle - Doing more with docker image
- url https://training.play-with-docker.com/ops-s1-images/
- concept 

## Image creation from a container

```
# example
docker container run -ti ubuntu bash
## after in the bash of ubuntu docker

apt-get update
apt-get install -y figlet
figlet "hello docker"

docker container ls -a
## to get the docker ID　of ubuntu docker
docker containner commit <CONTAINER ID>
## create image from docker container

docker image ls
## viewing images
docker image tag <Image ID> ourfiglet
## set the name of image

docker container run ourfiglet figlet hello
## using figlet command in ourfiglet image to print 'hello'

```



## Image creation using a Dockerfile

```
docker image build -t hello:v0.1 .
```


