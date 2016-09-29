# NVIDIA Docker Setup
## 1. Install docker. ([source](https://docs.docker.com/engine/installation/linux/ubuntulinux/))
### 1) Update apt sources.
`$ sudo apt-get update`<br />
`$ sudo apt-get install apt-transport-https ca-certificates`<br />
`$ sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D`<br />
`$ sudo vim /etc/apt/sources.list.d/docker.list`<br />
Add the following entry in the file.<br />
Ubuntu 14.04: `deb https://apt.dockerproject.org/repo ubuntu-trusty main`<br />
Ubuntu 16.04: `deb https://apt.dockerproject.org/repo ubuntu-xenial main`<br />
`$	sudo apt-get update`<br />
`$	sudo apt-get purge lxc-docker`<br />
`$	apt-cache policy docker-engine`<br />
### 2) Install recommended packages.<br />
`$	sudo apt-get update`<br />
`$	sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual`<br />
### 3) Install docker engine.<br />
`$	sudo apt-get update`<br />
`$	sudo apt-get install docker-engine`<br />
`$	sudo service docker start`<br />
`$	sudo docker run hello-world`<br />
## 2. Install NVIDIA wrapper over the docker. ([source](https://github.com/NVIDIA/nvidia-docker))
`$	wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.0-rc.3/nvidia-docker_1.0.0.rc.3-1_amd64.deb`<br />
`$	sudo dpkg -i /tmp/nvidia-docker*.deb && rm /tmp/nvidia-docker*.deb`<br />
## 3. Pull a docker image you will use.
Ex) Pull cuda-torch.<br />
`$	sudo docker pull kaixhin/cuda-torch:latest`<br />
## 4. Account setup for your image.
This setup enables getting the same authority between your host account and your image account.<br />
Get your user id and group id in your host system.<br />
`$	id`<br />
Get into your container and make the same account.<br />
`$	groupadd -r dgyoo -g 1000`<br />
`$	useradd -u 1000 -g dgyoo -m -s /bin/bash dgyoo`<br />
Optional) Give image users an authority to execute and read files in `/root/` if some packages are installed there like Torch.<br />
`$	chmod -R 555 /root/`<br />

