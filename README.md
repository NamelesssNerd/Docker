# Docker setUp with react projectsssss
## docker file
    FROM node:18 //-- docker image name [node 18]
    WORKDIR /app  //---- working directiory for docker
    COPY ./package*.json ./    //---- copy package file into docker [package.json and package.lock.json]
    RUN yarn install    //--- installing the dependency into the docker container
    COPY . .    //--- copy all the things into docker container after [extra file into the docker]
    CMD [ "yarn","run","dev" ]  //--- development command

## build command
    docker build -t testreact-image location-path  [if same file write only .]

## see all docker image
    docker image ls
    docker images

### running the docker image file 
    docker run --name  container-name --rm image-name
### stopping docker container
    docker stop image-name

### Running the docker file outside the docker
    docker run --rm --name conatiner-name -d -p source-port:destination-port image-name

### runnig docker and sync with the local file
    docker run --rm --name container-name -d -p source-por:destination-port -v $(pwd):/app image-name


### Docker image CLI
Commands | Descriptions 
--- | ---
docker run ubuntu | Pull the ubuntu image and make a container with default name
docker image prune -a | remove all the unused docker images
docker inspect <image_id> | gives the information about the installed docker image having the current image_id
docker image rm <image_id> | remmoving the docker image with given image_id

### Docker container CLI
Commands | Descriptions 
--- | ---
docker container ls --all | List all the docker running container
docker excute <container_name> <your_command> | run the command inside the docker container without intering inside it<br>eg: docker excute sushant mkdir newFolder





