<img src="https://profile-counter.glitch.me/NamelesssNerd/count.svg" />
# Docker setUp with react projectsssss
## sample docker file [Dockerfile]

command | descriptions
--- | ---
FROM node:18 | Pull the nodejs docker image from dockerhub
WORKDIR /app  | working directory for docker image
COPY ./package*.json ./ | copy package file into docker [package.json and package.lock.json]
RUN yarn install | installing required dependencies into the docker container
COPY . .  | copy all the file and folder from local to docker container home or working directory
CMD [ "yarn","run","dev" ]  | Entry point for docker container 


### Docker image CLI
Commands | Descriptions 
--- | ---
docker search <image_name> | Search docker image in docker hub <code> Eg: ubuntu </code>
docker run ubuntu | Pull the ubuntu image and make a container with default name
docker pull <image> | downloads an image from a registry. Example: docker pull ubuntu
docker build <path> | builds an image from a Dockerfile. Example: docker build.
docker tag <image> <repository>:<tag> | tags an image with a repository and tag. Example: docker tag my-image my-repo:1.0
docker push <repository>:<tag> | pushes an image to a registry. Example: docker push my-repo:1.0
docker rmi <image> | removes an image. Example: docker rmi my-image
docker image prune -a | remove all the unused docker images
docker inspect <image_id> | gives the information about the installed docker image having the current image_id
docker image rm <image_id> | remmoving the docker image with given image_id
docker image ls ,docker images | list all the running docker images
docker build -t testreact-image location-path  [if same file write only .] | building the docker image
docker run --name  container-name --rm image-name | running the docker image with custome name
docker run --rm --name conatiner-name -d -p source-port:destination-port image-name | accessing the docker image from outsidde it
docker run --rm --name container-name -d -p source-por:destination-port -v $(pwd):/app image-name |  accessing the docker image from outsidde it and auto sync when any change is happened
docker stop image-name or <image_id> | stop the relevent docker image



### Docker container CLI
Commands | Descriptions 
--- | ---
docker container ls --all | List all the docker running container
docker excute <container_name> <your_command> | run the command inside the docker container without intering inside it<br>eg: docker excute sushant mkdir newFolder
docker run <image> | creates and starts a container based on the specified image. Example: docker run nginx
docker start <container> | starts a stopped container. Example: docker start my-container
docker stop <container> | stops a running container. Example: docker stop my-container
docker rm <container> |  removes a stopped container. Example: docker rm my-container 
docker ps | lists all running containers. Example: docker ps
docker ps -a | lists all containers, including stopped ones. Example: docker ps -a
docker logs <container_id> | displays the logs of a container. Example: docker logs my-container
docker volume ls | list all the available docker volume
docker volume rm <volume_name> | remove the related docker volume
docker run -it -P <Image> | Automatic port mapping Note: add <code> Expose <your_port> </code> into the Dockerfile eg:3000
docker tag <your_image> <custome_name> | giving the the custom tag name to the docker image
docker push <Your_image> | pushing the docker image into Docker hub
docker run -it -v /yourPath:/home/app ubuntu | attaching the host volume
docker compose up | make ready numbers of containers at a time <code>Note: create docker-compose.yml file</code>
docker compose down | Killing all the composed container <code>Note: Docker composed into the stack </code>
docker compose up -d | compose all the caontainer and run it in background mode. <code>Note: other service can be used at same time</code>








