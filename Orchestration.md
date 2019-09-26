##  1. Complete the setup of a swarm mode cluster, with managers and worker nodes

1. create a new swarm `$ docker swarm init --advertise-addr <MANAGER-IP>`
2. To retrieve the join command including the join token for worker/manager nodes, run the following command on a manager node: `$ docker swarm join-token worker/manager`
3. Run the command from the output on the worker/manager to join the swarm:
`docker swarm join \
  --token SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
  192.168.99.100:2377 `


##  2. State the differences between running a container vs running a service


**???**


## 3. Demonstrate steps to lock a swarm cluster
- Initialize a swarm with autolocking enabled `$ docker swarm init --autolock`
-  Enable or disable autolock on an existing swarm `docker swarm update --autolock=true`



## 4. Extend the instructions to run individual containers into running services under swarm
1. Create a service`$ docker service create --name="myservice" --replicas 3 ubuntu:latest`
2. Change a service: `docker service update --replicas 5 myservice`

## 5. Interpret the output of "docker inspect" commands
Return low-level information on Docker objects. Docker inspect provides detailed information on constructs controlled by Docker. By default, docker inspect will render results in a JSON array.


## 6. Convert an application deployment into a stack file using a YAML compose file with "docker stack deploy"


**???**



## 7. Increase # of replicas
- `docker service update --replicas 2 SERVICE`
- `docker service scale SERVICE=REPLICAS`

## 8. Add networks, publish ports


`docker service update \
  --publish-add published=8080,target=80 \
  myservice`


  `docker service update \
  --network-rm my-network \
  --network-add name=my-network,alias=web1 \
  myservice`

## 9. Mount volumes


`docker service update \
    --mount-add \
      type=volume,source=other-volume,target=/somewhere-else \
    myservice`

## 10. Illustrate running a replicated vs global service

**???**


## 11. Identify the steps needed to troubleshoot a service not deploying



**???**



## 12. Apply node labels to demonstrate placement of tasks
We can use node constraints to control which nodes a service’s tasks will run on based upon node labels. Here is an example:
`docker service create --constraint node.labels.availability_zone==east nginx`
To use various expressions for constraints, such as inequality, we can run, for instance:
`docker service create --constraint node.labels.availability_zone!=east`

Use `--placement-pref` to spread tasks evenly based on the value of a specific label:
`docker service create --placement-pref spread=node.labels.availability_zone --replicas 3 nginx`

## 13. Sketch how a Dockerized application communicates with legacy systems
## 14. Paraphrase the importance of quorum in a swarm cluster
## 15. Demonstrate the usage of templates with "docker service create"
## 16. Manipulate a running stack of services
