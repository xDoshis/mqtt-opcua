# MQTT to OPCUA Bridge
Takes mqtt topics to an OPC UA server via folders. Supports read/write.

I've also put this code into a container using Docker, for anybody who would like to run it that way. 

*This project is based on code written by github user nzfarmer1. I've taken it and tried to modify it to be compatible with newer versions of nodejs, opcua, and mqtt.*

## General Usage
```
$ git clone https://github.com/xdoshis/mqtt-opcua
$ cd mqtt-opcua
$ npm link
$ node examples/run.js
```
## Running in Container 
If you would like to run the code inside of a container, use the following steps:
First make sure that you have docker installed, you can find steps for ubuntu at the following link (steps for other OS can be found on the side bar): https://docs.docker.com/engine/install/ubuntu/

To build the image:
```
$ npm install 
$ docker build -t your_dockerhub_username/mqttopcua .
```
You can make sure that the image was created with the following step:
```
$ docker images 
```
If created successfuly, you should receive something that looks kind of like this:
```
REPOSITORY                                         TAG                 IMAGE ID            CREATED             SIZE
your_dockerhub_username/mattopcua                 latest              5740a0a79bf9        8 seconds ago       1.06 GB
```
Now, to run the container in the background:
```
$ docker run --name mqttopcua-bridge -p 8324:8234 -d your_dockerhub_username/mqttopcua
```
You can set the --name to whatever works best for you, and also reroute the ports if needed.

## Notes
**The code is still buggy and I'm slowly working on patching things. If you encounter any issues or have suggestions on how to go about fixing them, please reach out! 
You can send me an email at: DariaChekhovskaya@gmail.com**
