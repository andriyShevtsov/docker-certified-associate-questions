1. Complete the setup of a swarm mode cluster, with managers and worker nodes

- create a new swarm `$ docker swarm init --advertise-addr <MANAGER-IP>`
- To retrieve the join command including the join token for worker nodes, run the following command on a manager node: `$ docker swarm join-token worker`
  - To retrieve the join command including the join token for manager nodes, run the following command on a manager node: `$ docker swarm join-token manager`
- Run the command from the output on the worker to join the swarm: ```docker swarm join \
  --token SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
  192.168.99.100:2377```
  - Run the command from the output on the manager to join the swarm: ```docker swarm join \
    --token SWMTKN-1-49nj1cmql0jkz5s954yi3oex3nedyz0fb0xx14ie39trti4wxv-8vxv8rssmk743ojnwacrr2e7c \
    192.168.99.100:2377```

• State the differences between running a container vs running a service



• Demonstrate steps to lock a swarm cluster
• Extend the instructions to run individual containers into running services under swarm
• Interpret the output of "docker inspect" commands
• Convert an application deployment into a stack file using a YAML compose file with "docker stack deploy"
• Manipulate a running stack of services
• Increase # of replicas
• Add networks, publish ports
• Mount volumes
• Illustrate running a replicated vs global service
• Identify the steps needed to troubleshoot a service not deploying
• Apply node labels to demonstrate placement of tasks
• Sketch how a Dockerized application communicates with legacy systems
• Paraphrase the importance of quorum in a swarm cluster
• Demonstrate the usage of templates with "docker service create"
