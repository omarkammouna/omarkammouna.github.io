---
title : SETUP DOCKER ON WSL2
---

## Install Docker Engine on Ubuntu

To get started with Docker Engine on Ubuntu, make sure you meet the prerequisites, and then follow the installation steps.

### Prerequisites

**Note**: If you use ufw or firewalld to manage firewall settings, be aware that when you expose container ports using Docker, these ports bypass your firewall rules. For more information, refer to Docker and ufw.

**OS requirements**: To install Docker Engine, you need the 64-bit version of one of these Ubuntu versions:

- Ubuntu Lunar 23.04
- Ubuntu Kinetic 22.10
- Ubuntu Jammy 22.04 (LTS)
- Ubuntu Focal 20.04 (LTS)
- Ubuntu Bionic 18.04 (LTS)

Docker Engine is compatible with x86_64 (or amd64), armhf, arm64, and s390x architectures.

### Uninstall old versions

Before you can install Docker Engine, you must first make sure that any conflicting packages are uninstalled.

Distro maintainers provide an unofficial distribution of Docker packages in APT. You must uninstall these packages before you can install the official version of Docker Engine.

The unofficial packages to uninstall are:

- docker.io
- docker-compose
- docker-doc
- podman-docker

Moreover, Docker Engine depends on containerd and runc. Docker Engine bundles these dependencies as one bundle: containerd.io. If you have installed the containerd or runc previously, uninstall them to avoid conflicts with the versions bundled with Docker Engine.

Run the following command to uninstall all conflicting packages:
```
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do
sudo apt-get remove $pkg;
done
```

`apt-get` might report that you have none of these packages installed.

Images, containers, volumes, and networks stored in `/var/lib/docker/` aren’t automatically removed when you uninstall Docker. If you want to start with a clean installation and prefer to clean up any existing data, read the uninstall Docker Engine section.

### Installation methods

You can install Docker Engine in different ways, depending on your needs:

1. Docker Engine comes bundled with Docker Desktop for Linux. This is the easiest and quickest way to get started.
2. Set up and install Docker Engine from Docker’s apt repository.
3. Install it manually and manage upgrades manually.
4. Use convenience scripts. This is only recommended for testing and development environments.

#### Install using the apt repository

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

#### Set up the repository

 1.Update the apt package index and install packages to allow apt to use a repository over HTTPS:

```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg 
```
 2.Add Docker’s official GPG key:

```
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```
 3.Use the following command to set up the repository:
```
echo \
  "deb [arch=\"$(dpkg --print-architecture)\" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo \"$VERSION_CODENAME\") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
``` 
## Install Docker Engine

Update the apt package index:

```
sudo apt-get update
```
 1.Install Docker Engine, containerd, and Docker Compose.
        List the available versions:
 ```
 apt-cache madison docker-ce | awk '{ print $3 }'
 ```

2.Select the desired version and install for our case in Baycii-Labs :
```
 VERSION_STRING=5:20.10.19~3-0~ubuntu-focal
 sudo apt-get install docker-ce=$VERSION_STRING docker-ce-cli=$VERSION_STRING containerd.io docker-buildx-plugin docker-compose-plugin
```
3.Verify that the Docker Engine installation is successful by running the hello-world image.

```
 sudo docker run hello-world
```
This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits.

#### You have now successfully installed and started Docker Engine.
------------------------------------------------------------
> by-OmarKammoun