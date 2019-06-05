## Application Management

### Deploy
```
docker service create --replicas 5 -p 80:80 --name web nginx
```
### Scale
``` 
docker service scale web=6
```

### Rolling Update
```
docker service update --image nginx:0.6 web
```

### Delete Deployment
```
docker service rm web
```

### Notes
 - No inbuilt load balancer(k8s service equivalent)

### Miscellaneous Commands
- Find status of a service (can be run only on manager)  
``` docker service ls ```
- Status of each replica  
``` docker service ps web ```
- Find running docker daemons  
``` docker ps ```
- Deploy a stack  
``` docker stack deploy --compose-file docker-compose.yaml web ```

