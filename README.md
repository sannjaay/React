Pull and Run hello-world
docker pull hello-world
docker run hello-world
Tests Docker installation with a sample container.
List Containers
docker ps       # Running containers
docker ps -a    # All containers, including stopped ones
Remove Containers and Images
docker rm [container-id]      # Removes a container
docker rmi hello-world        # Removes an image
Experiment 2: Running Redis with Docker
Pull Redis Image
docker pull redis
Downloads the Redis image from Docker Hub.
Run Redis Container
docker run --name my-redis -d redis
Runs Redis in the background.
Access Redis CLI
docker exec -it my-redis redis-cli
Opens Redis CLI in the container.
Example Commands:
Set value:
SET name "Alice"
Get value:
GET name
Stop and Remove Redis
docker stop my-redis
docker rm my-redis
docker rmi redis
Stops and removes the Redis container and image.
Experiment 3: Building Custom Images Using Dockerfile
Write and Build a Dockerfile
docker build -t custom-redis .
Builds an image named custom-redis from the Dockerfile.
Run a Container from the Custom Image
docker run --name redis-container -d custom-redis
Runs a container named redis-container.
Commit Changes to a New Image
docker commit [container-id] yourusername/redis-custom
Saves the container state as an image.
Push Image to Docker Hub
docker login
docker tag custom-redis yourusername/custom-redis
docker push yourusername/custom-redis
Logs in, tags, and uploads the image to Docker Hub.
Experiment 4: Docker Compose for Multi-Container Applications
Create and Run Containers Using Compose
docker-compose up -d
Starts all containers defined in the docker-compose.yml.
Stop and Remove Compose Containers
docker-compose stop          # Stops containers
docker-compose down          # Removes containers
Access Services Locally
Open the browser at:
http://localhost:<port>
Example: WordPress setup accessible at http://localhost:8000.
Experiment 5: Modify and Push Docker Image
Pull Base Image (e.g., Ubuntu)
docker pull ubuntu
Run and Access a Container
docker run -it --name my-ubuntu -d ubuntu
docker exec -it my-ubuntu bash
Install Software Inside Container
apt update
apt install git -y
git --version
Save Container Changes to an Image
docker commit my-ubuntu yourusername/ubuntu-custom
Push the Modified Image to Docker Hub
docker login
docker push yourusername/ubuntu-custom
Experiment 6: JavaScript Application with Docker
Create a Dockerfile for the App
Dockerfile
FROM node:16-alpine
WORKDIR /app
COPY calculator.js /app
CMD ["node", "calculator.js"]
Build and Run the Image
docker build -t simple-calculator .
docker run simple-calculator
Push the Image to Docker Hub
docker login
docker tag simple-calculator yourusername/simple-calculator
docker push yourusername/simple-calculator
Pull and Reuse the Image
docker pull yourusername/simple-calculator
docker run yourusername/simple-calculator
