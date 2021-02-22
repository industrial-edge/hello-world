# Installation

- [Installation](#installation)
  - [Build Application](#build-application)
    - [Download Repository](#download-repository)
    - [Build docker image](#build-docker-image)
  - [Upload App to the Industrial Edge Managment](#upload-app-to-the-industrial-edge-managment)
    - [Connect your Industrial Edge App Publisher](#connect-your-industrial-edge-app-publisher)
    - [Upload App using the Industrial Edge App Publisher](#upload-app-using-the-industrial-edge-app-publisher)
  - [Install Application on Industrial Edge Device](#install-application-on-industrial-edge-device)
  
## Build Application

### Download Repository
Download or clone the repository source code to your workstation.

### Build docker image

Open terminal in the project root path where docker-compose.yml is located and execute: 
```bash
docker-compose build
```
This command builds the docker image of the service which is specified in the docker-compose.yml file.

## Upload App to the Industrial Edge Managment

Please find below a short description how to publish your application in your IEM.

For more detailed information please see the section for [uploading apps to the IEM](https://github.com/industrial-edge/upload-app-to-iem).

### Connect your Industrial Edge App Publisher

- Connect your Industrial Edge App Publisher to your docker engine
- Connect your Industrial Edge App Publisher to your Industrial Edge Management System

### Upload App using the Industrial Edge App Publisher

- Create a new Project or select a existing one
- Create new Application
- Add a new app version
- Import the [docker-compose](../docker-compose.yml) file to the Industrial Edge App Publisher using the **Import YAML** button
- The warnings <br> `Build (Detail) (services >> hello-world >> build) is not supported` <br> 
  can be ignored
- Configure reverse proxy of hello-world service. Click **+** button to save settings
  
```txt
Container Port: 80
Protocol: HTTP 
Service Name: hello-world
Rewrite Target: /
```

<a href="graphics/reverse-proxy.png"><img src="graphics/reverse-proxy.png" height="25%" width="25%" ></a> 
<br>

- **Start Upload** to transfer the app to Industrial Edge Management
- Further information about using the Industrial Edge App Publisher can be found in the [IE Hub](https://iehub.eu1.edge.siemens.cloud/documents/appPublisher/en/start.html)

## Install Application on Industrial Edge Device

Select Uploaded version of Application and install to Industrial Edge Device.
