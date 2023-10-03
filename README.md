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
docker run ubuntu | Pull the ubuntu image and make a container with default name
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





