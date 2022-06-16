# Deploy Docker Swarm on AWS EC2 with Ansible

This is based on a [blog post](https://www.seelk.co/blog/docker-swarm-on-aws-with-ansible/) and its 
associated [GitHub repo](https://github.com/BorisLaporte/ansible_aws_docker_swarm_tutorial).
(It's not a fork because I created it by following along with the blog post one step at a time.)

I had to change a lot of things because the 
blog post used deprecated methods and plugins,
but this allowed me to learn more about
what I was doing.

The only thing hardcoded in here is the VPC and subnet IDs. You will also need an ssh key to make this work - you can get this from me. 

