# Creating-Replicated-and-Global-Services-Docker

To deploy an application image when Docker Engine is in swarm mode, you create a service. For replicated services, you specify the number of replica tasks for the swarm manager to schedule onto available nodes. For global services, the scheduler places one task on each available node that meets the service’s placement constraints and resource requirements.

```

1. Create a replicated service with the nginx image
$ sudo docker service create --name myweb --replicas 3 nginx

2. Create a global service with the alpine image
$ sudo docker service create \
> --name myservice \
> --mode global alpine top

3. List all the Docker services
$ sudo docker service ls

4. Check the status of the global service i.e., myservice
$ sudo docker service ps myservice

5. Check the status of the replicated service i.e., myweb
$ sudo docker service ps myweb

Note: Notice that the service runs replicas on all the nodes of the swarm cluster.

```
