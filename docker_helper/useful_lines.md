# Installing docker

 * sudo yum/apt-get install docker
 * systemctl start docker #this force starts docker daemon
 
 # Environment variables
 
 ## SSH agents
 
To create a new ssh agent run 
$eval `ssh-agent -s`
$ssh-add  # This adds the default identity file to this agent

#Running docker
Basic build

```$docker build -t proj_name:version_name .```

building with env variables

```DOCKER_BUILDKIT=1 docker build -t proj_name:latest --ssh default --secret id=aws,src=$HOME/.aws/credentials  .```

or if you need sudo 

```sudo -E DOCKER_BUILDKIT=1 docker build -t proj_name:latest --ssh default --secret id=aws,src=$HOME/.aws/credentials  .```
