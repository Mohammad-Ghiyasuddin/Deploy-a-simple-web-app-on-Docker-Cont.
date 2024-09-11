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

***Index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Docker Web App</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: black;
            color: white;
            font-family: Arial, sans-serif;
        }
        .container {
            text-align: center;
        }
        h1 {
            margin: 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Hello from Docker container</h1>
        <h2>I am live</h2>
    </div>
</body>
</html>

***
## Dockerfile

# Use the official Nginx image
FROM nginx:alpine

# Copy the HTML file into the container
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80
EXPOSE 80
##

###Build Docker image

```bash
sudo docker build -t my-web-app .
```

##Docker container
```bash
sudo docker run -d -p 8080:80 my-web-app
```

##Finally, open a web browser and navigate to http://localhost:8080 to see your web page
