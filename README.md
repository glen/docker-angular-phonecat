# AngularJS Phone Catalog Tutorial Application using Docker


## Overview
The phonecat app runs in a docker container, thereby reducing the need to install additional softwares in your host system.

## Prerequisites
Docker
Virtualbox or VMWare
The angular phonecat tutorial - https://github.com/angular/angular-phonecat.git package.json file's start script provides localhost as the host - this should be changed to 0.0.0.0
```
http-server ./app -a 0.0.0.0 -p 8000 -c-1
```

### Node.js and Tools
Build the image
```
docker build -t phonecat-angular .
```

Run the container
```
docker run -it --rm -p 8000:8000 -v $(pwd):/usr/src/app --name phonecat-app phonecat-angular
```

Explanation
- Provides port mapping between the container to the host [Using port 8000]
- Provides volume sharing between the container and the host.

Find out the machine ip - in a new terminal run
```
docker-machine ip
```

Open the angularjs phonecat app in a brower using the ip address obtained above along with the port - http://192.168.99.100:8000
