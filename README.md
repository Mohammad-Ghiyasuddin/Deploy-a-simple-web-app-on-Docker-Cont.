# Deploy a Simple Web App with Docker

To deploy a simple web app using Docker on Ubuntu, follow these instructions.

## Install Docker on Ubuntu

First, update your package index:

```bash
sudo apt update
```
##Instal prerequiste 

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
## Add Docker official GPG KEY

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
## Add Docker Repository

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

##Update Package

```bash
sudo apt update
```
##install docker

```bash

sudo apt install docker-ce
```

##Verify Docker install

```bash
sudo systemctl status docker
```

##Create peoject directory
```bash
mkdir my-web-app
cd my-web-app
```

##Create Index.html
```bash
nano index.html
```
use index.html file code


## Create Dockerfile
```bash
nano Dockerfile
```
Use dockerfile code

###Build Docker image

```bash
sudo docker build -t my-web-app .
```

##Docker container
```bash
sudo docker run -d -p 8080:80 my-web-app
```

##Finally, open a web browser and navigate to http://localhost:8080 to see your web page
