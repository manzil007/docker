# Docker and AWS ECS

- Steps to add ECS account through AWSCLI and push/pull docker image

```
apt-get update && apt-get install -y apt-transport-https ca-certificates
apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
echo deb https://apt.dockerproject.org/repo ubuntu-trusty main > /etc/apt/sources.list.d/docker.list
apt-get update && apt-get install -y docker-engine
gpasswd -a ubuntu docker
docker pull ubuntu:14.04
curl 'https://s3.amazonaws.com/aws-cli/awscli-bundle.zip' -o 'awscli-bundle.zip'
unzip awscli-bundle.zip && ./awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws
eval '$(aws ecr get-login --region us-east-1 --registry-ids XXXXXXXXXXXX)'
export AWS_ACCESS_KEY_ID=-x-x-x-x-x-x-x-
export AWS_SECRET_ACCESS_KEY=-x-x-x-x-x-x-x-x-x-x-x-x-x-
eval '$(aws ecr get-login --region us-east-1 --registry-ids XXXXXXXXXXXX)'
docker pull XXXXXXXXXXXX.dkr.ecr.us-east-1.amazonaws.com/services-base:0.3.0
cd
ps fauwx | less
which docker
docker ps
docker images
```
