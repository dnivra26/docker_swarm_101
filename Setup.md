### Setup
1. Create Docker Machines  
```
docker-machine create --driver virtualbox master  
docker-machine create --driver virtualbox slave1  
docker-machine create --driver virtualbox slave2  
```  
2. Initialize Docker Swarm
```
docker swarm init --advertise-addr 192.168.99.100
```
3. Add Worker Nodes

```
docker swarm join --token TOKEN 192.168.99.100:2377
```

### Notes
- Manager and Worker Role (both multiple)
- RAFT protocol


### Miscellaneous Commands
- Find IP of docker machine  
```docker-machine ip master```
- SSH to a docker machine  
```docker-machine ssh master```
- List Swarm Nodes (can only be run on a manager)
```docker node ls```
- Print command to join swarm
```docker swarm join-token worker|manager```
- Info about swarm (can be run on any node in a swarm)
```docker info```



References  
- https://rominirani.com/docker-swarm-tutorial-b67470cf8872
- https://docs.docker.com/machine/overview/