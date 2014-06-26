# Ceres in Docker
Dockerfile for ceres .

# Installation

Build it
```
sudo docker build --rm -t <username>/ceres .
```

Install and run [dockerfile/mongodb](https://index.docker.io/u/dockerfile/mongodb/ "dockerfile/mongodb")
```
sudo docker pull dockerfile/mongodb 
sudo docker run -d -p 27017:27017 --name mongodb dockerfile/mongodb
```

Fill in twitter credentials and other server configuration (e.g. port, build, ...) in `opt/server-config.edn` on the local machine where docker is running. Be sure that you are the only one having access to this file. **Do not** share this file with others.


Run it
```
sudo docker run -d --link mongodb:db --name ceres -p 8082:8082 <username>/ceres
```
