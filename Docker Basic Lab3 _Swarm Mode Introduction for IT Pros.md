# Swarm Mode Introduction for IT Pros

- url https://training.play-with-docker.com/ops-s1-swarm-intro/



## Swarm

- An example

```shell
[node1]$ docker swarm init --advertise-addr $(hostname -i)
# initialize docker swarm, copy the prompt mesassage
[node1]$ docker swarm join-token worker
# show the token of joining swarm as worker
[node2]$ docker swarm join --token <token> 192.168.0.43:2377
# add node2 into the swarm of node1
[node1]$ docker node ls
# showing manager and worker information

[node1]$ git clone https://github.com/docker/example-voting-app
[node1]$ cd example-voting-app 
```

