# Docker with Microservices
Docker integration with java


# Important Command 

<details><summary> Command</summary>
<p>

  <details><summary> General commands</summary>
<p>
- Install docker 

```
yum install docker
```

- Docker version 

```
docker --version
```
  
- Start docker service 

```
service docker start
```
  
- Check docker information 

```
docker info
```
  
- To Check docker image in linux box 

```
docker images
```
  
- To pull docker image and run 

```
docker run hello-world
```
  
- To pull docker image and with version 

```
docker pull mysql:5.7
```

- Docker process status 

```
docker ps
```

- To stop Docker 

```
docker stop <container id>
```

- To remove Docker container 

```
docker rm -f <contain id>
```
  
- To remove Docker image 

```
docker rmi -f <image id>
```
  
- Give container custome name

```
docker run -dit --name=mycontainer nginx
```  
  
- Give container custome name with port

```
docker run -dit --name=mycontainer -p 8000:80 nginx
```  

- Pause and unpause container

```
docker pause/unpause <container name>
``` 
 </p>
</details>
  
<details><summary> Docker MYSQL Command</summary>
<p>
```
 docker run -d -p 6666:3306 --name=docker-mysql --env="MYSQL_ROOT_PASSWORD=test1234" --env="MYSQL_DATABASE=emp" mysql
```
```
docker exec -it docker-mysql bash
```
```
mysql -uroot -p 
```
- Enter mysql password
```
test1234
```
- Perform some sql command
```
mysql> show databases;
```
```
mysql> show tables; 
```
</p>
</details>
  
  
<details><summary> Volumrs and bind mount</summary>
<p>
  
- List all the volumes docker is maintaining

```
docker volumes ls
``` 
  
- Create docker volume

```
docker volumes <create volume_name> myvolume
``` 
  
- Mount container to volume

```
docker run -dit --mount source=myvolume,destination=/temp nginx
``` 
</p>
</details>
  
  
<details><summary> Docker network</summary>
<p>
  
- To list network

```
docker network ls
``` 
  
- Create network 

```
docker network create denonetwork --subnet=172.19.0.0/16
``` 
  
- Attach network to container

```
docker run --name webserver2 --net demonetwork --ip 172.19.0.2 -h web.mausam.com -p 82:80 -ti ubuntu /bin/bash
``` 

- Connect and disconnect network to container

```
docker network di/connect <network name> <container name>
``` 

  
</p>
</details>
  
  
<details><summary> Create custome docker image</summary>
<p>
  
- Crate dockerfile
```
vi dockerfile
``` 
 
- Create docker file with followind syntac
```
  FROM centos
  RUN yum install -y httpd
  ADD index.html /var/www/html
  CMD apachectl -D FOREGROUND
  EXPOSE 80
  MAINTAINER MAUSAM
  ENV myenv myvalue
  
``` 
```
docker build -t myimagename .
  
``` 
</p>
</details>
  
  
<details><summary> Publish image to docker hun</summary>
<p>
  
- Tag docker file
```
docker tag <image name> <docker hub user name>/<image name>
``` 
- Push to hun
  
```
docker push <docker hub user name>/<image name>
``` 
</p>
</details>
  
</p>
</details>

