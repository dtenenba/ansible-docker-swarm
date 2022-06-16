# Deploy Docker Swarm on AWS EC2 with Ansible

This is based on a [blog post](https://www.seelk.co/blog/docker-swarm-on-aws-with-ansible/) and its 
associated [GitHub repo](https://github.com/BorisLaporte/ansible_aws_docker_swarm_tutorial).
(It's not a fork because I created it by following along with the blog post one step at a time.)

I had to change a lot of things because the 
blog post used deprecated methods and plugins,
but this allowed me to learn more about
what I was doing.

The only thing hardcoded in here is the VPC and subnet IDs. You will also need an ssh key to make this work - you can get this from me. 

## Steps:

```
ansible-playbook create_ec2_playbook.yml
ansible-playbook deploy_swarm_playbook.yml
ansible-playbook deploy_stack_playbook.yml

```

Get the FQDN of the manager with this command:

```
ansible-inventory --graph
```

Hit the web apps at:

```
http://<FQDN>:5000
http://<FQDN>:5001
http://<FQDN>:8080
```

Optionally SSH to the manager and inspect the swarm.

When done, shut everything down (important!) with:

```
ansible-playbook remove_ec2_playbook.yml
```

## Next Steps

* Install Portainer
* Install Traefik and set up ingress/SSL termination
* Add authentication to swarm

